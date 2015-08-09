---
layout: post
title: "无后端（nobackend）：前端优先的Web开发【译】"
date: 2014-01-26 09:49:18 -0600
comments: true
categories: translation, front-end
---

每个应用都由两样东西构成：该应用独有的功能和所有应用共有的功能，比方说用户注册、登录、忘记密码等。而从用户的角度出发，那些独有的功能归结起来就是用户界面以及系统的行为模式。而在视觉表象之后的功能，用户并不关心，他们只期望系统能按预期运行就可以了。

前端和后端有各自的侧重点，因此往往也需要不同的技能，由不同的开发人员来负责完成。无后端（[nobackend](http://nobackend.org/2013/05/welcome-to-noBackend.html)）的开发原则能够进一步解偶这些不同的侧重点，这样两边的开发人员可以更加专注于各自真正热衷的工作。

{% img /images/nobackend-logo.png noBackend %}

### 一个简单的例子

后端经常需要提供API给前端，以下是一个简单的例子，使用API进行用户登录。

```javascript
POST /session
{ "email":"joe@example.com", "password": "secret"  }
```

前端的开发人员需要负责发送上述请求并对结果进行响应，还要考虑到一些极端的情况，如失去连接或不可预知的服务器错误等。与此相反的是，无后端的设计原则则建议由前端开发人员来定义API，用前端的代码来描述后端的功能，举例如下：
```
signIn( 'joe@example.com', 'secret'  )
.then( showDashboard  )
.fail( showError  )
```

我们称此为梦幻代码（[Dreamcode](http://nobackend.org/dreamcode.html)），因为这些代码经常是在真正的代码可运行以前就已经写好了。初一看，这样并没有多大意义，只不过是改成了发送AJAX请求并调用相应的回调函数而已，但是以这样的方式定义的API在许多方面都会更加强大：

<!--more-->

#### 1. 灵活

用户如果想要登录，那么他们也就只关心登录这个行为本身，而绝不会去关心：

* 请求是否是送到应用的服务器还是一个中央的验证服务器
* 是一个HTTP的POST请求还是PUT请求。
* 是否是通过websocket发送的
* 验证使用的cookies还是使用session ID或者是自定义的header
* 应用是否会在前一个请求时后再次发送请求

signIn这个方法的实现可以进行调整以反映后端的变化，但是就这个API本身，前端开发人员并不需要去修改了。

#### 2. 简洁

从前端开发人员的角度来看，实现signIn方法要简单的多，代码量也可以少很多；而从后端开发人员的角度来看，尽管刚开始要投入更多的精力，但是和RESTful API相比，前面的API要更容易定义，文档化和测试。

#### 3. 前端驱动

前端开发人员可以引领构建应用的整个设计流程。以Dreadcode的方式来描述后端的功能，可以让开发人员更加专注于用户体验，从而避免了由于讨论具体的实现细节而有所分心，也不会由于要等待后端API的实现而拖延项目的进度。

### 一个更加复杂的例子

当你研究一个更复杂的例子以后，前优势会显得更加明显。假设你想要发送一封邮件，要附上当前页的PDF。

```
sendEmail({
  subject: "Hello, World!",
  text: "This mail has been sent from the frontend",
  html: "This mail has been sent from the frontend",
  to: "joe@example.com",
  attachments: [ 
  	convert( document.body  ).to("report.pdf"),
  ]
})
```

要让这段代码跑起来，并且要让它不受垃圾邮件的影响，可能会相当困难。但是至少可以马上写一些quick和dirty的实现，然后再一点一点地改进，而在这个过程中无需改变API。这里的**关键点**在于，前端开发人员可以把这看成是一个已有的功能，从而可以专注于用户体验，而不需要去关心后台开发人员到目前为止究竟有多么复杂地实现了这个功能。

### 现有的一些nobackend的解决方案

一个nobackend的解决方案应该提供一个前端的API来处理一些通用的后端任务，至少应该包括用户验证、数据持久化和同步等。以下是一些可以关注的方案：

* [Backendless](http://backendless.com/)
* [deployd](http://deployd.com/)
* [Firebase](https://www.firebase.com/)
* [Hoodie](http://hood.ie/)
* [Kinvey](http://www.kinvey.com/)
* [Parse](https://parse.com/)
* [remoteStorage](http://remotestorage.io/)
* [Sockethub](http://sockethub.org/)

也可以参考下：[unhosted](http://unhosted.org/)。以上这个列表中，绝大多数都是托管服务，对于想要用自己的服务器来托管的同学，可以选择开源的deployd。

原文：http://nobackend.org/2013/05/welcome-to-noBackend.html
