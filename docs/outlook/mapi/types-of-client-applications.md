---
title: 客户端应用程序的类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 52ce22a9-3ec2-481c-bb91-7a5bcca817f5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 167710243c61a7226375b88977c94ff4a517c1c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417054"
---
# <a name="types-of-client-applications"></a><span data-ttu-id="fc409-103">客户端应用程序的类型</span><span class="sxs-lookup"><span data-stu-id="fc409-103">Types of Client Applications</span></span>

  
  
<span data-ttu-id="fc409-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc409-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc409-105">邮件客户端主要分为两种类型：处理 iPM (的) 以及处理 IPC (进程间通信) 客户端。</span><span class="sxs-lookup"><span data-stu-id="fc409-105">There are primarily two types of messaging clients: those that handle interpersonal messages (IPM) and those that handle interprocess communication (IPC) messages.</span></span> <span data-ttu-id="fc409-106">在这些类型中，邮件客户端应用程序可以按如下方式分类：</span><span class="sxs-lookup"><span data-stu-id="fc409-106">Within those types, messaging client applications can be categorized as follows:</span></span>
  
- <span data-ttu-id="fc409-107">个人对个人</span><span class="sxs-lookup"><span data-stu-id="fc409-107">Person-to-person</span></span>
    
- <span data-ttu-id="fc409-108">个人到计算机</span><span class="sxs-lookup"><span data-stu-id="fc409-108">Person-to-machine</span></span>
    
- <span data-ttu-id="fc409-109">计算机到个人</span><span class="sxs-lookup"><span data-stu-id="fc409-109">Machine-to-person</span></span>
    
- <span data-ttu-id="fc409-110">计算机到计算机</span><span class="sxs-lookup"><span data-stu-id="fc409-110">Machine-to-machine</span></span>
    
- <span data-ttu-id="fc409-111">人员与计算机的组合</span><span class="sxs-lookup"><span data-stu-id="fc409-111">Mix of persons and machines</span></span>
    
<span data-ttu-id="fc409-112">个人到个人应用程序涉及发起邮件交换的人和另一个人做出响应。</span><span class="sxs-lookup"><span data-stu-id="fc409-112">Person-to-person applications involve a person initiating the exchange of messages and another person responding.</span></span> <span data-ttu-id="fc409-113">此类别的应用程序包括传统电子邮件应用程序以及更加结构化的交换，如文档传送或费用审批。</span><span class="sxs-lookup"><span data-stu-id="fc409-113">This category of applications includes traditional email applications as well as more structured exchanges such as document routing or expense approval.</span></span>
  
<span data-ttu-id="fc409-114">个人到计算机应用程序涉及发起邮件交换和计算机响应的人。</span><span class="sxs-lookup"><span data-stu-id="fc409-114">Person-to-machine applications involve a person initiating the exchange of messages and a machine responding.</span></span> <span data-ttu-id="fc409-115">此类别包括使用电子邮件的应用程序，例如提交数据库查询或订阅邮件列表。</span><span class="sxs-lookup"><span data-stu-id="fc409-115">This category includes applications that use email to, for example, submit a database query or subscribe to a mailing list.</span></span>
  
<span data-ttu-id="fc409-116">计算机到个人应用程序涉及发起邮件交换和人员响应的机器。</span><span class="sxs-lookup"><span data-stu-id="fc409-116">Machine-to-person applications involve a machine initiating the exchange of messages and a person responding.</span></span> <span data-ttu-id="fc409-117">此类别包括分发文档的应用程序，如新闻源和意见调查。</span><span class="sxs-lookup"><span data-stu-id="fc409-117">This category includes applications that distribute documents such as news feeds and opinion surveys.</span></span>
  
<span data-ttu-id="fc409-118">计算机到计算机应用程序涉及发起邮件交换和计算机响应的机器。</span><span class="sxs-lookup"><span data-stu-id="fc409-118">Machine-to-machine applications involve a machine initiating the exchange of messages and a machine responding.</span></span> <span data-ttu-id="fc409-119">此类别包括链接检测信号监视、目录和数据库复制等应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc409-119">This category includes applications such as link heartbeat monitoring and directory and database replication.</span></span>
  
