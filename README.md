# nginx配置
在server中添加location
```
server{
    .....
    location /api {
        include uwsgi_params;
        uwsgi_pass 127.0.0.1:8000;
    }
    .....
}
```
# uwsgi 配置
```
[uwsgi]
;项目目录
chdir=/Users/mering/projects/Questionnaire
module=Questionnaire.wsgi:application
master=true
pidfile=/tmp/project-master.pid
socket=127.0.0.1:8000
processes=5
harakiri=20
max-requests=5000
vacuum=true
;虚拟环境目录
home=/Users/mering/.py3
```