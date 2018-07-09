---
title: Outlook Social Connector 提供程序参考
manager: soliver
ms.date: 04/04/2016
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 13661393-adf6-4870-86c4-303262317675
description: Outlook Social Connector 2013 为个人和专业的通信提供了通信集线器。
ms.openlocfilehash: 32a9eb88b7724f8735d0eb8623bb3716ad836a7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779323"
---
# <a name="outlook-social-connector-provider-reference"></a><span data-ttu-id="0e7fb-103">Outlook Social Connector 提供程序参考</span><span class="sxs-lookup"><span data-stu-id="0e7fb-103">Outlook Social Connector provider reference</span></span>

<span data-ttu-id="0e7fb-104">Outlook Social Connector 2013 为个人和专业的通信提供了通信集线器。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-104">The Outlook Social Connector 2013 provides a communication hub for personal and professional communications.</span></span> <span data-ttu-id="0e7fb-105">Outlook Social Connector (OSC) 适用于 SharePoint Server，SharePoint Workspace Lync 客户端，并且所有 Office 客户端应用程序都支持的状态信息和联系人卡片都支持 OSC。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-105">The Outlook Social Connector (OSC) works with SharePoint Server, SharePoint Workspace, Lync client, and all Office client applications that support presence information and the Contact Card support the OSC.</span></span> 

<span data-ttu-id="0e7fb-106">在 Outlook 中特定，只需通过选择 Outlook 项目，如电子邮件或会议请求并单击发件人或收件人在该项目，而不必离开 Outlook 中，用户可以查看在人员窗格活动、 照片和此人的状态更新在其喜欢的社交网络。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-106">In Outlook in particular, just by selecting an Outlook item such as an email or meeting request and clicking the sender or a recipient in that item, without leaving Outlook, users can see in the People Pane activities, photos, and status updates of this person on their favorite social networks.</span></span> <span data-ttu-id="0e7fb-107">用户可以方便地查看所有 Outlook 电子邮件、 附件和接收来自此人的会议。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-107">Users can conveniently see all the Outlook emails, attachments, and meetings received from this person.</span></span> <span data-ttu-id="0e7fb-108">在组织的环境中，还可以在人员窗格文档更新和其他网站活动的 SharePoint 网站上的此人查看 SharePoint 网站上的用户。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-108">In an organizational environment, users on a SharePoint site can also see in the People Pane document updates and other site activities of this person on the SharePoint site.</span></span>
  
<span data-ttu-id="0e7fb-109">社交网络如何开发 OSC 提供程序同步和显示支持的服务器和应用程序中的社交网络更新。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-109">A social network can develop a provider for the OSC to synchronize and surface social network updates in supporting servers and applications.</span></span> <span data-ttu-id="0e7fb-110">LinkedIn、 Facebook，和 Windows Live 等的常用社交网络提供 OSC 提供的程序。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-110">Popular social networks such as LinkedIn, Facebook, and Windows Live are offering providers for the OSC.</span></span> 
  
<span data-ttu-id="0e7fb-111">Outlook Social Connector 2013 提供程序参考介绍如何开发 OSC 提供程序使用 OSC 提供程序扩展性。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-111">The Outlook Social Connector 2013 Provider Reference describes how to develop an OSC provider using OSC provider extensibility.</span></span> 
  
<span data-ttu-id="0e7fb-112">如果您是新增开发 Outlook 解决方案，请参阅[选择的 API 或技术的开发 outlook 解决方案](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md)来标识的 Api 和技术的最适合您的需求。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-112">If you are new to developing solutions for Outlook, see [Selecting an API or technology for developing solutions for Outlook](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md) to identify the APIs and technologies that are most appropriate for your needs.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="0e7fb-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="0e7fb-113">In this section</span></span>

- <span data-ttu-id="0e7fb-114">[Outlook Social Connector 提供程序开发入门](getting-started-with-developing-an-outlook-social-connector-provider.md)： 概述 OSC，其中包括： 如何 OSC 提供程序可能很有用，用于学习如何开发提供程序，技术要求快速步骤的最佳做法开发提供程序和 what's new in 此发行版。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-114">[Getting Started with Developing an Outlook Social Connector Provider](getting-started-with-developing-an-outlook-social-connector-provider.md): Provides an overview of the OSC, including the following: how an OSC provider can be useful, quick steps for learning to develop a provider, technical requirements, best practices for developing a provider, and what's new in this release.</span></span>
    
