# RHACM-demo-acc
This repo is a demo of application deploy to OCP 4 using RHACM
The demo is created specifically for ACC Navigate project.

# Instructions

## Deploy applications
1. Deploy this application on your ACM Hub cluster
   
   oc create -f rhacm-resources/application.yml

2.  Log into RHACM’s UI and go to the ‘Application lifecycle’ tab. 
    Notice that this will create an  application called ‘mariadb-app’. 
    This deployment will create the following resources:
    
    - 1x Subscription resource associated with it.
    - 1x managed cluster that runs the application.
    - 1x Pod that runs the load itself — The MariaDB server.

## Policies
1. To demonstrate RHACM policy, We are going to create a Role policy and a RoleBinding policy in order to maintain an RBAC strategy in our clusters
   
   oc apply -f rhacm-policy/role-policy/role-policy.yml
   oc apply -f rhacm-policy/role-binding/role-binding-policy.yml

2. To demonstrate RHACM policy to enforce resource limits to a selected namespace, do the following.
   
   oc apply -f rhacm-policy/memory-limits-ranges/rhacm-policy-limits-ranges.yaml

   This will enable a policy that will check all namespaces for violations excluding namespaces that starts with kube-* and openshift-*.


   
