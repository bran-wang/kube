
kubectl create -f my-nginx-rc.yaml

kubectl get rc 

kubectl get pod --selector app=nginx --label-columns app

kubectl delete pod my-nginx-1bhpl

kubectl delete rc my-nginx
kubectl delete rc my-nginx --cascade=false

kubectl scale rc my-nginx --replicas=3
kubectl scale rc my-nginx --replicas=1


kubectl rolling-update my-nginx-v1 -f roll_udpate/my-nginx-v2.yaml --update-period=10s
```
Created my-nginx-v2
Scaling up my-nginx-v2 from 0 to 4, scaling down my-nginx-v1 from 4 to 0 (keep 4 pods available, don't exceed 5 pods)
Scaling my-nginx-v2 up to 1
Scaling my-nginx-v1 down to 3
Scaling my-nginx-v2 up to 2
Scaling my-nginx-v1 down to 2
Scaling my-nginx-v2 up to 3
Scaling my-nginx-v1 down to 1
Scaling my-nginx-v2 up to 4
Scaling my-nginx-v1 down to 0
Update succeeded. Deleting my-nginx-v1
replicationcontroller "my-nginx-v1" rolling updated to "my-nginx-v2"
```

kubectl rolling-update my-nginx-v1 -f roll_udpate/my-nginx-v2.yaml --update-period=10s --rollback


>kubernetes provider more easy update rc and pod named: Deployment

kubectl create -f deployment/my-nginx-rc.yaml 
change version
kubectl apply -f deployment/my-nginx-rc.yaml 
