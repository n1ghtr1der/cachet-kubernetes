# Cachet Kubernetes 

## About
This Project is a Kubernetes version of Cachet Status Page Tool.

The focus of this project is to study/practice Kubernetes and also provide another way to implement Cachet. This Project implements Cachet only, you'll have to create your database however you want and integrate with Cachet.

## Prerequirements
- A Kubernetes cluster such as KIND, K3S or Minikube.
- Kubectl cli.

## Running the service
### 1. Setting up the ConfigMap 
- Once your database is up and running, fill the informations in cachet-configmap.yaml. Dont worry about the APP_KEY field, this will be discussed later in this tutorial.
    ```yaml
    DB_DRIVER: 
    DB_HOST: 
    DB_PORT: 
    DB_DATABASE: 
    DB_USERNAME: 
    DB_PASSWORD: 
    DB_PREFIX: chq_
    APP_KEY: 
    APP_LOG: errorlog
    APP_ENV: production
    APP_DEBUG: "false"
    ```
    If you want to insert more env variables, you can check all the existent ones in the official [documentation](https://docs.cachethq.io/installation/guide.html#configuring-a-database)
### 2. Running the application 
- After putting your db info in cachet-configmap.yaml, let's start the application.
    ```bash
    kubectl create -f cachet-service.yaml,cachet-configmap.yaml,cachet-deployment.yaml
    ```

### 3. Checking the application (TODO) 
