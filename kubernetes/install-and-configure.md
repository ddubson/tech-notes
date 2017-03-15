# Configuration

* Each node in the cluster must have a time server \(NTP\) installed and running.

**RedHat**

```bash
yum install -y ntp
systemctl enable ntpd && systemctl start ntpd
```

The master has to have a path to the minion nodes:

edit /etc/hosts

```
[ip-addr] [host1]
[ip-addr] [minion1]
[ip-addr] [minion2]
```

Each node needs a docker repo path

**RedHat**

create new file `/etc/yum.repos.d/virt7-docker-common-release.repo`

with contents

```
[virt7-docker-common-release]
name=virt7-docker-common-release
baseurl=http://cbs.centos.org/repos/virt7-docker-common-release/x86_64/os/
gpgcheck=0
```

Install K8s and Docker

**Redhat**

```
yum install -y --enablerepo=virt7-docker-common-release kubernetes docker etcd
```

---

## Configuring the Master Controller

1. Edit `/etc/kubernetes/config` and modify \`KUBE\_MASTER and add \`KUBE\_ETCD\_SERVERS\` options![](/assets/kube-install-1.png)

2. Edit `/etc/etcd/etcd.conf`

	1. Modify  `ETCD_LISTEN_CLIENT_URLS` to `http://0.0.0.0:2379` in both member and cluster sections

ETCD is only run on master\*\*

3. Edit the apiserver `/etc/kubernetes/apiserver`

	1. edit KUBE\_API\_ADDRESS to `—address=0.0.0.0`

	2. edit KUBE\_API\_PORT to `—port=8080`

	3. edit KUBELET\_PORT to `—kubelet-port=10250`

4. Enable services:

```
systemctl enable etcd kube-apiserver kube-controller-manager kube-scheduler
```

5. Start services

```
systemctl start etcd kube-apiserver kube-controller-manager kube-scheduler
systemctl status etcd kube-apiserver kube-controller-manager kube-scheduler
```

---

## Configuring the Minions

1. edit `/etc/kubernetes/config`

	1. `KUBE_MASTER` to \`--master=http://centos-master:8080\`

	2. \`KUBE\_ETCD\_SERVERS\` to \`--etcd-servers=http://centos-master:2379\`

2. edit \`/etc/kubernetes/kubelet\`

	1. \`KUBELET\_ADDRESS\` to \`--address=0.0.0.0\`

	2. \`KUBELET\_PORT\` to \`—port=10250\`

	3. \`KUBELET\_HOSTNAME\` to \`--hostname-override=centos-minion1\`

	4. \`KUBELET\_API\_SERVER\` to \`--api-servers=http://centos-master:8080\`

	5. KUBELETE\_POD\_INFRA\_CONTAINER commented out

3. \`systemctl enable kube-proxy kubelet docker\`

4. \`systemctl start kube-proxy kubelet docker\`

5. \`systemctl status kube-proxy kubelet docker\` -&gt; grep for 3 running services

6. verify docker - \`docker pull hello-world && docker run hello-world\`

---

## Exploring Environment

* `kubectl` is the main utility \(man kubectl-get\)

* list of nodes that have registered themselves with the master - `kubectl get nodes`

```
kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="ExternalIP")].address}'
```



