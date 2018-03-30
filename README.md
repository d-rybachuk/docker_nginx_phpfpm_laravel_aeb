### Docker + Nginx + php-fpm + deploy on Amazon Elastic Beanstalk


### File structure

```
.
├── my-app (Laravel demo inside)
|   └── Dockerfile
├── proxy
│   └── conf.d
│       └── default.conf
├── Dockerrun.aws.json
└── README.md
```

### Development

clone this repo as docker_nginx_phpfpm_laravel_aeb

cd docker_nginx_phpfpm_laravel_aeb

```
docker-compose up -d
```

View laravel demo http://localhost/

### Deploy to Elastic Beanstalk
Push your docker container to docker repository (in this example i used https://hub.docker.com/ and my repo dmitriyr)

For pushing you should docker login first
```
docker login dmitriyr
```

```
docker push dmitriyr/docker_nginx_phpfpm_laravel_aeb
```

make zip from inside docker_nginx_phpfpm_laravel_aeb folder (there is issue with .zip from github release folder, not sutable for uploading to Amazon EB )
```
zip -r docker_nginx_phpfpm_laravel_aeb.zip Dockerrun.aws.json  my-app  proxy  README.md 
```

Create New Environment with Multi-container Docker and upload your docker_nginx_phpfpm_laravel_aeb


