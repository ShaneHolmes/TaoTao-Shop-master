# 淘淘商城项目开发过程（Eclipse）
* * *
## 1 maven工程搭建
### 1.1 .m2文件
	用提供的.m2文件夹将C:\Users\47463\.m2**文件覆盖**
### 1.2 创建父类工程
	在eclipse中创建Maven项目，**勾选Create a simple project**-->next-->GroupId:com.taotao;Artifact Id:taotao-parent;
	Version:0.0.1-SNAPSHOT;在**Packaging中选择pom**（所有子项目的父工程）-->完成。在taotao-parent项目下**修改pom.xml**
	文件：点击文本编辑框下面的pom.xml。添加后详情见项目中文件
### 1.3 创建一个common工程
	该工程有很多共有的代码，需要继承taotao-parent工程。在eclipse中创建Maven项目，勾选Create a simple project-->next-- 
	>GroupId:com.taotao;Artifact Id:taotao-common;Version:0.0.1-SNAPSHOT;在Packaging:jar）-->在Parent Projrct里面：
	Group Id:**com.taotao**;Artifact Id:**taotao-parent**;Version:0.0.1-SNAPSHOT-->完成。在taotao-parent项目下修改
	pom.xml文件：点击文本编辑框下面的pom.xml。添加后：详情见项目中文件

### 1.4 创建一个聚合工程taotao-manager
	在eclipse中创建Maven项目，勾选Create a simple project-->next-->GroupId:com.taotao;Artifact Id:taotao-manager;
	Version:0.0.1-SNAPSHOT;在Packaging:pom）-->在Parent Projrct里面：Group Id:**com.taotao**;Artifact Id:taotao-parent# 淘淘商城项目开发过程（Eclipse）
* * *
## 1.maven工程搭建
### 1.1 .m2文件
	用提供的.m2文件夹将C:\Users\47463\.m2**文件覆盖**
### 1.2 创建父类工程
	在eclipse中创建Maven项目，**勾选Create a simple project**-->next-->GroupId:com.taotao;Artifact Id:taotao-parent;
	Version:0.0.1-SNAPSHOT;在**Packaging中选择pom**（所有子项目的父工程）-->完成。在taotao-parent项目下**修改pom.xml**
	文件：点击文本编辑框下面的pom.xml。添加后详情见项目中文件
### 1.3 创建一个common工程
	该工程有很多共有的代码，需要继承taotao-parent工程。在eclipse中创建Maven项目，勾选Create a simple project-->next-- 
	>GroupId:com.taotao;Artifact Id:taotao-common;Version:0.0.1-SNAPSHOT;在Packaging:jar）-->在Parent Projrct里面：
	Group Id:**com.taotao**;Artifact Id:**taotao-parent**;Version:0.0.1-SNAPSHOT-->完成。在taotao-parent项目下修改
	pom.xml文件：点击文本编辑框下面的pom.xml。添加后：详情见项目中文件

### 1.4 创建一个聚合工程taotao-manager
	在eclipse中创建Maven项目，勾选Create a simple project-->next-->GroupId:com.taotao;Artifact Id:taotao-manager;
	Version:0.0.1-SNAPSHOT;在Packaging:pom）-->在Parent Projrct里面：Group Id:**com.taotao**;Artifact Id:taotao-parent
	Version:0.0.1-SNAPSHOT-->完成。在taotao-parent项目下修改pom.xml文件：点击文本编辑框下面的pom.xml。添加后：详情见项目中文
	件(pom工程)该聚合工程包括以下包：
#### 1.4.1 taotao-manager-pojo(jar包)
	点击taotao-manager**项目右键**，创建Maven项目，选择**Maven Module**勾选Create a simple project-->Module Name：taotao
	-manager-pojo-->下一步-->jar-->完成。**taotao-manager项目下出现文件夹：taotao-manager-pojo；pom.xml文件中有相应的模块;
	删除该文件夹则taotao-manager-pojomodule也将一并删除，同一个文件夹的不同展示**taotao-manager-pojo中pom.xml不需要修改（不
	依赖任何jar包）
