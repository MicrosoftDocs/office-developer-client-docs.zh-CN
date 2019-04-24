---
title: 邮件服务实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb529cc7-ad09-4f86-89bc-0e8ad29a3f38
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ef3820afbd4ae7ff04a3f54071e56f4e0a856109
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356915"
---
# <a name="message-service-implementation"></a><span data-ttu-id="4a07f-103">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="4a07f-103">Message Service Implementation</span></span>

  
  
<span data-ttu-id="4a07f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a07f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a07f-105">邮件服务是一个或多个相关的服务提供商, 旨在简化安装和配置。</span><span class="sxs-lookup"><span data-stu-id="4a07f-105">A message service is one or more related service providers grouped together for the purpose of simplifying installation and configuration.</span></span> <span data-ttu-id="4a07f-106">所有服务提供商应包含在邮件服务中。</span><span class="sxs-lookup"><span data-stu-id="4a07f-106">All service providers should be included in a message service.</span></span>
  
<span data-ttu-id="4a07f-107">若要为一个或多个提供程序实现消息服务, 请使用以下过程:</span><span class="sxs-lookup"><span data-stu-id="4a07f-107">To implement a message service with one or more providers, use the following procedure:</span></span>
  
1. <span data-ttu-id="4a07f-108">设计邮件服务, 以确定要包括的服务提供程序的数量和类型。</span><span class="sxs-lookup"><span data-stu-id="4a07f-108">Design the message service, determining the number and type of service providers to be included.</span></span> <span data-ttu-id="4a07f-109">有关如何设计邮件服务的详细信息, 请参阅[设计邮件服务](designing-a-message-service.md)。</span><span class="sxs-lookup"><span data-stu-id="4a07f-109">For more information about how to design a message service, see [Designing a Message Service](designing-a-message-service.md).</span></span>
    
2. <span data-ttu-id="4a07f-110">创建安装程序以在邮件服务中安装服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="4a07f-110">Create a setup program to install the service providers in the message service.</span></span> <span data-ttu-id="4a07f-111">有关编写邮件服务安装程序的详细信息, 请参阅[支持邮件服务安装](supporting-message-service-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="4a07f-111">For more information about writing a message service setup program, see [Supporting Message Service Installation](supporting-message-service-installation.md).</span></span> 
    
3. <span data-ttu-id="4a07f-112">创建用于执行配置的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="4a07f-112">Create an entry point function to perform configuration.</span></span> <span data-ttu-id="4a07f-113">有关编写邮件服务入口点函数的详细信息, 请参阅[支持邮件服务配置](supporting-message-service-configuration.md)和[MSGSERVICEENTRY](msgserviceentry.md)。</span><span class="sxs-lookup"><span data-stu-id="4a07f-113">For more information about writing a message service entry point function, see [Supporting Message Service Configuration](supporting-message-service-configuration.md) and [MSGSERVICEENTRY](msgserviceentry.md).</span></span> 
    
4. <span data-ttu-id="4a07f-114">创建一个公共头文件, 其中包含对邮件服务支持的任何自定义属性的有效值的属性标签和有效值说明。</span><span class="sxs-lookup"><span data-stu-id="4a07f-114">Create a public header file that contains the property tags and descriptions of valid values for any custom properties that the message service supports.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="4a07f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a07f-115">See also</span></span>



[<span data-ttu-id="4a07f-116">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="4a07f-116">MAPI Service Providers</span></span>](mapi-service-providers.md)

