# k8s-nextcloud

Deploy Nextcloud on minikube or any other Kubernetes clusters. Uses ngrok to make the Nextcloud instance accessible externally.

## Setup and Prerequisites

* Login to [Ngrok](https://ngrok.com/) and create a free account and copy your authtoken. Subscription required if you want static URLs.
* Replace <NGROK_AUTHTOKEN> with your token on ngrok-deployment.yaml
* Replace below variables with your own values on nextcloud-deployment.yml and mariadb-deployment.yml
  * <MYSQL_ROOT_PASSWORD>
  * <NEXTCLOUD_ADMIN_PASSWORD>

## Deployment

```bash
#Create kubernetes deployments and services

kubectl create -f mariadb-deployment.yml,mariadb-service.yml,nextcloud-deployment.yml,nextcloud-service.yml,ngrok-deployment.yml,ngrok-service.yml,redis-deployment.yml,redis-service.yml

#Done!
```
Open your [Ngrok Dashboard](https://dashboard.ngrok.com/endpoints/status) to find your current URL and open it. Login using admin/<NEXTCLOUD_ADMIN_PASSWORD>.
