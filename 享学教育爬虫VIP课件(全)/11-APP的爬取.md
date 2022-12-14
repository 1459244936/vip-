# 第十一节 APP 的爬取

前面的课程中介绍的都是爬取 Web 网页的内容。随着移动互联网的发展，越来越多的企业并没有提供 Web 网页端的服务，而是直接开发了 App，更多更全的信息都是通过 App 来展示的。那么针对 App 我们可以爬取吗？当然可以。

App 的爬取相比 Web 端爬取更加容易，反爬虫能力没有那么强，而且数据大多是以 JSON 形式传输的，解析更加简单。在 Web 端，我们可以通过浏览器的开发者工具监听到各个网络请求和响应过程，在 App 端如果想要查看这些内容就需要借助抓包软件。常用的抓包软件有 WireShark、Filddler、Charles、mitmproxy、AnyProxy 等，它们的原理基本是相同的。我们可以通过设置代理的方式将手机处于抓包软件的监听之下，这样便可以看到 App 在运行过程中发生的所有请求和响应了，相当于分析 Ajax 一样。如果这些请求的 URL、参数等都是有规律的，那么总结出规律直接用程序模拟爬取即可，如果它们没有规律，那么我们可以利用另一个工具 mitmdump 对接 Python 脚本直接处理 Response。另外，App 的爬取肯定不能由人来完成，也需要做到自动化，所以我们还要对 App 进行自动化控制，这里用到的库是 Appium。

本节将介绍 Charles、mitmproxy、mitmdump、Appium 等库的用法。掌握了这些内容，我们可以完成绝大多数 App 数据的爬取。