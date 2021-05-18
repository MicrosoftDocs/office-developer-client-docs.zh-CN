---
title: Outlook Social Connector 提供程序参考
manager: soliver
ms.date: 04/04/2016
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 13661393-adf6-4870-86c4-303262317675
description: The Outlook Social Connector 2013 provides a communication hub for personal and professional communications.
ms.openlocfilehash: e570fe69cbbe0e8d472e712fb3b8592c97fe43c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359834"
---
# <a name="outlook-social-connector-provider-reference"></a><span data-ttu-id="7c2c5-103">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="7c2c5-103">Outlook Social Connector provider reference</span></span>

<span data-ttu-id="7c2c5-104">The Outlook Social Connector 2013 provides a communication hub for personal and professional communications.</span><span class="sxs-lookup"><span data-stu-id="7c2c5-104">The Outlook Social Connector 2013 provides a communication hub for personal and professional communications.</span></span> <span data-ttu-id="7c2c5-105">the Outlook Social Connector (OSC) works with SharePoint Server， SharePoint Workspace， Lync client， and all Office client applications that support presence information and the Contact Card support the OSC.</span><span class="sxs-lookup"><span data-stu-id="7c2c5-105">The Outlook Social Connector (OSC) works with SharePoint Server, SharePoint Workspace, Lync client, and all Office client applications that support presence information and the Contact Card support the OSC.</span></span> 

<span data-ttu-id="7c2c5-106">特别是Outlook，只需选择 Outlook 项目（如电子邮件或会议请求）并单击该项目中的发件人或收件人，而无需离开 Outlook，用户即可在最喜爱的社交网络上查看此人的"人员窗格"活动、照片和状态更新。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-106">In Outlook in particular, just by selecting an Outlook item such as an email or meeting request and clicking the sender or a recipient in that item, without leaving Outlook, users can see in the People Pane activities, photos, and status updates of this person on their favorite social networks.</span></span> <span data-ttu-id="7c2c5-107">用户可以方便地查看从Outlook收到的所有电子邮件、附件和会议。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-107">Users can conveniently see all the Outlook emails, attachments, and meetings received from this person.</span></span> <span data-ttu-id="7c2c5-108">在组织环境中，SharePoint用户还可以在人员窗格文档更新以及此人员的其他网站活动上查看SharePoint活动。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-108">In an organizational environment, users on a SharePoint site can also see in the People Pane document updates and other site activities of this person on the SharePoint site.</span></span>
  
<span data-ttu-id="7c2c5-109">社交网络可以开发 OSC 提供程序，以同步和显示支持服务器和应用程序中的社交网络更新。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-109">A social network can develop a provider for the OSC to synchronize and surface social network updates in supporting servers and applications.</span></span> <span data-ttu-id="7c2c5-110">热门社交网络（如 LinkedIn、Facebook 和 Windows Live）为 OSC 提供提供程序。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-110">Popular social networks such as LinkedIn, Facebook, and Windows Live are offering providers for the OSC.</span></span> 
  
<span data-ttu-id="7c2c5-111">The Outlook Social Connector 2013 Provider Reference介绍如何使用 OSC 提供程序扩展性开发 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-111">The Outlook Social Connector 2013 Provider Reference describes how to develop an OSC provider using OSC provider extensibility.</span></span> 
  
<span data-ttu-id="7c2c5-112">如果你是第一次开发 Outlook 解决方案，请参阅[选择某个 API 或技术开发适用于 Outlook 的解决方案](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md)，以确定最适合你需求的 API 和技术。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-112">If you are new to developing solutions for Outlook, see [Selecting an API or technology for developing solutions for Outlook](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md) to identify the APIs and technologies that are most appropriate for your needs.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="7c2c5-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="7c2c5-113">In this section</span></span>

- <span data-ttu-id="7c2c5-114">[开发 Outlook](getting-started-with-developing-an-outlook-social-connector-provider.md)Social Connector 提供程序入门：概述 OSC，包括以下内容：OSC 提供程序如何有用、学习开发提供程序的快速步骤、技术要求、开发提供程序的最佳实践以及此版本的新增功能。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-114">[Getting Started with Developing an Outlook Social Connector Provider](getting-started-with-developing-an-outlook-social-connector-provider.md): Provides an overview of the OSC, including the following: how an OSC provider can be useful, quick steps for learning to develop a provider, technical requirements, best practices for developing a provider, and what's new in this release.</span></span>
    
