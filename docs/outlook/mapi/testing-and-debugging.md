---
title: 测试和调试
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0afceb1f-9086-4cc9-8ce4-fb9256a81a9c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8e1f15ae354894aede4e8418e6428d0524ccb70d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316480"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="d65b8-103">测试和调试</span><span class="sxs-lookup"><span data-stu-id="d65b8-103">Testing and Debugging</span></span>

  
  
<span data-ttu-id="d65b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d65b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d65b8-105">测试策略将根据您是否在开发客户端或服务提供程序而有所不同。</span><span class="sxs-lookup"><span data-stu-id="d65b8-105">Testing strategies differ depending on whether you are developing a client or service provider.</span></span> <span data-ttu-id="d65b8-106">由于客户端应用程序需要一个或多个服务提供程序才能运行, 因此应在具有不同的服务提供程序集的环境中测试客户端。</span><span class="sxs-lookup"><span data-stu-id="d65b8-106">Because a client application requires one or more service providers to operate, clients should be tested in an environment with different sets of service providers.</span></span>
  
<span data-ttu-id="d65b8-107">但是, 服务提供程序应在与其他提供程序集成之前在隔离中进行测试。</span><span class="sxs-lookup"><span data-stu-id="d65b8-107">Service providers, however, should be tested in isolation before being integrated with other providers.</span></span> <span data-ttu-id="d65b8-108">MAPI 提供的工具旨在测试特定类型的服务提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="d65b8-108">MAPI provides tools that are meant to test the features of a service provider of a particular type.</span></span> <span data-ttu-id="d65b8-109">[MFCMAPI](https://go.microsoft.com/fwlink/?LinkId=124154)示例应用程序演示如何测试通讯簿提供程序的功能, 以及如何与邮件存储提供程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="d65b8-109">The [MFCMAPI](https://go.microsoft.com/fwlink/?LinkId=124154) sample application shows how to test the features of an address book provider and works with a message store provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d65b8-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d65b8-110">See also</span></span>



[<span data-ttu-id="d65b8-111">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="d65b8-111">MAPI Programming Overview</span></span>](mapi-programming-overview.md)
  
[<span data-ttu-id="d65b8-112">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d65b8-112">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

