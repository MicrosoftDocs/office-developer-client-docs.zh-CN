---
title: 邮件服务实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb529cc7-ad09-4f86-89bc-0e8ad29a3f38
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c7007c01803676412b3efca8b7825b2ed8d863e6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582481"
---
# <a name="message-service-implementation"></a><span data-ttu-id="67326-103">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="67326-103">Message Service Implementation</span></span>

  
  
<span data-ttu-id="67326-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67326-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67326-105">消息服务是组合在一起以简化安装和配置的一个或多个相关的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="67326-105">A message service is one or more related service providers grouped together for the purpose of simplifying installation and configuration.</span></span> <span data-ttu-id="67326-106">所有服务提供程序应都包含在邮件服务。</span><span class="sxs-lookup"><span data-stu-id="67326-106">All service providers should be included in a message service.</span></span>
  
<span data-ttu-id="67326-107">若要实现与一个或多个提供程序的消息服务，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="67326-107">To implement a message service with one or more providers, use the following procedure:</span></span>
  
1. <span data-ttu-id="67326-108">设计邮件服务，确定的数量和要包括的服务提供商的类型。</span><span class="sxs-lookup"><span data-stu-id="67326-108">Design the message service, determining the number and type of service providers to be included.</span></span> <span data-ttu-id="67326-109">有关如何设计的消息服务的详细信息，请参阅[Designing 消息服务](designing-a-message-service.md)。</span><span class="sxs-lookup"><span data-stu-id="67326-109">For more information about how to design a message service, see [Designing a Message Service](designing-a-message-service.md).</span></span>
    
2. <span data-ttu-id="67326-110">创建用于消息服务中安装的服务提供程序安装程序。</span><span class="sxs-lookup"><span data-stu-id="67326-110">Create a setup program to install the service providers in the message service.</span></span> <span data-ttu-id="67326-111">有关编写消息服务安装程序的详细信息，请参阅[支持的消息服务安装](supporting-message-service-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="67326-111">For more information about writing a message service setup program, see [Supporting Message Service Installation](supporting-message-service-installation.md).</span></span> 
    
3. <span data-ttu-id="67326-112">创建执行配置入口点函数。</span><span class="sxs-lookup"><span data-stu-id="67326-112">Create an entry point function to perform configuration.</span></span> <span data-ttu-id="67326-113">有关写入消息服务的条目的详细信息指向函数，请参阅[支持的消息服务配置](supporting-message-service-configuration.md)和[MSGSERVICEENTRY](msgserviceentry.md)。</span><span class="sxs-lookup"><span data-stu-id="67326-113">For more information about writing a message service entry point function, see [Supporting Message Service Configuration](supporting-message-service-configuration.md) and [MSGSERVICEENTRY](msgserviceentry.md).</span></span> 
    
4. <span data-ttu-id="67326-114">创建公共头文件包含属性标记和消息服务支持的任何自定义属性的有效值的说明。</span><span class="sxs-lookup"><span data-stu-id="67326-114">Create a public header file that contains the property tags and descriptions of valid values for any custom properties that the message service supports.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="67326-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67326-115">See also</span></span>



[<span data-ttu-id="67326-116">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="67326-116">MAPI Service Providers</span></span>](mapi-service-providers.md)

