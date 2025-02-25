1、.zip导入 function是导入函数 api是导入接口 记得选择增量导入
2、项目默认开启了swagger http://192.168.9.242:9999/v2/api-docs/magic-api/swagger2.json
3、项目swagger线上界面 http://localhost:9999/swagger-ui.html
## mysql 建表语句
```sql
CREATE TABLE `magic_api_file_v2` (
  `file_path` varchar(512) NOT NULL,
  `file_content` mediumtext,
  PRIMARY KEY (`file_path`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4
```
### 备份表建表语句
```sql
CREATE TABLE `magic_backup_record_v2` (
  `id` varchar(32) NOT NULL COMMENT '原对象ID',
  `create_date` bigint(13) NOT NULL COMMENT '备份时间',
  `tag` varchar(32) DEFAULT NULL COMMENT '标签',
  `type` varchar(32) DEFAULT NULL COMMENT '类型',
  `name` varchar(64) DEFAULT NULL COMMENT '原名称',
  `content` blob COMMENT '备份内容',
  `create_by` varchar(64) DEFAULT NULL COMMENT '操作人',
  PRIMARY KEY (`id`,`create_date`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4
```

### mock数据 例程所需数据
magic-api.sql