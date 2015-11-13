WEB-PERF-SERVICE(WPS)安装说明
公共安装：
1.	所有的机器上都要安装jdk 6
2.	所有的机器上都要安装tomcat 6，且tomcat不能装成service
3.	HWS和BMPS的机器上要安装相应的IE和FF，并且要安装HttpWatch专业版，装HttpWatch的时候勾选同时安装到FF上即可，如何路由由hosts.properties相应配置决定，目前支持ie6，ie7，ie8，ie9，ff36，ff40，ff50，ff60，ff70，ff80，ff90，每一种类型最大支持5台测试机


4.	IE一台机器只能装1个，安装在默认机器下，FF一台机器可以装多个，默认安装目录在config.properties中配置

如果要安装不同版本的FF版本，如3.6,4.0,5.0…则安装文件命名如下：

目前支持3.6,4.0,5.0,6.0,7.0,8.0,9.0
PDS安装：
直接从

http://code.google.com/p/web-perf-test-service/downloads/list
下载WPS-1.1.0-with-src.rar的源代码并获得WEB-INF文件及文件夹下所有内容

在要安装PDS的那台机器下的Tomcat下的webapp下新建一个WPS文件夹
把WEB-INF文件夹直接拷贝到要安装PDS那台机器下的Tomcat下的webapp下的WPS文件夹下，如下图所示：

配置下列属性文件：
Log4j.properties:这个就不说了
Hosts.properties:这个要测试的HWS和BMPS客户端的配置，分别指向那台HWS，注意要有端口号

Config.properties:

Outputfilefullpath参数生生成的har文件和txt文件存放路径
Defaultfirefoxinstallpath参数是FF安装全路径的前缀
Defaultwaitseconds参数是页面打开后等待完全渲染的秒数
启动tomcat，不能作为service启动
运行deploy\_pds.bat

HWS安装：
同PDS，只需运行deploy\_hws.bat即可

BMPS安装：
同PDS，只需运行deploy\_bmps.bat即可
