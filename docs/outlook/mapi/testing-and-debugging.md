---
title: 测试和调试
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0afceb1f-9086-4cc9-8ce4-fb9256a81a9c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ae9b49717fd7981d653e9852ed02d50bef7c7846
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590685"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="04e5e-103">测试和调试</span><span class="sxs-lookup"><span data-stu-id="04e5e-103">Testing and Debugging</span></span>

  
  
<span data-ttu-id="04e5e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="04e5e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="04e5e-105">测试策略不同，具体取决于是否正在开发的客户端或服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="04e5e-105">Testing strategies differ depending on whether you are developing a client or service provider.</span></span> <span data-ttu-id="04e5e-106">因为客户端应用程序需要一个或多个服务提供商进行操作，则应具有不同的服务提供程序集的环境中测试客户端。</span><span class="sxs-lookup"><span data-stu-id="04e5e-106">Because a client application requires one or more service providers to operate, clients should be tested in an environment with different sets of service providers.</span></span>
  
<span data-ttu-id="04e5e-107">但是，应在之前要与其他提供程序集成的隔离中测试服务提供商。</span><span class="sxs-lookup"><span data-stu-id="04e5e-107">Service providers, however, should be tested in isolation before being integrated with other providers.</span></span> <span data-ttu-id="04e5e-108">MAPI 提供了为了测试特定类型的服务提供程序的功能的工具。</span><span class="sxs-lookup"><span data-stu-id="04e5e-108">MAPI provides tools that are meant to test the features of a service provider of a particular type.</span></span> <span data-ttu-id="04e5e-109">[MFCMAPI](http://go.microsoft.com/fwlink/?LinkId=124154)示例应用程序演示如何测试通讯簿提供程序的功能和适用于一条消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="04e5e-109">The [MFCMAPI](http://go.microsoft.com/fwlink/?LinkId=124154) sample application shows how to test the features of an address book provider and works with a message store provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="04e5e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04e5e-110">See also</span></span>



[<span data-ttu-id="04e5e-111">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="04e5e-111">MAPI Programming Overview</span></span>](mapi-programming-overview.md)
  
[<span data-ttu-id="04e5e-112">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="04e5e-112">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

