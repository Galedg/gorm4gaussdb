# gorm4gaussdb

[GORM](https://gorm.io) 是一个强大的Go编程语言中的ORM库，具有简单易用、多数据库支持、自动迁移、事务支持和强大的查询功能等特点。

[云数据库 GaussDB](https://support.huaweicloud.com/gaussdb/index.html) 是华为自主创新研发的分布式关系型数据库。该产品具备企业级复杂事务混合负载能力，同时支持分布式事务，同城跨AZ部署，数据0丢失，支持1000+的扩展能力，PB级海量存储。同时拥有云上高可用，高可靠，高安全，弹性伸缩，一键部署，快速备份恢复，监控告警等关键能力。

本项目的目的是让GORM支持GaussDB数据库 [GORM适配GaussDB开源开发任务](https://developer.huaweicloud.com/programs/opensource/contributing/task-detail/0bf191f008bb4a8eb07cc428f65167f5)


## Quick Start

```go
import (
  gaussdb "github.com/okyer/gorm4gaussdb"
  "gorm.io/gorm"
)

// https://github.com/jackc/pgx
dsn := "host=localhost user=gorm password=gorm dbname=gorm port=9920 sslmode=disable TimeZone=Asia/Shanghai"
db, err := gorm.Open(gaussdb.Open(dsn), &gorm.Config{})
```

## Configuration

```go
import (
  gaussdb "github.com/okyer/gorm4gaussdb"
  "gorm.io/gorm"
)

db, err := gorm.Open(gaussdb.New(gaussdb.Config{
  DSN: "host=localhost user=gorm password=gorm dbname=gorm port=9920 sslmode=disable TimeZone=Asia/Shanghai", // data source name, refer https://github.com/jackc/pgx
  PreferSimpleProtocol: true, // disables implicit prepared statement usage. By default pgx automatically uses the extended protocol
}), &gorm.Config{})
```


Checkout [https://gorm.io](https://gorm.io) for details.



