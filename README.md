clone as docker_nginx_phpfpm_laravel_aeb

cd docker_nginx_phpfpm_laravel_aeb

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
```
docker-compose up -d
```

View laravel demo http://localhost/

### Deploy to Elastic Beanstalk
Push your docker container to repository
```
docker push dmitriyr/docker_nginx_phpfpm_laravel_aeb
```

Create New Environment with Multi-container Docker. 
upload release from repo/