<span data-ttu-id="fc409-120">最后一个类别是人员与计算机的组合，涉及更复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="fc409-120">The final category, a mix of persons and machines, involves a more complex scenario.</span></span> <span data-ttu-id="fc409-121">此类别包括不必在发件人和收件人之间传输邮件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc409-121">This category includes applications that do not necessarily transmit messages between senders and recipients.</span></span> <span data-ttu-id="fc409-122">相反，他们可能会直接将它们张贴到公用文件夹或消息存储支持的网站论坛中。</span><span class="sxs-lookup"><span data-stu-id="fc409-122">Instead they might post them directly into a public folder or to a web-site forum supported by a message store.</span></span> <span data-ttu-id="fc409-123">然后，其他读者、管理员或软件代理可以按需使用这些邮件。</span><span class="sxs-lookup"><span data-stu-id="fc409-123">The messages can then be consumed on demand by other readers, an administrator, or a software agent.</span></span>
  
<span data-ttu-id="fc409-124">如果要编写将消息发送到公共论坛的个人到个人应用程序、计算机到个人应用程序或应用程序，请设计应用程序以发送和接收 IPM 消息。</span><span class="sxs-lookup"><span data-stu-id="fc409-124">If you are writing a person-to-person application, machine-to-person application, or an application that posts messages to public forums, design your application to send and receive IPM messages.</span></span> <span data-ttu-id="fc409-125">如果要编写个人到计算机或计算机到计算机的应用程序，它可以设计为发送和接收 IPC 邮件。</span><span class="sxs-lookup"><span data-stu-id="fc409-125">If you are writing a person-to-machine or machine-to-machine application, it can be designed to send and receive IPC messages.</span></span> <span data-ttu-id="fc409-126">任何需要用户交互的应用程序都必须支持 IPM 消息。</span><span class="sxs-lookup"><span data-stu-id="fc409-126">Any application that requires the interaction of a human user must support IPM messages.</span></span> <span data-ttu-id="fc409-127">各种方案中涉及用户和计算机的应用程序通常必须同时支持 IPM 和 IPC 消息。</span><span class="sxs-lookup"><span data-stu-id="fc409-127">Applications that involve both people and machines in a variety of scenarios often must support both IPM and IPC messages.</span></span> <span data-ttu-id="fc409-128">这两个类之间的唯一真正区别是邮件存储中的 IPM 邮件对邮件客户端的用户可见，而 IPC 消息通常对客户端应用程序用户不可见。</span><span class="sxs-lookup"><span data-stu-id="fc409-128">The only real difference between the two classes is that IPM messages in a message store are visible to users of messaging clients, while IPC messages usually are not visible to the client application users.</span></span> 
  
<span data-ttu-id="fc409-129">通过创建新的 IPM 或 IPC 子类，可以自定义和增强这些类，而不是将邮件限制到 MAPI 超级类、IPM 和 IPC 提供的功能。</span><span class="sxs-lookup"><span data-stu-id="fc409-129">Rather than limiting your messages to the capabilities provided by the MAPI superclasses, IPM and IPC, you can customize and enhance these classes by creating new IPM or IPC subclasses.</span></span> <span data-ttu-id="fc409-130">创建邮件子类涉及创建继承自超级类的新邮件类。</span><span class="sxs-lookup"><span data-stu-id="fc409-130">Creating message subclasses involves inventing new message classes that inherit from the superclasses.</span></span> <span data-ttu-id="fc409-131">例如，如果您的个人对个人应用程序专门负责客户关系管理，则可以通过定义 IPM 对 IPM 超级类进行子类。Contact.Customer 类，并创建描述客户的属性。</span><span class="sxs-lookup"><span data-stu-id="fc409-131">For example, if your person-to-person application specializes in customer relationship management, you can subclass the IPM superclass by defining an IPM.Contact.Customer class and create properties that describe a customer.</span></span> <span data-ttu-id="fc409-132">除了支持这些自定义属性，你的 IPM。Contact.Customer 邮件将继承所有 IPM 邮件支持的属性。</span><span class="sxs-lookup"><span data-stu-id="fc409-132">In addition to supporting these custom properties, your IPM.Contact.Customer messages will inherit the properties supported by all IPM messages.</span></span>
  

