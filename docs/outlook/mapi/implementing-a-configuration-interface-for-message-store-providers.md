---
title: 实现邮件存储提供程序的配置接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 508e6950-d483-4cbe-b817-8016f4aa5cd8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c349a03b0be465ed1262712372b6ee17a9812abd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415885"
---
# <a name="implementing-a-configuration-interface-for-message-store-providers"></a><span data-ttu-id="26248-103">实现邮件存储提供程序的配置接口</span><span class="sxs-lookup"><span data-stu-id="26248-103">Implementing a Configuration Interface for Message Store Providers</span></span>

  
  
<span data-ttu-id="26248-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26248-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26248-105">邮件存储提供程序需要实现一个接口, 该接口允许用户将邮件存储提供程序配置为在该用户的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="26248-105">Message store providers are required to implement an interface that allows the user to configure the message store provider to run on that user's computer.</span></span> <span data-ttu-id="26248-106">通常情况下, 在将邮件存储提供程序添加到用户的配置文件中时, 会配置邮件存储区提供程序。</span><span class="sxs-lookup"><span data-stu-id="26248-106">Typically, the message store provider is configured when the message store provider is added to a user's profile.</span></span> <span data-ttu-id="26248-107">邮件存储提供程序的配置界面通常处理诸如为受保护的邮件存储区设置用户名和密码、选择必要文件的路径以及创建它将使用的基础存储机制 (如有必要) 的任务。</span><span class="sxs-lookup"><span data-stu-id="26248-107">The message store provider's configuration interface generally handles tasks such as setting user names and passwords for protected message stores, choosing paths to necessary files, and creating the underlying storage mechanism it will use, if necessary.</span></span>
  
<span data-ttu-id="26248-108">通过邮件服务提供程序的 DLL 中的其他入口点访问您实现的配置界面。</span><span class="sxs-lookup"><span data-stu-id="26248-108">The configuration interface you implement is accessed through additional entry points in your message service provider's DLL.</span></span> <span data-ttu-id="26248-109">有关详细信息, 请参阅[配置邮件服务](configuring-a-message-service.md)。</span><span class="sxs-lookup"><span data-stu-id="26248-109">For more information, see [Configuring a Message Service](configuring-a-message-service.md).</span></span> <span data-ttu-id="26248-110">邮件存储提供程序的配置界面是邮件存储提供程序必须实现的唯一用户界面。</span><span class="sxs-lookup"><span data-stu-id="26248-110">The message store provider's configuration interface is the only user interface that a message store provider must implement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="26248-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26248-111">See also</span></span>



[<span data-ttu-id="26248-112">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="26248-112">Message Store Features</span></span>](message-store-features.md)

