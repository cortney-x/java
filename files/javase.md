### java SE
<p>
javaEE 是 javaSE 上的一个官方扩展，用于“企业”程序开发(直译其实不是很贴切)。所有的第三方扩展都是为了简化原生的操作。你先设想这样的一个环节。如果你要开发一个web项目，但是完全用javaSE。1.你要自己写一个网络通信库，和netty类似，用来将Socket封装起来。简化其中的操作。2.你要根据HTTP协议写协议的encode 和 decode,这里是最复杂的。因为你要根据HTTP协议的不同状况进入不同的流程，最重要的你还需要根据HTTP header中的内容，区分出各种各样的情况，比如cookie的设置和判断等。3.等你完整地实现了一个http协议的server之后，你进入了 resquest 和response 的 content内容的处理，request中不仅有参数，有的时候还是文件的二进制流。其中最重要的是response的content的内容构造，为了拥有动态的内容，你还要根据用户(cookie)的上下文状态，返回合适的结果。现在我们还没有涉及到EJB，JDBC，JSP 之类的东西。然后你发现，上面的 1 2 就是一个简单的tomcat的HTTP server部分，3 其实就是servlet做的事情。这个时候你就明白了，javaEE的 web部分其实就是一个规范，用来对“java进行web开发”进行一个规范化和约束，使得整个生态都围绕着某一个规范进行。这样的好处就是，你在开发一个 java web应用的时候，你是不需要去考虑你的web是跑在 tomcat 或者 Jboss 上的。SSH的诞生，其实就是对 servlet的简陋的不满，以及 java EE中 EJB的不满而诞生的。其中的struts or spring MVC ，是对请求路径，数据解析等操作提供了更高层次的抽象，我相信每一个在web.xml中配置上百个路径映射的人都深恶痛绝。第二个 S ，早先 Spring 的提出就是为了解决 java项目中各种对象之间的依赖和解耦所提出的方案。目前的Spring 已经自成一体了，已经成为了另一种事实上的标准。第三个 H，hibernate （其实大家用mybatis比较多），是为了简化 java与 关系性数据库交互而诞生的。如果你用过原生的JDBC 操作数据库，特别是存在上百个sql的时候，想跳楼的想法会时不时冒出来。毕竟数据库中存储的数据和 java 能操作的对象是两码事，为了在其中进行转换，无数先辈折戟沉沙，比如 enum 在数据库中的存储。总结部分：java SE，是整个体系的基石。往后的其他东西都是为了解决某一个特定问题而衍生开发出来的第三方组件。其最主要的目的是为了简化开发过程，减少人为因素导致整个项目的不可控。
</p>