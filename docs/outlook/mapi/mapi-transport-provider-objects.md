---
title: MAPI 传输提供程序对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4f28fab8-2ce1-4398-a941-6d718c9bbd6a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: de0334ee9a90da38e472571314136195c84a7866
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592701"
---
# <a name="mapi-transport-provider-objects"></a><span data-ttu-id="45518-103">MAPI 传输提供程序对象</span><span class="sxs-lookup"><span data-stu-id="45518-103">MAPI transport provider objects</span></span>
  
<span data-ttu-id="45518-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="45518-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="45518-105">标准提供程序和所有服务提供程序都实现的登录对象中，除了传输提供程序实现所需状态对象。</span><span class="sxs-lookup"><span data-stu-id="45518-105">In addition to the standard provider and logon objects implemented by all service providers, transport providers are required to implement a status object.</span></span> <span data-ttu-id="45518-106">对于其他服务提供程序类型，实现状态对象是可选的。</span><span class="sxs-lookup"><span data-stu-id="45518-106">For the other service provider types, implementing a status object is optional.</span></span> <span data-ttu-id="45518-107">但是，MAPI 要求其传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="45518-107">However, MAPI requires it for transport providers.</span></span> <span data-ttu-id="45518-108">支持下载邮件头从远程服务器的传输提供程序还实现文件夹和表。</span><span class="sxs-lookup"><span data-stu-id="45518-108">Transport providers that support the downloading of message headers from a remote server also implement a folder and a table.</span></span> 
  
<span data-ttu-id="45518-109">下图显示了每个传输提供程序可以实现与及其相应的接口的对象。</span><span class="sxs-lookup"><span data-stu-id="45518-109">The following illustration shows each of the objects that transport providers can implement with their corresponding interfaces.</span></span> <span data-ttu-id="45518-110">图还指示 MAPI 或客户端是否对象的用户。</span><span class="sxs-lookup"><span data-stu-id="45518-110">The illustration also indicates whether MAPI or a client is the object's user.</span></span>
  
<span data-ttu-id="45518-111">![传输提供程序实现的对象](media/amapi_66.gif "传输提供程序实现的对象")</span><span class="sxs-lookup"><span data-stu-id="45518-111">![Objects that transport providers implement](media/amapi_66.gif "Objects that transport providers implement")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45518-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45518-112">See also</span></span>

- [<span data-ttu-id="45518-113">MAPI 服务提供商对象</span><span class="sxs-lookup"><span data-stu-id="45518-113">MAPI Service Provider Objects</span></span>](mapi-service-provider-objects.md)

