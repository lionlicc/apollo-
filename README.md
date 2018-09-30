# apollo-dbencrypt
开源框架Apollo提供的数据库配置是明文连接了，生产一般都需要加密，需要做细微的修改！

---
* **下载jasypt**
  * https://mvnrepository.com/artifact/org.jasypt/jasypt/1.9.2

* **加密密码**
  * java -cp *jasypt的路径* org.jasypt.intf.cli.JasyptPBEStringEncryptionCLI input=*密码* password=*随便填（字母数字）* algorithm=PBEWithMD5AndDES  
 
* **增加jasypt-spring-boot-starter依赖**
  *  Apollo1.0.0中spring-boot的版本是1.3.8，jasypt-spring-boot-starter的版本不宜太高，1.7版本可以已在uat测试过了
  *  apollo-configservice、apollo-adminservice 、apollo-portal需要增加此依赖，其余的不用。
 ```
 <dependency>
		<groupId>com.github.ulisesbocchio</groupId>
		<artifactId>jasypt-spring-boot-starter</artifactId>
		<version>1.7</version>
 </dependency>
 ```

* **修改application-github.properties**
 ```
spring.datasource.url = datasource_url
spring.datasource.username = datasource_username
spring.datasource.password = ENC(密文)
jasypt.encryptor.password=和命令里password的值一样
 ```
