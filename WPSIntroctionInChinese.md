WEB-PERF-SERVICE（WPS）说明
简介：
WPS是一套利用HttpWatch，BrowserMobProxy，Selenium 2.0真实操作浏览器获得web性能数据（HttpWatch/BrowserMobProxy生成的HAR）和附加的web性能数据（运行期的浏览器内存值，CPU值和页面渲染的HTML代码）整套服务，包括如下service：
1.	MemoryService：获得运行期浏览器内存服务
2.	CPUService：获得运行期CPU服务
3.	HWS：利用HttpWatch+Selenium获得web性能数据（包括附加的性能数据）服务
4.	BMPS：利用BrowserMobProxy+Selenium获得web性能数据（包括附加的性能数据）服务
5.	PQS：运行的case入队出队服务
6.	PBS: 批处理case服务
7.	PDS：运行的case分发到具体执行机器上服务

支持功能：
8.	多浏览器（ie6，ie7，ie8和ff36，ff40，ff50，ff60，ff70，ff80）
9.	多操作系统（Selenium 2.0即WebDriver支持的所有操作系统）
10.	分布式执行（一套PDS对应多套PQS和多套HWS，BMPS，PDS负责分发）
11.	同时得到性能HAR文件和附加的性能txt文件
12.	提供webservice形式，方便调用
13.	提供2种形式的case（请求url方式和Selenium IDE录制的脚本（TODO））



架构设计：
详细依赖关系如下图：