# EKS-nginx-ingress-controller-movieapp-nodejs

#kubectl install

$ curl -LO https://dl.k8s.io/release/v1.28.3/bin/linux/amd64/kubectl
$ chmod +x kubectl
$ sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
#helm install

$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
$ chmod 700 get_helm.sh
$ ./get_helm.sh
$ helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
$ helm upgrade -i ingress-nginx ingress-nginx/ingress-nginx \
    --version 4.2.3 \
    --namespace kube-system \
    --set controller.service.type=LoadBalancer
#nginx-ingress-controller deployment

$ kubectl -n kube-system rollout status deployment ingress-nginx-controller
$ kubectl get deployment -n kube-system ingress-nginx-controller
$ kubectl create namespace apps
$ kubectl apply -f bollywoodservice.yml -f hollywoodservice.yml -f tollywoodservice.yml
$ kubectl apply -f ingress.yml
