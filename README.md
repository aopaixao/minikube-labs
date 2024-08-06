# Ref

https://www.baeldung.com/ops/docker-local-images-minikube

# Criar um pod a partir da imagem da aplicação gerada
kubectl run container-nodejshelloworld --image=apaixao/nodejs_helloworld --image-pull-policy=Never --restart=Never


kubectl expose deployment container-nodejshelloworld --type=NodePort --port=3095

kubectl expose deployment apaixao/nodejs_hellworld:latest --type=NodePort --port=3095




#Ver os logs da aplicação
kubectl logs container-nodejshelloworld

#Ver os pods rodando
kubectl get pods

#Deploy da aplicação utilizando o deployment.yaml
kubectl apply -f deployment.yaml

#Criar o serviço defino no service.yaml
kubectl apply -f service.yaml

#Verificar os serviços rodando
kubectl get service

#Criando o tunnel para acesso externo à aplicação
minikube service hellokube --url


#Fazendo forward de porta
kubectl port-forward --address localhost,<YOUR_Linux_Server_IP> deployment/hello-minikube1 8080

kubectl port-forward hellokube-758b98f55-c4f6p 5000:3095

ssh -i ~/.minikube/machines/minikube/id_rsa docker@$(minikube ip) -L \*:3095:0.0.0.0:3095
ssh -i ~/.minikube/machines/minikube/id_rsa docker@$(minikube ip) -L \*:31443:0.0.0.0:31443


minikube tunnel 
kubectl expose deployment hellokube --type=LoadBalancer --port=8081


kubectl expose deployment hellokube --type=NodePort --port=8081

minikube service hellokube --url

minikube service nodejs-helloworld --url

sudo ufw allow 31443/tcp

kubectl port-forward service/hellokube 8081:8081


#Acessando a aplicação através do navegador
minikube service nodejs-helloworld 


# Delete a pod with minimal delay
kubectl delete pod nodejs-hellworld-645f78c4c8-qkgz6 --now
kubectl delete pod nodejs-hellworld-789fb88c9c-fntp4 --now

kubectl delete pods nodejs-hellworld-645f78c4c8-qkgz6,nodejs-hellworld-789fb88c9c-fntp4 --grace-period=0 --force


kubectl delete pod nodejs-hellworld-645f78c4c8-qkgz6 --force


minikube service container-nodejshelloworld --url



kubectl delete service nodejs-helloworld
