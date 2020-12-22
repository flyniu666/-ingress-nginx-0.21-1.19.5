BUILD:
```bash

cd images/nginx/
make
cd  -
cd images/e2e/
make
cd -
e2e_tag=`docker images|grep e2e|awk {'print  $2'}`
sed -i "s/e2e:11111111/e2e:$e2e_tag/" build/go-in-docker.sh
make


echo -e '\n\n\n\n\n'
docker images|grep  ingress-nginx
```
