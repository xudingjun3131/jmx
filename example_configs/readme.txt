#必须先声明项目的jmx的端口，范围8501~8599
declare -A DIC_PORT
KEY=$1
DIC_PORT=([cloud-auth]="8501" [gateway]="8502" [cloud-oss]="8503" [person-auth-provider]="8504" [cloud-jsvs]="8505" [cloud-opgatew
ay]="8506" [cloud-csb]="8507" [notary-provider]="8508" [cloud-evs]="8509" [cloud-cms]="8510" [cloud-ics]="8511" [log-provider]="85
12" [crm-provider]="8513" [cloud-passport]="8514" [cloud-fee]="8515" [cloud-webapp]="8516" [cloud-ums]="8517" [project-provider]="
8518" [cloud-ecs]="8519" [message-provider]="8520" [corp-auth-provider]="8521" [cloud-link]="8522" [cloud-mobile]="8523" [cert-pro
vider]="8524" [timestamp-provider]="8525" [cloud-open]="8526" [cloud-ess]="8527" [cloud-seal]="8528")
JMX_PORT=${DIC_PORT[$KEY]}
echo $JMX_PORT


然后jmx.yaml中配置
#定义jmx监控端口范围6601~6699
  - jobname: cloud-auth
    startDelaySeconds: 0
    #hostPort: 127.0.0.1:8501
    socket: 127.0.0.1:6601
    username:
    password:
    jmxUrl: service:jmx:rmi:///jndi/rmi://127.0.0.1:8501/jmxrmi
    ssl: false
  - jobname: gateway
    startDelaySeconds: 0
    #hostPort: 127.0.0.1:8502
    socket: 127.0.0.1:6602
    username:
    password:
    jmxUrl: service:jmx:rmi:///jndi/rmi://127.0.0.1:8502/jmxrmi
    ssl: false
  - jobname: cloud-oss
    startDelaySeconds: 0
    #hostPort: 127.0.0.1:8503
    socket: 127.0.0.1:6603
    username:
    password:
    jmxUrl: service:jmx:rmi:///jndi/rmi://127.0.0.1:8503/jmxrmi
    ssl: false
  - jobname: person-auth-provider
    startDelaySeconds: 0
    #hostPort: 127.0.0.1:8504
    socket: 127.0.0.1:6604
    username:
    password:
    jmxUrl: service:jmx:rmi:///jndi/rmi://127.0.0.1:8504/jmxrmi
    ssl: false