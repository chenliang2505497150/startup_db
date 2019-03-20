# startup_db

## 启动数据库服务

```shell
# 进入docker-compose所在目录
./docker-compose -f db.yml up -d
```

## 创建mongodb相关数据库

```shell
# mongo新建数据库，添加普通用户
docker exec -it xxxx bash
mongo
use admin;

db.auth('root','123456');

use cta;

db.createUser({
  user: 'shukun',
  pwd: '123456',
  roles: [{role: 'readWrite',db: 'cta'}]
});
```

## use mongo by url string

```shell
"mongodb://shukun:123456@local_mongo:27017/cta?authMechanism=SCRAM-SHA-1"
```
