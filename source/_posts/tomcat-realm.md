---
title: tomcat设置realm
date: 2016-06-27 14:31:31
tags: [tomcat,mysql,realm]
---

### 一、server.xml
- 设置全局resource

```
<GlobalNamingResources>

	<Resource name="hd_jndi" auth="Container" type="javax.sql.DataSource"
		maxTotal="100" maxIdle="30" maxWaitMillis="10000"
		username="root" password="login" driverClassName="com.mysql.jdbc.Driver"
		url="jdbc:mysql://192.168.0.114:3306/fss?useUnicode=true&amp;characterEncoding=UTF-8"/>
</GlobalNamingResources>
```

- 在Engine下面加入realm结点

```
<Realm className="org.apache.catalina.realm.DataSourceRealm"
	dataSourceName="hd_jndi"
	userTable="v_account_password" userNameCol="account" userCredCol="password"  
	userRoleTable="v_user_role" roleNameCol="role_name"/> 
```

### 二、context.xml
- 在context中引用全局resource

```
<ResourceLink global="hd_jndi" name="hd_jndi" type="javax.sql.DataSource" />  
```

### 三、servlet-api 与 jsp-api 与tomcat冲突
- 在context节点下加入 

```
<Loader delegate="true"></Loader>  
```


