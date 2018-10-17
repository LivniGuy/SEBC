#!/bin/sh
# Confirm the path values given below correspond to your installation

MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
HADOOP=/opt/cloudera/parcels/CDH/bin

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 8 16
do
   # Reducer containers
   for j in 1 4
   do
      # Container memory
      for k in 512 2048
      do
         # Set mapper JVM heap
         MAP_MB=`echo "($k*0.8)/1" | bc`
         MAP_MB="${MAP_MB}MB"

         # Set reducer JVM heap
         RED_MB=`echo "($k*0.8)/1" | bc`
         RED_MB="${RED_MB}MB"

         echo "Parameters:"
         echo "mappers = $i, reducers = $j, container memory = $k"
         echo "mapper JVM heapsize = $MAP_MB, reducer JVM heapsize = $RED_MB"

         echo "Cleaning up before run"
         $HADOOP/hadoop fs -rm -r -skipTrash /results/tg-10GB-${i}-${j}-${k}
         $HADOOP/hadoop fs -rm -r -skipTrash /results/ts-10GB-${i}-${j}-${k}

        time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
	             51200000 /results/tg-10GB-${i}-${j}-${k} 1>teragen_${i}_${j}_${k}.out 2>teragen_${i}_${j}_${k}.err

       time ${HADOOP}/hadoop jar $MR/hadoop-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
	             /results/tg-10GB-${i}-${j}-${k}  \
                     /results/ts-10GB-${i}-${j}-${k} 1>>terasort_${i}_${j}_${k}.out 2>>terasort_${i}_${j}_${k}.err

        $HADOOP/hadoop fs -rm -r -skipTrash /results/tg-10GB-${i}-${j}-${k}
        $HADOOP/hadoop fs -rm -r -skipTrash /results/ts-10GB-${i}-${j}-${k}
      done
   done
done

echo Testing loop ended on `date`