- <span data-ttu-id="0e7fb-115">[OSC 示例模板](osc-sample-templates.md)： 描述的开发提供程序的多个 Visual Studio 模板。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-115">[OSC Sample Templates](osc-sample-templates.md): Describes several Visual Studio templates for developing a provider.</span></span>
    
- <span data-ttu-id="0e7fb-116">[OSC 典型调用序列](osc-typical-calling-sequences.md)： 描述通过 OSC 提供程序扩展性接口中的成员 OSC 的几个典型调用序列。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-116">[OSC Typical Calling Sequences](osc-typical-calling-sequences.md): Describes a few typical calling sequences by the OSC of members in the OSC provider extensibility interfaces.</span></span> <span data-ttu-id="0e7fb-117">这应使您能够更好地了解如何实现这些接口。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-117">This should enable you to better understand how to implement these interfaces.</span></span>
    
- <span data-ttu-id="0e7fb-118">[开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)： 介绍如何 OSC 提供程序扩展性接口和 OSC XML 架构旨在支持 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-118">[Developing a Provider with the OSC XML Schema](developing-a-provider-with-the-osc-xml-schema.md): Describes how the OSC provider extensibility interfaces and OSC XML schema are designed to support an OSC provider.</span></span>
    
- <span data-ttu-id="0e7fb-119">[调试提供程序](debugging-a-provider.md)： 建议几种方法可以帮助调试 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-119">[Debugging a Provider](debugging-a-provider.md): Suggests a few ways to help debug an OSC provider.</span></span>
    
- <span data-ttu-id="0e7fb-120">[部署提供程序](deploying-a-provider.md)： 描述注册要求 OSC 提供程序，并提供用于安装的提供程序的清单。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-120">[Deploying a Provider](deploying-a-provider.md): Describes registration requirements for an OSC provider, and provides a checklist for installing a provider.</span></span>
    
- <span data-ttu-id="0e7fb-121">[获取准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)： 建议发布 OSC 提供程序之前，您可以执行操作的测试。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-121">[Getting Ready to Release an OSC Provider](getting-ready-to-release-an-osc-provider.md): Suggests tests you can do before releasing an OSC provider.</span></span>
    
- <span data-ttu-id="0e7fb-122">[Outlook Social Connector 提供程序参考](outlook-social-connector-provider-reference-0.md)： 提供引用 OSC 提供程序扩展性接口和 OSC XML 架构和列表可能错误代码的信息。</span><span class="sxs-lookup"><span data-stu-id="0e7fb-122">[Outlook Social Connector Provider Reference](outlook-social-connector-provider-reference-0.md): Provides reference information for the OSC provider extensibility interfaces and OSC XML schema, and lists possible error codes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0e7fb-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e7fb-123">See also</span></span>

- [<span data-ttu-id="0e7fb-124">Outlook Social Connector 2013 提供程序参考版权声明</span><span class="sxs-lookup"><span data-stu-id="0e7fb-124">Outlook Social Connector 2013 provider reference copyright notice</span></span>](outlook-social-connector-2013-provider-reference-copyright-notice.md) 
- [<span data-ttu-id="0e7fb-125">文档约定</span><span class="sxs-lookup"><span data-stu-id="0e7fb-125">Document Conventions</span></span>](http://msdn.microsoft.com/zh-cn/office/aa905365.aspx)   
- [<span data-ttu-id="0e7fb-126">Microsoft 产品中的辅助功能</span><span class="sxs-lookup"><span data-stu-id="0e7fb-126">Accessibility in Microsoft Products</span></span>](http://www.microsoft.com/enable/products/default.aspx)  
- [<span data-ttu-id="0e7fb-127">Microsoft 联机隐私声明</span><span class="sxs-lookup"><span data-stu-id="0e7fb-127">Microsoft Online Privacy Notice</span></span>](https://privacy.microsoft.com/en-us/privacystatement)
    

