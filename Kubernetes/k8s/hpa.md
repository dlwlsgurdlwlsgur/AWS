# ./k8s/hpa.yml
```
apiVersion: autoscaling/v2beta2
kind: HorizontalPodAutoscaler
metadata:
  name: (이름 1)-hpa
  namespace: (네임스페이스 이름)
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: (이름 1)-deployment
  minReplicas: 2
  maxReplicas: 20
  metrics:
  - type: Resource
    resource:
      name: cpu
      target:
        type: Utilization
        averageUtilization: 60
---
apiVersion: autoscaling/v2beta2
kind: HorizontalPodAutoscaler
metadata:
  name: (이름 2)-hpa
  namespace: (네임스페이스)
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: (이름 2)-deployment
  minReplicas: 2
  maxReplicas: 20
  metrics:
  - type: Resource
    resource:
      name: cpu
      target:
        type: Utilization
        averageUtilization: 60
```