#### 1.4.2 taotao-manager-mapper(jar包）
	同taotao-manager-pojo。但需要修改pom.xml
#### 1.4.3 taotao-manager-service(jar包)
	taotao-manager-pojo.但需要修改pom.xml
#### 1.4.4 taotao-manager-web(controller)(war包)（最后聚合到war包里面）
	Packaging选择war.需要在src/main/webapp下创建/WEB-INF/web.xml
### 1.5 运行（运行taotao-manager工程）
	在taotao-manager工程的pom.xml中配置tomcat插件.点击taotao-manager项目右键，run as选第二个，在Goals输入：clean tomcat7
	.run出现错误找不到parent。在taotao-parent项目点击右键，run as-->Maven install(将taotao-parent安装到本地仓库);在taotao
	-common项目点击右键，run as-->Maven install(将taotao-common安装到本地仓库。运行taotao-manager工程，在浏览器输入http://
	localhost:8080/ 即可访问。

	Version:0.0.1-SNAPSHOT-->完成。在taotao-parent项目下修改pom.xml文件：点击文本编辑框下面的pom.xml。添加后：详情见项目中文
	件(pom工程)该聚合工程包括以下包：
#### 1.4.1 taotao-manager-pojo(jar包)
	点击taotao-manager**项目右键**，创建Maven项目，选择**Maven Module**勾选Create a simple project-->Module Name：taotao
	-manager-pojo-->下一步-->jar-->完成。**taotao-manager项目下出现文件夹：taotao-manager-pojo；pom.xml文件中有相应的模块;
	删除该文件夹则taotao-manager-pojomodule也将一并删除，同一个文件夹的不同展示**taotao-manager-pojo中pom.xml不需要修改（不
	依赖任何jar包）
#### 1.4.2 taotao-manager-mapper(jar包）
	同taotao-manager-pojo。但需要修改pom.xml
#### 1.4.3 taotao-manager-service(jar包)
	taotao-manager-pojo.但需要修改pom.xml
#### 1.4.4 taotao-manager-web(controller)(war包)（最后聚合到war包里面）
	Packaging选择war.需要在src/main/webapp下创建/WEB-INF/web.xml
### 1.5 运行（运行taotao-manager工程）
	在taotao-manager工程的pom.xml中配置tomcat插件.点击taotao-manager项目右键，run as选第二个，在Goals输入：clean tomcat7
	.run出现错误找不到parent。在taotao-parent项目点击右键，run as-->Maven install(将taotao-parent安装到本地仓库);在taotao
	-common项目点击右键，run as-->Maven install(将taotao-common安装到本地仓库。运行taotao-manager工程，      在浏览器输入 http://localhost:8080/ 即可访问。

### 1.6 问题
- 	关闭Eclipse重启之后，项目taotao-manager-mapper(pojo,service,web)出现找不到资源的错误。解决方案：将项目重新Maven install。

## 2 导入逆向工程
	import-->general-->现有项目到工作空间-->generatorSqlmapCustom(复制项目)-->完成.修改数据库相关配置（用户名密码），在GeneratorSqlmap中运行main().
## 3 SSM框架整合
### 3.1 整合思路
- [ ] **Dao层**：使用mybatis框架
1.创建SqlMapConfig.xml文件
2.applicationContext-dao.xml文件（1.配置数据源。2.需要让spring容器管理SessionFactory，单例存在。3.把mapper的代理对象放到spring容器中使用扫描包的方式加载mapper的代理对象）
- [ ] **Service层**：
1.事务管理。
2.需要把service实现对象放到spring容器中管理
- [ ] **表现层**：
1.配置注释驱动
2.配置视图解析器
3.需要扫描controller
- [ ]** web.xml**
1.spring容器的配置
2.Springmvc前端控制器的配置
3.Post乱码过滤器
	
