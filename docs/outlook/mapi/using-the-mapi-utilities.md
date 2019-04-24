---
title: 使用 MAPI 实用工具
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5f0e5c97-5089-47cb-b604-2292b2ff945c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d8ec18ee7b80d8603266cf827f9484ee85bdb03c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329629"
---
# <a name="using-the-mapi-utilities"></a><span data-ttu-id="95879-103">使用 MAPI 实用工具</span><span class="sxs-lookup"><span data-stu-id="95879-103">Using the MAPI Utilities</span></span>

  
  
<span data-ttu-id="95879-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95879-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95879-105">MAPI 实用程序由表数据和属性数据对象以及用于支持杂项功能的各种函数组成。</span><span class="sxs-lookup"><span data-stu-id="95879-105">The MAPI utilities are made up of table data and property data objects and a variety of functions to support miscellaneous features.</span></span> <span data-ttu-id="95879-106">客户端可以只需要这些实用程序, 而无需登录到 MAPI 子系统即可与服务提供商建立连接。</span><span class="sxs-lookup"><span data-stu-id="95879-106">It is possible for a client to need only these utilities and not have to log on to the MAPI subsystem to establish a connection with service providers.</span></span> <span data-ttu-id="95879-107">如果您的客户端符合此类别, 请在初始化时调用 API 函数[ScInitMapiUtil](scinitmapiutil.md) , 而不是[MAPIInitialize](mapiinitialize.md)函数。</span><span class="sxs-lookup"><span data-stu-id="95879-107">If your client fits into this category, call the API function [ScInitMapiUtil](scinitmapiutil.md) rather than the [MAPIInitialize](mapiinitialize.md) function at initialization time.</span></span> 
  
 <span data-ttu-id="95879-108">**ScInitMapiUtil**使客户端能够使用需要 MAPI allocators 的实用工具函数, 但不会显式请求 allocators。</span><span class="sxs-lookup"><span data-stu-id="95879-108">**ScInitMapiUtil** enables clients to use utility functions that require MAPI allocators, but that do not ask for the allocators explicitly.</span></span> <span data-ttu-id="95879-109">当需要关机时, 请调用[DeinitMapiUtil](deinitmapiutil.md)以释放资源, 而不是[MAPIUninitialize](mapiuninitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="95879-109">When it is time to shut down, call [DeinitMapiUtil](deinitmapiutil.md) to free resources rather than [MAPIUninitialize](mapiuninitialize.md).</span></span> <span data-ttu-id="95879-110">从不调用**MAPIInitialize**的客户端不应调用**MAPIUninitialize**。</span><span class="sxs-lookup"><span data-stu-id="95879-110">Clients that never call **MAPIInitialize** should not call **MAPIUninitialize**.</span></span>
  
<span data-ttu-id="95879-111">如果您已调用**ScInitMapiUtil**而不是**MAPIInitialize** , 并且通过**ITableData**方法而不是使用**IMAPITable**方法使用表, 请注意, 表通知将不起作用。</span><span class="sxs-lookup"><span data-stu-id="95879-111">If you have called **ScInitMapiUtil** rather than **MAPIInitialize** and are using tables through the **ITableData** methods rather than through the **IMAPITable** methods, be aware that table notifications will not work.</span></span> <span data-ttu-id="95879-112">通知需要使用 MAPI 库和[IMAPITable: IUnknown](imapitableiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="95879-112">Notifications require the use of the MAPI libraries and [IMAPITable : IUnknown](imapitableiunknown.md).</span></span>
  

