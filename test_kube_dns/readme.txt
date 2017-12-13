Service解决了Pod的服务发现和负载均衡问题

kube-dns可以解决Service的发现问题
k8s将Service的名称当做域名注册到kube-dns中，通过Service的名称就可以访问其提供的服务。

在POD里面可以通过Service的名字访问service的服务
root@k8s-master-0-276edc70-524e-414e-a913-150607184c02:~# kubectl exec jenkins-5ftk4 -- curl -s my-nginx:80
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>