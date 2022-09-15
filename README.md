## Related Repositories

<table>
  <tr>
    <td colspan=2 align=center>플랫폼</td>
    <td colspan=2 align=center><a href="https://github.com/PaaS-TA/paasta-deployment">어플리케이션 플랫폼</a></td>
    <td colspan=2 align=center><a href="https://github.com/PaaS-TA/paas-ta-container-platform">컨테이너 플랫폼</a></td>
  </tr>
  <tr>
    <td colspan=2 rowspan=2 align=center>포털</td>
    <td colspan=2 align=center><a href="https://github.com/PaaS-TA/portal-deployment">AP 포털</a></td>
    <td colspan=2 align=center><a href="https://github.com/PaaS-TA/container-platform-portal-release">CP 포털</a></td>
  </tr>
  <tr align=center>
    <td colspan=4><a href="https://github.com/PaaS-TA/PaaS-TA-Monitoring">모니터링 대시보드</a></td>
  </tr>
  <tr align=center>
    <td rowspan=2 colspan=2><a href="https://github.com/PaaS-TA/monitoring-deployment">모니터링</a></td>
    <td><a href="https://github.com/PaaS-TA/PaaS-TA-Monitoring-Release">Monitoring</a></td>
    <td><a href="https://github.com/PaaS-TA/paas-ta-monitoring-logsearch-release">Logsearch</a></td>
    <td><a href="https://github.com/PaaS-TA/paas-ta-monitoring-influxdb-release">InfluxDB</a></td>
    <td><a href="https://github.com/PaaS-TA/paas-ta-monitoring-redis-release">Redis</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-PINPOINT-MONITORING-RELEASE">Pinpoint</td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-PINPOINT-MONITORING-BUILDPACK">Pinpoint Buildpack</td>
    <td></td>
    <td></td>
  </tr>
  </tr>
  <tr align=center>
    <td rowspan=4 colspan=2><a href="https://github.com/PaaS-TA/service-deployment">AP 서비스</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-CUBRID-RELEASE">Cubrid</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-API-GATEWAY-SERVICE-RELEASE">Gateway</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-GLUSTERFS-RELEASE">GlusterFS</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE">🚩 Lifecycle</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-LOGGING-SERVICE-RELEASE">Logging</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-MONGODB-SHARD-RELEASE">MongoDB</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-MYSQL-RELEASE">MySQL</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-PINPOINT-RELEASE">Pinpoint APM</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-DELIVERY-PIPELINE-RELEASE">Pipeline</a></td>
    <td align=center><a href="https://github.com/PaaS-TA/rabbitmq-release">RabbitMQ</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-ON-DEMAND-REDIS-RELEASE">Redis</a></td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-SOURCE-CONTROL-RELEASE">Source Control</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-WEB-IDE-RELEASE-NEW">WEB-IDE</a></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align=center>
    <td rowspan=1 colspan=2><a href="https://github.com/PaaS-TA/paas-ta-container-platform-deployment">CP 서비스</a></td>
    <td><a href="https://github.com/PaaS-TA/container-platform-pipeline-release">Pipeline</a></td>
    <td><a href="https://github.com/PaaS-TA/container-platform-source-control-release">Source Control</a></td>
    <td></td>
    <td></td>
  </tr>
</table>
<i>🚩 You are here.</i>



  

  


## PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE

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
    $ wget -O src.zip  https://nextcloud.paas-ta.org/index.php/s/qksWX6iygDeQRSg/download
    
    ## unzip download source files
    $ unzip src.zip 
    
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
        │   └── mariadb-10.5.17-linux-x86_64.tar.gz  
        ├── nginx  
        │   └── nginx-1.21.3.tar.gz
        ├── postgres 
        │   └── postgresql-11.17.tar.gz
        └── service-broker  
        │   └── paasta-app-lifecycle-service-broker.jar    
    ```
- Create APP Lifecycle Release
    ```
    $ cd PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE
    ## <RELEASE_TARBALL_PATH> :: release file path (e.g. /home/ubuntu/workspace/paasta-app-lifecycle-service-release.tgz) 
    $ bosh -e <bosh_name> create-release --name=paasta-app-lifecycle-service --version=1.1.1 --tarball=<RELEASE_TARBALL_PATH> --force
    ```

### PAAS-TA-APP-LIFECYCLE-SERVICE-DEPLOYMENT
- https://github.com/PaaS-TA/service-deployment/tree/master/lifecycle-service

### 참고 자료
- https://bosh.io/docs
- https://taigaio.github.io/taiga-doc/dist/

## Contributors ✨

<a href="https://github.com/PaaS-TA/PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=PaaS-TA/PAAS-TA-APP-LIFECYCLE-SERVICE-RELEASE" />
</a>
