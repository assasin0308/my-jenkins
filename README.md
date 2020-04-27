## Jenkins

### 1. installation

```json
# sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
# rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
# yum install jenkins
```

### 2. configure

```json
vim /etc/sysconfig/jenkins

## Default:     8080
## ServiceRestart: jenkins
#
# Port Jenkins is listening on.
# Set to -1 to disable
#
JENKINS_PORT="8091"

## Type:        string
## Default:     ""
## ServiceRestart: jenkins
```

### 3. start service

```json
# systemctl  start  jenkins
# systemctl daemon-reload
# systemctl restart jenkins 
# systemctl status jenkins

http://localhost:8091/ 
```

### 4. 

```json

```

### 5. 

```json

```

### 6. 

```json

```

