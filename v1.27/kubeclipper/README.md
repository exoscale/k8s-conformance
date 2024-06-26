## To reproduce:
#### Creating a cluster with KubeClipper

Step 1:Download kcctl v1.3.1.
It's recommended to install using root user.
```
curl -sfL https://oss.kubeclipper.io/kcctl.sh | KC_VERSION=master bash -
```

Step 2:Get Started With Installation.
It's recommended to install using root user, the /root/key is common key for deploy machines.
```
kcctl deploy --server 192.168.10.110,192.168.10.111,192.168.10.112 --agent 192.168.10.110,192.168.10.111,192.168.10.112 --pk-file /root/key --pkg https://oss.kubeclipper.io/release/master/kc-amd64.tar.gz
 _   __      _          _____ _ _
| | / /     | |        /  __ \ (_)
| |/ / _   _| |__   ___| /  \/ |_ _ __  _ __   ___ _ __
|    \| | | | '_ \ / _ \ |   | | | '_ \| '_ \ / _ \ '__|
| |\  \ |_| | |_) |  __/ \__/\ | | |_) | |_) |  __/ |
\_| \_/\__,_|_.__/ \___|\____/_|_| .__/| .__/ \___|_|
                                 | |   | |
                                 |_|   |_|
```

Step 3:Create Cluster With KubeClipper.
It's recommended to install using root user.
```
kcctl login -H https://localhost:8080  -u admin -p Thinkbig1
kcctl create cluster --master 192.168.10.110,192.168.10.111,192.168.10.112 --name demo --untaint-master
```

#### Deploy sonobuoy Conformance test

* Follow the conformance suite instructions to [test](https://github.com/cncf/k8s-conformance/blob/master/instructions.md) it.