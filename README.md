Workshop Cloud

git clone github.com/alimuamar11/Kubernetes 
cd Kubernetes

AutoScaling

$ kubectl run php-apache --image=k8s.gcr.io/hpa-example --requests=cpu=200m --expose --port=80

$ kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10

$ kubectl get hpa

Load testing
$ kubectl run -i --tty load-generator --image=busybox /bin/sh

Hit enter for command prompt

$ while true; do wget -q -O- http://php-apache.default.svc.cluster.local; done

open new terminal
$ kubectl get hpa
