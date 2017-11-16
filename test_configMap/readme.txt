
kubectl exec `kubectl get pods -l run=my-nginx  -o=name|cut -d "/" -f2` env|grep log_level

kubectl edit configmap special-config

kubectl exec `kubectl get pods -l run=my-nginx  -o=name|cut -d "/" -f2` cat /etc/config/log_level


about 20s volume config_map value will change after we edit configmap.

env config map will not change the value

