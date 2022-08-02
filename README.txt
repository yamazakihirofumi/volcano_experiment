kubectl get pods --all-namespaces   # get all namespaces

$ kubectl get deploy -n {namespace}

$ kubectl delete deploy {deployment name} -n {namespace}


kubectl delete --all pods --namespace=foo

kubectl describe pod <pod name>

kubectl logs <volcano scheduler pod name> -n volcano-system
kubectl logs volcano scheduler gpu-pod1-n volcano-system
kubectl logs --namespace volcano pod/volcano-scheduler-5665cdc4d9-r82qt
## get log 
    kubectl logs pod/gpu-pod1-n

## delete pods 
    kubectl get pods -o wide 
    kubectl delete pods <name> --grace-period=0 --force

## delete service 
    kubectl delete serviceaccount -n kube-system volcano-device-plugin

## delete all pods from one namespace
    kubectl delete all --all -n {namespace (volcano-system)}

kubectl delete all --all 

## delete wrong file (Already Exist)
    kubectl delete -f <Already_EXIST.yaml>

## check on log status
    kubectl -n kube-system describe pod coredns-6d4b75cb6d-58nzg 



## Other references: 
    > find coreDns not works
        https://coredns.io/2017/04/28/coredns-for-minikube/





Your Kubernetes control-plane has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

Alternatively, if you are the root user, you can run:

  export KUBECONFIG=/etc/kubernetes/admin.conf

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join 192.168.1.110:6443 --token t9560h.od7sjozpflzb51y6 \
	--discovery-token-ca-cert-hash sha256:ca8b014276bbb7ca5c58a993472e3ffb13885d1f6d5aa64449553a587afdc55a 


$$$ Set up master node
    Execute the following command to install the calico network plugin on the cluster.
        kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
    
    