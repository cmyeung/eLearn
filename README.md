# eLearn

# The section to upload some necessary training material as my future reference

1. Section: kubernetes/example-voting-app/

   - Prerequisites:

     - Install minikube in Macbook

   - Sequence of yaml starting:

     ```
     kubectl create -f xxx.yaml
     ```

     ```
     a. voting-app-deploy.yaml
     b. voting-app-service.yaml
     c. redis-deploy.yaml
     d. redis-service.yaml
     e. postgres-deploy.yaml
     f. postgres-service.yaml
     g. worker-app-deploy.yaml
     h. result-app-deploy.yaml
     i. result-app-service.yaml
     ```

   - Start (yaml) Result:

     ```
     cmyeung@Tims-Air voting-app-kubernetes % kubectl get deployments,pods,svc
     NAME READY UP-TO-DATE AVAILABLE AGE
     deployment.apps/postgres-deploy 1/1 1 1 3m51s
     deployment.apps/redis-deploy 1/1 1 1 4m29s
     deployment.apps/result-app-deploy 1/1 1 1 95s
     deployment.apps/voting-app-deploy 1/1 1 1 6m4s
     deployment.apps/worker-app-deploy 1/1 1 1 2m11s

     NAME READY STATUS RESTARTS AGE
     pod/postgres-deploy-d9ddc956f-k464t 1/1 Running 0 3m51s
     pod/redis-deploy-744ff4944f-9h4nl 1/1 Running 0 4m29s
     pod/result-app-deploy-5bd6cd48f5-5x9v5 1/1 Running 0 95s
     pod/voting-app-deploy-85c4dc78d-hlxbg 1/1 Running 0 6m4s
     pod/worker-app-deploy-bbdd88cdd-zqvtt 1/1 Running 0 2m11s

     NAME TYPE CLUSTER-IP EXTERNAL-IP PORT(S) AGE
     service/db ClusterIP 10.99.60.108 <none> 5432/TCP 3m47s
     service/kubernetes ClusterIP 10.96.0.1 <none> 443/TCP 9m35s
     service/redis ClusterIP 10.101.84.93 <none> 6379/TCP 4m24s
     service/result-service NodePort 10.107.133.185 <none> 80:30005/TCP 89s
     service/voting-service NodePort 10.111.196.96 <none> 80:30004/TCP 5m58s
     ```

   - Start Minikube Services:

     ```
     minikube service voting-service --url
     minikube service result-service --url
     ```

2. Section: nodejs/express-app-with-fibonacci-series

   - Prerequisites:

     - Install nodemon to run the server.js

       ```
       npm install -g nodemon
       ```

   - Run the server.js

     ```
     nodemon server.js
     ```

   - loadtest

     ```
     npm install -g loadtest
     ```

     - REMEMBER NEED TO QUOTE THE LINK

     ```
      cmyeung@Tims-MacBook-Air ~ % loadtest -n 1000 -c 200 --rps 100 'http://localhost:3000/?number=20'
      [Wed Nov 30 2022 11:24:38 GMT+0800 (Hong Kong Standard Time)] INFO Requests: 0 (0%), requests per second: 0, mean latency: 0 ms
      [Wed Nov 30 2022 11:24:43 GMT+0800 (Hong Kong Standard Time)] INFO Requests: 599 (60%), requests per second: 120, mean latency: 6.5 ms
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Target URL:          http://localhost:3000/?number=20
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Max requests:        1000
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Concurrency level:   200
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Agent:               none
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Requests per second: 100
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Completed requests:  1000
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Total errors:        0
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Total time:          9.008881208 s
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Requests per second: 111
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Mean latency:        5.8 ms
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO Percentage of the requests served within a certain time
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO   50%      4 ms
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO   90%      11 ms
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO   95%      15 ms
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO   99%      25 ms
      [Wed Nov 30 2022 11:24:47 GMT+0800 (Hong Kong Standard Time)] INFO  100%      37 ms (longest request)
     ```

3. Section: blockchain



