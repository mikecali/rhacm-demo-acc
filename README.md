# RHACM-demo-acc
This repo is a demo of application deploy to OCP 4 using RHACM
The demo is created specifically for ACC Navigate project.

# Instructions

1. Deploy this application on your ACM Hub cluster
   
   oc create -f rhacm-resources/application.yml

2.  Log into RHACM’s UI and go to the ‘Application lifecycle’ tab. 
    Notice that this will create an  application called ‘mariadb-app’. 
    This deployment will create the following resources:
    
    - 1x Subscription resource associated with it.
    - 1x managed cluster that runs the application.
    - 1x Pod that runs the load itself — The MariaDB server.
