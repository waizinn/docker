# Apache PHP Redis MySQL
[![GitHub version](https://badge.fury.io/gh/cgarde89%2Fdocker-apache-php-redis-mysql.svg)](https://badge.fury.io/gh/cgarde89%2Fdocker-apache-php-redis-mysql)

Docker runing Apache PHP-FPM, Redis and MySQL

### Images used

- [httpd](https://hub.docker.com/layers/httpd/library/httpd/2.4.41-alpine/images/sha256-4df91a8788e987e74b16b02e328b204fc1fe8329143dc249be7e37d330277ba1)
- [PHP-FPM](https://hub.docker.com/layers/php/library/php/7.4.5-fpm-alpine/images/sha256-797c1e43838377697511f3ac06e1ae741f257f89f2ede06da37e647dd6d05ccb)
- [Redis](https://hub.docker.com/layers/redis/library/redis/5.0.7-alpine/images/sha256-166c09afbde11b339de35a8a894556584a17e21256ca7dd8a60c879fcda8fb1d)
- [MySQL](https://hub.docker.com/layers/mysql/library/mysql/8/images/sha256-09de7b17af0c17d397e6b69ff841756b80074aed00c1e91d7bc0f3caa5512113)
- [Generate Certificate](https://hub.docker.com/r/jacoelho/generate-certificate)

The project use the following ports:

| **Server** | **Port** |
| ---------- | --------: |
| MySQL      | 3360     |
| PHP | 9090 |
| Apache | 80 |
| Apache SSL | 443 |
| Redis | 6379 |

#### Configure Apache With SSL Certificates

Generate SSL certificates

```bash
source .env && docker run --rm -v ./etc/infrastructure/ssl:/certificates -e "SERVER=$APACHE_HOST" jacoelho/generate-certificate
```

