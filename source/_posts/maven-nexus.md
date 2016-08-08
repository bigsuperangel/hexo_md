---
title: maven 私服 nexus 搭建
date: 2016-08-04 10:38:08
tags: [maven,nexus,java]
---

1. 安装[nexus](http://www.sonatype.com/download-oss-sonatype),可下载sh版，直接运行可根据提示完成配置，适合初学者

2. 配置maven中settings.xml文件的servers节点，可以发布jar包到nexus

    <server>
      <id>nexus-releases</id>
      <username>admin</username>
      <password>admin123</password>
    </server>
   
    <server>
      <id>nexus-snapshots</id>
      <username>admin</username>
      <password>admin123</password>
    </server>

３. 配置pom.xml文件

	<repositories>
		<!-- 私服 -->
		<repository>
			<id>nexus-repos</id>
			<name>maven-public</name>
			<url>http://192.168.0.114:8081/repository/maven-public/</url>
			<snapshots>
				<enabled>true</enabled>
			</snapshots>
			<releases>
				<enabled>true</enabled>
			</releases>
		</repository>
		
	</repositories>

	<pluginRepositories>
		<pluginRepository>
			<id>nexus-repos</id>
			<name>maven-public</name>
			<url>http://192.168.0.114:8081/repository/maven-public/</url>
			<releases>
				<enabled>true</enabled>
			</releases>
			<snapshots>
				<enabled>false</enabled>
			</snapshots>
		</pluginRepository>
	</pluginRepositories>

    <distributionManagement>
        <repository>
            <id>nexus-releases</id>
            <name>maven-releases</name>
            <url>http://192.168.0.114:8081/repository/maven-releases/</url>
        </repository>
        <snapshotRepository>
            <id>nexus-snapshots</id>
            <name>maven-snapshots</name>
            <url>http://192.168.0.114:8081/repository/maven-snapshots/</url>
        </snapshotRepository>
    </distributionManagement>

