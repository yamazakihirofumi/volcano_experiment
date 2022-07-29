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