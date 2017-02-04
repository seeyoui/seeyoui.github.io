---
title: kensite基础开发步骤
layout: post
guid: urn:uuid:6762f91f-7e36-42ea-84d3-4e882a2298eb
tags:
  - work
  - kensite
---

### 5分钟开发一个基础模块

#### 1.创建业务表  
![创建业务表](/media/files/2017/02/04/develop1.png)  

#### 2.创建数据库字段  
![创建数据库字段](/media/files/2017/02/04/develop2.png)  

#### 3.配置数据库字段  
> 单行输入框
![配置数据库字段](/media/files/2017/02/04/develop31.png)
数值输入框
![配置数据库字段](/media/files/2017/02/04/develop32.png)
下拉列表框
![配置数据库字段](/media/files/2017/02/04/develop33.png)
单选按钮组
![配置数据库字段](/media/files/2017/02/04/develop34.png)
复选框
![配置数据库字段](/media/files/2017/02/04/develop35.png)
日期选择框
![配置数据库字段](/media/files/2017/02/04/develop36.png)
多行输入框
![配置数据库字段](/media/files/2017/02/04/develop37.png)
下拉选择树
![配置数据库字段](/media/files/2017/02/04/develop38.png)
html富文本编辑器
![配置数据库字段](/media/files/2017/02/04/develop39.png)
扩展选择按钮
![配置数据库字段](/media/files/2017/02/04/develop30.png)

#### 4.修改代码生成器配置文件  
> 配置文件位置**src/test/java/generator.xml**  


```xml
<?xml version="1.0" encoding="GBK"?>
<!DOCTYPE properties SYSTEM "http://java.sun.com/dtd/properties.dtd">
<properties>
	<comment>
		代码生成器配置文件: 
		1.会为所有的property生成property_dir属性,如pkg=com.company => pkg_dir=com/company
		2.可以引用环境变量: ${env.JAVA_HOME} or System.properties: ${user.home},property之间也可以相互引用
	</comment>
	<!-- ==========只需要配置一次========== -->
	<!-- 当前功能名，对应工作空间的文件夹名，注意大小写 -->
	<entry key="projectName">Kensite_cms</entry>
	<!-- 项目基础包路径 -->
	<entry key="basepackage">com.seeyoui.kensite</entry>
	<!-- 项目本地硬盘绝对路径 -->
	<entry key="outRoot">C:\Users\Administrator\git\</entry>
	<!-- ==========只需要配置一次========== -->		
	<!-- JSP文件所在路径 web/${namespace}/${className}/list.jsp -->
	<entry key="namespace">WEB-INF/view</entry>	
	<!-- ==========根据业务自行修改========== -->
	<!-- 当前模块所属包路径 -->
	<entry key="innerpackage">framework.report</entry>
	<!-- 当前模块名，@RequestMapping(value = "guestbook")==@RequestMapping(value = "cms/guestbook") -->
	<entry key="moduleC">ks/</entry>
	<!-- 当前模块名，@RequiresPermissions("guestbook:view")==@RequiresPermissions("cms:guestbook:view") -->
	<entry key="moduleP">ks:</entry>
	<!-- 是否生成全文检索模块，需要：Y，不需要：N，打开将会对增删改查操作有一定效率影响，请按照需求设置 -->
	<entry key="lucene">N</entry>
	<!-- ==========根据业务自行修改========== -->
	<!-- 需要移除的表名前缀,使用逗号进行分隔多个前缀,示例值: t_,v_ -->
	<entry key="tableRemovePrefixes">job_,bo_,cms_,sys_,mod_,t_,ks_</entry>	
	<!-- 数据库用户名及密码，自行修改 -->
	<entry key="jdbc.username">kensitecms</entry>
	<entry key="jdbc.password">kensite</entry>		
	<!-- oracle需要指定jdbc.schema,其它数据库忽略此项配置，注意此项必须为大写  -->
	<entry key="jdbc.schema">KENSITECMS</entry>
	<entry key="jdbc.catalog"></entry>	
	<!-- 数据库类型映射  -->
	<entry key="java_typemapping.java.sql.Timestamp">java.util.Date</entry>
	<entry key="java_typemapping.java.sql.Date">java.util.Date</entry>
	<entry key="java_typemapping.java.sql.Time">java.util.Date</entry>	
	<entry key="java_typemapping.java.lang.Byte">Integer</entry>
	<entry key="java_typemapping.java.lang.Short">Integer</entry>
	<entry key="java_typemapping.java.math.BigDecimal">Long</entry>
	<!-- Mysql 
	<entry key="jdbc.url">jdbc:mysql://localhost:3306/kensitecms?useUnicode=true&amp;characterEncoding=UTF-8</entry>
	<entry key="jdbc.driver">com.mysql.jdbc.Driver</entry>
	-->
	<!-- Oracle -->
	<entry key="jdbc.url">jdbc:oracle:thin:@192.168.31.251:1521:orcl</entry>
	<entry key="jdbc.driver">oracle.jdbc.driver.OracleDriver</entry>	
</properties>
```

#### 5.执行代码生成器生成文件  
> 打开**src/test/java/cn/org/generator/GenerationTest.java**  
修改对应业务表并运行  
运行完成之后刷新整个项目即可看到代码生成器生成的页面  
页面包括：  
JAVA代码：controller|domain|persistence|service  
XML代码：Mapper.xml  
JSP代码：list.jsp|form.jsp  
功能包括：  
新增|修改|删除|导出excel

```java
package cn.org.generator;
import cn.org.rapid_framework.generator.GeneratorFacade;

public class GenerationTest {

	public static void main(String[]args)throws Exception{
		GeneratorFacade g = new GeneratorFacade();
		g.generateByTable("对应业务表明大写","template_kensite_V2");
	}
}
```

#### 6.配置系统菜单及访问权限  
![配置系统菜单](/media/files/2017/02/04/develop4.png)  
![配置访问权限](/media/files/2017/02/04/develop5.png)  

#### 7.重启服务  

#### 8.完成  
![完成](/media/files/2017/02/04/develop6.png)  