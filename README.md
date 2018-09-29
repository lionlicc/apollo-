# apollo-dbencrypt
集中配置开源框架apollo提供的数据库配置是明文连接了，生产一般都需要加密，需要做细微的修改！

### 以apollo-configservice为列
#### 1、下载jasypt
https://mvnrepository.com/artifact/org.jasypt/jasypt/1.9.2

#### 2、增加jasypt-spring-boot-starter依赖
 ```
 <dependency>
		<groupId>com.github.ulisesbocchio</groupId>
		<artifactId>jasypt-spring-boot-starter</artifactId>
		<version>1.7</version>
 </dependency>
 ```
