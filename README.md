# Struts2的Hello World

## 一、搭建Struts2的环境

- 加入jar包

  复制struts\apps\struts2-blank\WEB-INF\lib下的所有jar包到当前web应用的lib目录下

- 在web.xml文件中配置struts2

  复制struts\apps\struts2-blank1\WEB-INF\web.xml文件中的过滤器的配置到当前web应用的web.xml文件中

- 在当前web应用的classpath下添加struts的配置文件

  struts.xml：复制struts1\apps\struts2-blank\WEB-INF\classes下的struts.xml文件到当前web应用的src目录下

## 二、零散知识点

- 在struts.xml中，package表示包，struts2使用package来组织模块，其中name属性必须，用于其他的包应用当前包；extends属性表示当前包继承哪个包，即可以继承其中的所有的配置，通常情况下继承struts-default；namespace属性时可选的，如果没有给出，/是默认值，若namespace有一个非默认值，则要想调用这个包里的action，就必须把这个属性所定义的命名控件添加到相关的URI字符串里，即在servletPath前面加上这个namespace：http://localhost:8080/contextPath/namspace/actionName.action

- 一个struts2的请求就是一个action。

- 配置一个action，name属性对应一个struts2的请求的名字（或者对应servletPath，但去除/和扩展名），不包含扩展名；class的默认值：com.opensymphony.xwork2.ActionSupport；method的默认值为：execute；result表示结果，表示action方法执行后可能返回的结果，所以一个action节点可能会有多个result子结点，多个result子结点使用name来区分，name标识一个result，和action方法的返回值对应，默认值为success；type表示结果的类型，默认值为dispatcher（转发到结果）。

  ```xml
  <action name="product-input">
  	<result>/WEB-INF/pages/input.jsp</result>
  </action>
  ```