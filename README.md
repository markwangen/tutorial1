tutorial1
=========

这个是WEBX框架的一个简单的实例，在自动生成了实例之后添加了一些功能。

以下是一些对WEBX的原理理解。
WEBX借鉴了turbine框架的思想，核心在于约定胜于配置，由于刚开始不太理解约定胜于配置的概念，
结果无法理解http://localhost:8081/simple/say_hi.do与org.mark.webx.tutorial1.app1.module.screen.simple.SayHi.java是如何对应起来的，
一切都无法理解，匪夷所思。

实际上，webx基于一套约定的规则，去用WebxApplicationContext（继承于spring的ResourceLoadingXmlWebApplicationContext）
去将指定目录的java文件配成spring容器中的bean,也就是说spring需要读取xml配置文件或者用注解引擎去将java配置成容器中的bean,而webx
直接就是将符合规则的包中的所有java文件读取进容器。

规则：
1. say_hi.do 对应到SayHi.java，这个不用配置，webx turbine框架自动去找的，以下类似。
2.新增一个car(sofa中一个web bundle的概念)，只需要新增对应的包即可，对于上例，如果想新增一个app2的car，那么只需
新增包org.mark.webx.tutorial1.app2.module.screen.simple，然后再包里放基于规则1的类即可
3.在WEB-INFO中要对应的放置webx-app2.xml的配置文件，同时要放置对应car的folder用于放置表单验证等的xml文件

做完以上这些步，基本就可以了。

WEBX的其它的一些注入概念，分层概念都很容易理解，就不单独记笔记了。
