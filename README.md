## Jenkins

### 1. installation

```json
https://www.cnblogs.com/mmzs/p/12092982.html

# sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
# rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
# yum install jenkins
```

### 2. configure

```json
vim /etc/sysconfig/jenkins # 暂不做修改
```

### 3. start service

```json
# systemctl  start  jenkins
# systemctl daemon-reload
# systemctl restart jenkins 
# systemctl status jenkins


http://localhost:8080/ 
# 出现 Please wait while Jenkins is getting ready to work...  
# 修改: 
vim /var/lib/jenkins/hudson.model.UpdateCenter.xml
# <url>http://updates.jenkins.io/update-center.json</url> 将https改为http
# 其他国内备用地址（也可以选择使用）：
https://mirrors.tuna.tsinghua.edu.cn/jenkins/updates/update-center.json
http://mirror.esuni.jp/jenkins/updates/update-center.json
# 重启服务
```

### 4. 反向代理

```json

server {
    listen       83;
    server_name  localhost;
    #access_log /var/log/jenkins_access_log main;
    #error_log  /var/log/jenkins_error_log  debug_http;
    client_max_body_size 60M;
    client_body_buffer_size 512k;
    location / {
        proxy_pass      http://127.0.0.1:8080/;
        proxy_redirect  off;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
     }
}
```

### 5. 

```json

```

### 6. 

```json

```

