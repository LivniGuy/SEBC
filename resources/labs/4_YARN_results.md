### I used a variation of the following parameters:
Mappers - {8, 16}
Reducers - {1, 4}
Memory - {512MB, 2048MB}

Teragen was hardly affected by the changes in parameters.

### The slowest run for Terasort was with the following params:
mappers = 8, reducers = 1, container memory = 2048

These are the results:
Terasort time:
real	6m19.218s
user	0m8.605s
sys	0m0.843s

### The fastest run for Terasort was with the following params:
mappers = 16, reducers = 4, container memory = 512

These are the results:
Terasort time:
real	2m1.196s
user	0m8.400s
sys	0m0.648s






Here are the results from all the different combinations:

Parameters:
mappers = 8, reducers = 1, container memory = 512
mapper JVM heapsize = 409MB, reducer JVM heapsize = 409MB

Teragen time:
real	1m3.203s
user	0m6.191s
sys	0m0.586s

Terasort time:
real	2m36.952s
user	0m8.428s
sys	0m0.708s

Parameters:
mappers = 8, reducers = 1, container memory = 2048
mapper JVM heapsize = 1638MB, reducer JVM heapsize = 1638MB

Teragen time:
real	1m9.107s
user	0m6.383s
sys	0m0.551s

Terasort time:
real	6m19.218s
user	0m8.605s
sys	0m0.843s

Parameters:
mappers = 8, reducers = 4, container memory = 512
mapper JVM heapsize = 409MB, reducer JVM heapsize = 409MB

Teragen time:
real	1m0.245s
user	0m6.464s
sys	0m0.540s

Terasort time:
real	2m10.187s
user	0m8.248s
sys	0m0.687s

Parameters:
mappers = 8, reducers = 4, container memory = 2048
mapper JVM heapsize = 1638MB, reducer JVM heapsize = 1638MB

Teragen time:
real	1m3.973s
user	0m6.241s
sys	0m0.551s

Terasort time:
real	2m49.994s
user	0m8.222s
sys	0m0.677s

Parameters:
mappers = 16, reducers = 1, container memory = 512
mapper JVM heapsize = 409MB, reducer JVM heapsize = 409MB

Teragen time:
real	1m6.089s
user	0m6.349s
sys	0m0.579s

Terasort time:
real	4m23.590s
user	0m8.844s
sys	0m0.721s

Parameters:
mappers = 16, reducers = 1, container memory = 2048
mapper JVM heapsize = 1638MB, reducer JVM heapsize = 1638MB

Teragen time:
real	1m16.982s
user	0m6.399s
sys	0m0.570s

Terasort time:
real	3m47.634s
user	0m8.471s
sys	0m0.764s

Parameters:
mappers = 16, reducers = 4, container memory = 512
mapper JVM heapsize = 409MB, reducer JVM heapsize = 409MB

Teragen time:
real	1m8.966s
user	0m6.283s
sys	0m0.556s

Terasort time:
real	2m1.196s
user	0m8.400s
sys	0m0.648s

Parameters:
mappers = 16, reducers = 4, container memory = 2048
mapper JVM heapsize = 1638MB, reducer JVM heapsize = 1638MB

Teragen time:
real	1m21.993s
user	0m6.457s
sys	0m0.564s

Terasort time:
real	3m0.061s
user	0m8.488s
sys	0m0.756s

Testing loop ended on Wed Oct 17 10:44:42 UTC 2018Used a smaller file (512MB) due to storage limitations on my EC2 instances
