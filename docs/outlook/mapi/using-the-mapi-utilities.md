---
title: 使用 MAPI 实用工具
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5f0e5c97-5089-47cb-b604-2292b2ff945c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3f461d50e838aac0caee37d295ba8e86b9559bd1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779076"
---
# <a name="using-the-mapi-utilities"></a><span data-ttu-id="5ffa1-103">使用 MAPI 实用工具</span><span class="sxs-lookup"><span data-stu-id="5ffa1-103">Using the MAPI Utilities</span></span>

  
  
<span data-ttu-id="5ffa1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5ffa1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5ffa1-105">MAPI 实用程序组成的表数据属性的数据对象和各种功能，以支持 miscellaneous 功能。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-105">The MAPI utilities are made up of table data and property data objects and a variety of functions to support miscellaneous features.</span></span> <span data-ttu-id="5ffa1-106">很可能为客户端需要仅这些实用程序并不需要登录到 MAPI 子系统建立与服务提供商的连接。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-106">It is possible for a client to need only these utilities and not have to log on to the MAPI subsystem to establish a connection with service providers.</span></span> <span data-ttu-id="5ffa1-107">如果您的客户端符合此类别中，调用 API 函数[ScInitMapiUtil](scinitmapiutil.md)而不是[MAPIInitialize](mapiinitialize.md)函数在初始化时。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-107">If your client fits into this category, call the API function [ScInitMapiUtil](scinitmapiutil.md) rather than the [MAPIInitialize](mapiinitialize.md) function at initialization time.</span></span> 
  
 <span data-ttu-id="5ffa1-108">**ScInitMapiUtil**使客户端使用需要 MAPI 分配器，但的不询问的分配器明确的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-108">**ScInitMapiUtil** enables clients to use utility functions that require MAPI allocators, but that do not ask for the allocators explicitly.</span></span> <span data-ttu-id="5ffa1-109">关闭时间后，调用[DeinitMapiUtil](deinitmapiutil.md)以释放资源，而不是[MAPIUninitialize](mapiuninitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-109">When it is time to shut down, call [DeinitMapiUtil](deinitmapiutil.md) to free resources rather than [MAPIUninitialize](mapiuninitialize.md).</span></span> <span data-ttu-id="5ffa1-110">从不呼叫**MAPIInitialize**的客户端不应调用**MAPIUninitialize**。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-110">Clients that never call **MAPIInitialize** should not call **MAPIUninitialize**.</span></span>
  
<span data-ttu-id="5ffa1-111">如果以前呼叫过**ScInitMapiUtil** ，而不是**MAPIInitialize**并通过**ITableData**方法，而不通过**IMAPITable**方法使用表，请注意，表通知不起作用。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-111">If you have called **ScInitMapiUtil** rather than **MAPIInitialize** and are using tables through the **ITableData** methods rather than through the **IMAPITable** methods, be aware that table notifications will not work.</span></span> <span data-ttu-id="5ffa1-112">通知要求使用 MAPI 库和[IMAPITable: IUnknown](imapitableiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="5ffa1-112">Notifications require the use of the MAPI libraries and [IMAPITable : IUnknown](imapitableiunknown.md).</span></span>
  

