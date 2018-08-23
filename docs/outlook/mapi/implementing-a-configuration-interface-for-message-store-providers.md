---
title: 实现邮件存储区提供程序的配置接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 508e6950-d483-4cbe-b817-8016f4aa5cd8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 15833768fbd148ae4e689b5a80ed3479823864cb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592925"
---
# <a name="implementing-a-configuration-interface-for-message-store-providers"></a><span data-ttu-id="d2998-103">实现邮件存储区提供程序的配置接口</span><span class="sxs-lookup"><span data-stu-id="d2998-103">Implementing a Configuration Interface for Message Store Providers</span></span>

  
  
<span data-ttu-id="d2998-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d2998-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d2998-105">消息存储提供程序所需实现允许用户配置要在该用户的计算机上运行的消息存储提供程序的接口。</span><span class="sxs-lookup"><span data-stu-id="d2998-105">Message store providers are required to implement an interface that allows the user to configure the message store provider to run on that user's computer.</span></span> <span data-ttu-id="d2998-106">通常情况下，消息存储提供程序配置的消息存储提供程序添加到用户的配置文件时。</span><span class="sxs-lookup"><span data-stu-id="d2998-106">Typically, the message store provider is configured when the message store provider is added to a user's profile.</span></span> <span data-ttu-id="d2998-107">消息存储提供程序的配置界面通常处理任务，例如用户名和密码的受保护的邮件存储区中，选择所需文件的路径设置并创建基础存储机制它将使用，如有必要。</span><span class="sxs-lookup"><span data-stu-id="d2998-107">The message store provider's configuration interface generally handles tasks such as setting user names and passwords for protected message stores, choosing paths to necessary files, and creating the underlying storage mechanism it will use, if necessary.</span></span>
  
<span data-ttu-id="d2998-108">您实现配置界面来访问邮件服务提供商的 DLL 中的其他入口点。</span><span class="sxs-lookup"><span data-stu-id="d2998-108">The configuration interface you implement is accessed through additional entry points in your message service provider's DLL.</span></span> <span data-ttu-id="d2998-109">有关详细信息，请参阅[配置邮件服务](configuring-a-message-service.md)。</span><span class="sxs-lookup"><span data-stu-id="d2998-109">For more information, see [Configuring a Message Service](configuring-a-message-service.md).</span></span> <span data-ttu-id="d2998-110">消息存储提供程序的配置接口是消息存储提供程序必须实现的唯一用户界面。</span><span class="sxs-lookup"><span data-stu-id="d2998-110">The message store provider's configuration interface is the only user interface that a message store provider must implement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2998-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2998-111">See also</span></span>



[<span data-ttu-id="d2998-112">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="d2998-112">Message Store Features</span></span>](message-store-features.md)

