# Struts2的Hello World

## 一、搭建Struts2的环境

- 加入jar包

  复制struts\apps\struts2-blank\WEB-INF\lib下的所有jar包到当前web应用的lib目录下

- 在web.xml文件中配置struts2

  复制struts\apps\struts2-blank1\WEB-INF\web.xml文件中的过滤器的配置到当前web应用的web.xml文件中

- 在当前web应用的classpath下添加struts的配置文件

  struts.xml：复制struts1\apps\struts2-blank\WEB-INF\classes下的struts.xml文件到当前web应用的src目录下

## 二、零散知识点

- 在struts.xml中，package表示包，struts2使用package来组织模块，其中name属性必须，用于其他的包应用当前包，extends属性表示当前包继承哪个包，即可以继承其中的所有的配置，通常情况下继承struts-default；

- 一个struts2的请求就是一个action；

- 配置一个action，name属性对应一个struts2的请求的名字（或者对应servletPath，但去除/和扩展名），不包含扩展名，result表示结果

  ```xml
  <action name="product-input">
  	<result>/WEB-INF/pages/input.jsp</result>
  </action>
  ```