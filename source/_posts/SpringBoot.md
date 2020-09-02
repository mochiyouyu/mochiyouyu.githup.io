---
title: SpringBoot
date: 2020-09-02 21:01:13
tags:
---
## Spring Boot项目中需要注意的细节

### mapper中xml文件的配置 

``` xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN" "http://mybatis.org/dtd/mybatis-3-mapper.dtd" >
<mapper namespace="com.zzu.demo.mapper.UserMapper">

    <select id="getInfo" parameterType="String" resultType="com.zzu.demo.entity.User">
        SELECT * FROM user WHERE loginName = #{loginName} AND loginPwd = #{loginPwd}
    </select>

</mapper>
```
##### 注意：
mapper中的接口名称与xml文件对应的命名必须一致

### 主程序中问题

```
主程序中必须加上
@MapperScan(value = "com.zzu.demo.mapper")
才能够扫描到mapper文件夹中的接口
```

### 数据库连接中的问题
```yaml
spring:
  datasource:
    name: test  #数据库名
    url: jdbc:mysql://localhost:3306/mybatis?useUnicode=true&characterEncoding=utf-8&serverTimezone=Asia/Shanghai #url
    username: root  #用户名
    password: 123456  #密码
    driver-class-name: com.mysql.jdbc.Driver  #数据库链接驱动


mybatis:
  mapper-locations: classpath:mybatis/mapper/*.xml  #配置映射文件
  type-aliases-package: com.zzu.demo.entity #配置实体类

```
注意：
时区问题，不写会报错



