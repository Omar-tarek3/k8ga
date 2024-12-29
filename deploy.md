- in prod k8s dir \
|__ deployment.yaml \
|__ svc.yaml \
|__ ingress.yaml


- to apply changes 
```
sudo sed -i 's|image: .*|image: gapcloudacr.azurecr.io/sales:prod-$(Build.BuildId) |g' k8s/deployment.yaml
```
- publish 

```
#update
lubectl apply -k $(System.ArtifactsDirectory)/k8s-manifest'
```