- <span data-ttu-id="7c2c5-115">[OSC 示例模板](osc-sample-templates.md)：介绍Visual Studio提供程序的几个模板。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-115">[OSC Sample Templates](osc-sample-templates.md): Describes several Visual Studio templates for developing a provider.</span></span>
    
- <span data-ttu-id="7c2c5-116">[OSC 典型调用序列](osc-typical-calling-sequences.md)：介绍 OSC 提供程序扩展性接口中成员的 OSC 的一些典型调用序列。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-116">[OSC Typical Calling Sequences](osc-typical-calling-sequences.md): Describes a few typical calling sequences by the OSC of members in the OSC provider extensibility interfaces.</span></span> <span data-ttu-id="7c2c5-117">这应该可以更好地了解如何实现这些接口。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-117">This should enable you to better understand how to implement these interfaces.</span></span>
    
- <span data-ttu-id="7c2c5-118">[Developing a Provider with the OSC XML Schema](developing-a-provider-with-the-osc-xml-schema.md)： Describes how the OSC provider extensibility interfaces and OSC XML schema are designed to support an OSC provider.</span><span class="sxs-lookup"><span data-stu-id="7c2c5-118">[Developing a Provider with the OSC XML Schema](developing-a-provider-with-the-osc-xml-schema.md): Describes how the OSC provider extensibility interfaces and OSC XML schema are designed to support an OSC provider.</span></span>
    
- <span data-ttu-id="7c2c5-119">[调试提供程序](debugging-a-provider.md)：推荐了一些有助于调试 OSC 提供程序的方法。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-119">[Debugging a Provider](debugging-a-provider.md): Suggests a few ways to help debug an OSC provider.</span></span>
    
- <span data-ttu-id="7c2c5-120">[部署提供程序](deploying-a-provider.md)：介绍 OSC 提供程序的注册要求，并提供用于安装提供程序的清单。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-120">[Deploying a Provider](deploying-a-provider.md): Describes registration requirements for an OSC provider, and provides a checklist for installing a provider.</span></span>
    
- <span data-ttu-id="7c2c5-121">[准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)：建议在发布 OSC 提供程序之前可以执行的测试。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-121">[Getting Ready to Release an OSC Provider](getting-ready-to-release-an-osc-provider.md): Suggests tests you can do before releasing an OSC provider.</span></span>
    
- <span data-ttu-id="7c2c5-122">[Outlook连接器提供程序参考](outlook-social-connector-provider-reference-0.md)：提供 OSC 提供程序扩展性接口和 OSC XML 架构的参考信息，并列出可能的错误代码。</span><span class="sxs-lookup"><span data-stu-id="7c2c5-122">[Outlook Social Connector Provider Reference](outlook-social-connector-provider-reference-0.md): Provides reference information for the OSC provider extensibility interfaces and OSC XML schema, and lists possible error codes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7c2c5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c2c5-123">See also</span></span>

- [<span data-ttu-id="7c2c5-124">OutlookSocial Connector 2013 提供程序参考版权声明</span><span class="sxs-lookup"><span data-stu-id="7c2c5-124">Outlook Social Connector 2013 provider reference copyright notice</span></span>](outlook-social-connector-2013-provider-reference-copyright-notice.md) 
- [<span data-ttu-id="7c2c5-125">文档约定</span><span class="sxs-lookup"><span data-stu-id="7c2c5-125">Document Conventions</span></span>](https://msdn.microsoft.com/office/aa905365.aspx)   
- [<span data-ttu-id="7c2c5-126">Microsoft 产品中的辅助功能</span><span class="sxs-lookup"><span data-stu-id="7c2c5-126">Accessibility in Microsoft Products</span></span>](https://www.microsoft.com/enable/products/default.aspx)  
- [<span data-ttu-id="7c2c5-127">Microsoft Online 隐私声明</span><span class="sxs-lookup"><span data-stu-id="7c2c5-127">Microsoft Online Privacy Notice</span></span>](https://privacy.microsoft.com/en-us/privacystatement)
    

