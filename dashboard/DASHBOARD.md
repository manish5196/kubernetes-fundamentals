#### Dashboard Setup
>https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/ 

#### Setup the dashboard adming user
>https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md


#### Long Live Dashboard token
>eyJhbGciOiJSUzI1NiIsImtpZCI6ImM5aUhzODBOU2l6STJrSmJOSGtpXy1EQ0h3dmVPM3F5NnR1d3lLel9aTFEifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJrdWJlcm5ldGVzLWRhc2hib2FyZCIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJhZG1pbi11c2VyIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImFkbWluLXVzZXIiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiJmYTFlZTljOC0zMzg1LTQ2Y2MtYTJkNy01NTc3Y2JkZjYwMGQiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6a3ViZXJuZXRlcy1kYXNoYm9hcmQ6YWRtaW4tdXNlciJ9.U2jjr2ypI74qZjxe8uCIEoJhTeDu63OpMVg0rr0htV7LxjRadAD-L8s72ILiWvDNnBEePq25hJ11BDEDz_ei2u_hZHm0KrSXufJifc1nBhrCcphIT7zIw7-CXmD6w76Uq--Fc8gcFfjbCa3ElWiA0GMQ6Cai9S7mMjm7t1YELxNwlZm9EXsUpHHGRbiCyfVVChvBq_6rmvoca5-VEnq3OzcbCb8gCaUsGX-4IttmeW0c9XRPtAysTMSlkn1E6dydECVvlyL75rdvXQksZskTHOJ40AC4Y_lyRV9Nz8_4VnfRxtsCHIoByhIMT8MYzjyZt3wMb2LeFncPhm7JkpbqMA


#### Step to run and create token of dashboard

#### Step-1 
> kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

#### Step-2
>kubectl proxy

#### Step-3
>kubectl apply -f dashboard-adminuser.yaml

#### Step-4
>kubectl apply -f dashboard-cluster-role-binding.yaml

#### Step-5
>kubectl apply -f dashboard-adminuser-token.yaml 

#### Step-6
>kubectl get secret admin-user -n kubernetes-dashboard -o jsonpath={".data.token"} | base64 -d