# PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE

## PaaS-TA APP Lifecycle Service Configuration
- app-lifecycle-server :: N machine(s)
- app-lifecycle-service-broker :: 1 machine
- mariadb :: 1 machine

## PAAS-TA-APP-LIFECYCLE-SERVICE-DEPLOYMENT
- https://github.com/PaaS-TA/PAAS-TA-APP-LIFECYCLE-SERVICE-DEPLOYMENT

## src directory
src  
    ├── app-lifecycle  
    │   ├── taiga-back-4.2.12.tar.gz  
    │   └── taiga-front-dist-4.2.12-stable.tar.gz  
    ├── common  
    │   ├── pid_utils.sh  
    │   └── syslog_utils.sh  
    ├── java  
    │   └── OpenJDK8U-jre_x64_linux_hotspot_8u212b03.tar.gz  
    ├── mariadb  
    │   └── mariadb-10.3.15-linux-x86_64.tar.gz  
    ├── nginx  
    │   └── nginx-1.16.1.tar.gz  
    └── service-broker  
    │   └── paasta-app-lifecycle-service-broker.jar    
