### 前端使用history模式访问时nginx的配置：
[引用](https://www.jianshu.com/p/a0899ee652dd)

vue单页应用使用vue-router会有两种配置，，最主要的一点，url地址太即history模式和hash模式，但是hash模式其实会有很多限制丑了，所以我们在生产环境中也希望用到history模式。
``` bash
server {
  listen 80;
  server_name localhost;
  index index.html;
  root /root/dist;
  location / {
    root /root/dist;
    try_files $uri $uri/ /index.html =404; /这行是重点
  }
}

```

