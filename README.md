# PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE

### PaaS-TA APP Lifecycle Service Configuration
- app-lifecycle-server :: N machine(s)
- app-lifecycle-service-broker :: 1 machine
- mariadb :: 1 machine

### Create PaaS-TA APP Lifecycle Service Release
- Download the latest APP Lifecycle Release
    ```
    $ git clone https://github.com/PaaS-TA/PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE.git
    ```
- Download & Copy "source files" into the src directory
    ```
    ## download source files
    $ wget -O source-files.zip http://45.248.73.44/index.php/s/NeEBb9nAQdRQR4F/download
    
    ## unzip download source files
    $ unzip source-files.zip -d <src dircetory path>/
    
    ## final src directory
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
    ```
- Create APP Lifecycle Release
    ```
    $ cd PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE
    ## <RELEASE_TARBALL_PATH> :: release file path (e.g. /home/ubuntu/workspace/paasta-app-lifecycle-service-release.tgz) 
    $ bosh -e <bosh_name> create-release --name=paasta-app-lifecycle-service --version=1.0 --tarball=<RELEASE_TARBALL_PATH> --force
    ```

### PAAS-TA-APP-LIFECYCLE-SERVICE-DEPLOYMENT
- https://github.com/PaaS-TA/PAAS-TA-APP-LIFECYCLE-SERVICE-DEPLOYMENT

### 참고 자료
- https://bosh.io/docs
- https://taigaio.github.io/taiga-doc/dist/
