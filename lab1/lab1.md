## lab1

1-Add bitnami helm chart repository in the controlplane node.
```
   helm repo add bitnami https://charts.bitnami.com/bitnami
   helm repo list
```
<img src="https://user-images.githubusercontent.com/92440274/218346505-7a80c605-9f5f-490b-a74e-5349b6370a54.png">

2-Deploy the Apache application on the cluster using the apache from the bitnami repository.
Set the release Name to: amaze-surf

```
   helm install my-release bitnami/apache  
   kubectl get all
   
```
<img src="https://user-images.githubusercontent.com/92440274/218346688-72abbcd7-c021-479f-808f-7ef477692cdf.png">

3-Uninstall the apache chart release  from the cluster.

```
  helm delete my-release
```
<img src="https://user-images.githubusercontent.com/92440274/218346836-03653c81-8daf-42b1-ae8b-edc2fe6bfb95.png">

4- install specfic version of nginx 1.22.0, then update it to specfic 1.23.1 ,then rollback

```
  helm search repo nginx –versions
  helm install my-release bitnami/nginx --version 12.0.1
```

<img src="https://user-images.githubusercontent.com/92440274/218346986-7e28c978-ea0c-48da-9893-87104a940713.png">
<img src="https://user-images.githubusercontent.com/92440274/218347034-cc31f413-e878-45b7-af9a-7e02825a54a2.png">

```
   helm upgrade  my-release bitnami/nginx --version 13.1.3
   helm ls -a
```
<img src="https://user-images.githubusercontent.com/92440274/218347335-e051eac2-e222-4f78-bd7f-c473b9c5df4a.png">

```
  helm rollback my-release
```
<img src="https://user-images.githubusercontent.com/92440274/218347428-91e131ff-d413-46a9-8e49-f58b742387c0.png">



