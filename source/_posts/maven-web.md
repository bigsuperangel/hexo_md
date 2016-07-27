---
title: maven下实时编译web工程
date: 2016-07-27 11:11:38
tags: [maven,tomcat,jetty]
---

### 在pom文件build节点下加入
	<outputDirectory>${project.basedir}/src/main/webapp/WEB-INF/classes/</outputDirectory>

### web配置

1. tomcat6

```
			<!-- tomcat6插件 -->
			<plugin>
				<groupId>org.apache.tomcat.maven</groupId>
				<artifactId>tomcat6-maven-plugin</artifactId>
				<version>${tomcat.version}</version> 
				<configuration>
					<port>${webserver.port}</port>
					<path>/${project.artifactId}</path>
					<uriEncoding>${project.build.sourceEncoding}</uriEncoding>
				</configuration>
			</plugin>
```

2. tomcat7

```
			<!-- tomcat7插件 -->
			<plugin>
				<groupId>org.apache.tomcat.maven</groupId>
				<artifactId>tomcat7-maven-plugin</artifactId>
				<version>${tomcat.version}</version> 
				<configuration>
					<port>${webserver.port}</port>
					<path>/${project.artifactId}</path>
					<uriEncoding>${project.build.sourceEncoding}</uriEncoding>
				</configuration>
			</plugin>
```

3. jetty

```
			<!-- jetty插件 -->
			<plugin>
				<groupId>org.mortbay.jetty</groupId>
				<artifactId>jetty-maven-plugin</artifactId>
				<version>${jetty.version}</version>
				<configuration>
					<connectors>
						<connector implementation="org.eclipse.jetty.server.nio.SelectChannelConnector">
							<port>${webserver.port}</port>
						</connector>
					</connectors>
					<webAppConfig>
						<contextPath>/${project.artifactId}</contextPath>
					</webAppConfig>
					<systemProperties>  
						<systemProperty>
							<name>org.mortbay.util.URI.charset</name>
							<value>${project.build.sourceEncoding}</value>
						</systemProperty>
					</systemProperties>
				</configuration>
			</plugin>

```

