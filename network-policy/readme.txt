
kubectl run web --image=nginx --labels app=web,env=prod --expose --port 80


$ kubectl run --rm -i -t --image=alpine test-$RANDOM -- sh
/ # wget -qO- http://web
<!DOCTYPE html>
<html>
<head>


kubectl apply -f web-deny-all.yaml


$ kubectl run --rm -i -t --image=alpine test-$RANDOM -- sh
/ # wget -qO- --timeout=2 http://web
wget: download timed out


kubectl delete deploy web
kubectl delete service web
kubectl delete networkpolicy web-deny-all

