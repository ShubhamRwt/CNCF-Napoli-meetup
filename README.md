## Steps to execute the Demo
 
 ### 1. First step is to deploy the Strimzi operator

     kubectl create -f 'https://strimzi.io/install/latest?namespace=myproject' -n myproject

 ### 2. Now once the operator is Ready, you should deploy the Kafka custom resource named `kafkaTLS.yaml`.

     kubectl create -f kafkaTls.yaml -n my project

### 3. Once your Kafka Cluster is deployed, you can apply the `user` and `topic` custom resource.

*    For user

      ```sh
       kubectl create -f user.yaml -n myproject
      ```

*    For topic

      ```sh
       kubectl create -f topic.yaml -n myproject
      ```


### 4. After the above steps are performed, you can now apply the consumer and producer deployment files.
    
*    For consumer
    
     ```sh
      kubectl create -f consumer.yaml -n myproject
     ```

*    For producer

     ```sh
      kubectl create -f hello-world.yaml -n myproject
     ```

And then you can check the logs of the consumer to see that the messages producers are getting consumed by the consumer
