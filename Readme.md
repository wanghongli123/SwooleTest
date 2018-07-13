#### 所需环境(基于Mac)
###### 安装Docker, (Mac Docker 教程：https://blog.csdn.net/jiang_xinxing/article/details/58025417)
###### 安装wrk, (wrk 教程：https://www.restran.net/2016/09/27/wrk-http-benchmark/)

####启动整个程序的方法：
```
1.git clone https://github.com/wanghongli123/SwooleTest.git

2.cd SwooleTest/laravelapp && composer install

3.cd ../deploy && docker-compose up -d

4.docker exec -it deploy_php_1 /bin/sh 进入 php docker 后，cd ../app && php artisan laravels start(启动swoole)
```

