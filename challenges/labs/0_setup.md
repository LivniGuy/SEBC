### Using AWS
### RHEL 7.5
### Disk space in each node atleast 30 GB:
```
34.246.185.121 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       30G  1.3G   29G   5% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.3G     0  7.3G   0% /dev/shm
tmpfs           7.3G   17M  7.3G   1% /run
tmpfs           7.3G     0  7.3G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000

34.247.51.116 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       30G  1.3G   29G   5% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.3G     0  7.3G   0% /dev/shm
tmpfs           7.3G   17M  7.3G   1% /run
tmpfs           7.3G     0  7.3G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000

18.203.88.2 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       30G  1.3G   29G   5% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.3G     0  7.3G   0% /dev/shm
tmpfs           7.3G   17M  7.3G   1% /run
tmpfs           7.3G     0  7.3G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000

34.246.198.25 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       30G  1.3G   29G   5% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.3G     0  7.3G   0% /dev/shm
tmpfs           7.3G   17M  7.3G   1% /run
tmpfs           7.3G     0  7.3G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000

52.50.220.104 | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       30G  1.3G   29G   5% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.3G     0  7.3G   0% /dev/shm
tmpfs           7.3G   17M  7.3G   1% /run
tmpfs           7.3G     0  7.3G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000
```

### yum repolist enabled output:
```
[ec2-user@ip-172-31-26-77 ~]$ yum repolist enabled
Failed to set locale, defaulting to C
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/product/rhui-client-config-server-7.crt
Repo rhui-REGION-client-config-server-7 forced skip_if_unavailable=True due to: /etc/pki/rhui/rhui-client-config-server-7.key
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-releases forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/cdn.redhat.com-chain.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/product/content-rhel7.crt
Repo rhui-REGION-rhel-server-rh-common forced skip_if_unavailable=True due to: /etc/pki/rhui/content-rhel7.key
Could not contact CDS load balancer rhui2-cds01.eu-west-1.aws.ce.redhat.com, trying others.


Could not contact any CDS load balancers: rhui2-cds01.eu-west-1.aws.ce.redhat.com, rhui2-cds02.eu-west-1.aws.ce.redhat.com.
```

### cat /etc/passwd for raffles and fullerton:
```
raffles:x:2000:2000::/home/raffles:/bin/bash
fullerton:x:3000:3000::/home/fullerton:/bin/bash
```

### cat /etc/group for hotels and shops:
```
shops:x:3001:raffles
hotels:x:3002:fullerton
```
