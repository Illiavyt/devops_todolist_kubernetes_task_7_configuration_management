# Створи ресурси у Kubernetes:
kubectl apply -f configMap.yml
kubectl apply -f secret.yml
kubectl apply -f deployment.yml

# Перевір створені ресурси
kubectl get configmap
kubectl get secret
kubectl get deployment
kubectl get pods

# Перевір змінні середовища в поді
# Отримай ім’я поду:
kubectl get pods

# Перевір, що змінні застосувались:
kubectl exec -it <pod-name> -- printenv | grep -E 'PYTHONUNBUFFERED|SECRET_KEY'

# Перевір роботу застосунку
# Проглянь логи:
kubectl logs <pod-name>

# Або пробрось порт:
kubectl port-forward <pod-name> 8000:8000

# Відкрий у браузері:
http://localhost:8000/

# Очистка після перевірки
kubectl delete -f deployment.yml
kubectl delete -f configMap.yml
kubectl delete -f secret.yml