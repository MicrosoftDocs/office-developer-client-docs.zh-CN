---
title: 初始化 MAPI 实用工具
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02b14285-bbef-44f2-b2a4-45d96395998a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8ee0504d4a8b9e2ce96e42a53b778d4e3f518fcc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775933"
---
# <a name="initializing-the-mapi-utilities"></a><span data-ttu-id="03818-103">初始化 MAPI 实用工具</span><span class="sxs-lookup"><span data-stu-id="03818-103">Initializing the MAPI Utilities</span></span>

  
  
<span data-ttu-id="03818-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="03818-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="03818-105">如果您需要使用 MAPI 的唯一部分都实用程序 — 接口和函数在 MAPI 的 MAPIUTIL 中声明。如**IPropData**和**ITableData** H 头文件 — 您不需要进行初始化调用**MAPIInitialize** 。</span><span class="sxs-lookup"><span data-stu-id="03818-105">If the only part of MAPI that you need to use are the utilities — the interfaces and functions declared in MAPI's MAPIUTIL.H header file such as **IPropData** and **ITableData** — you do not need to call **MAPIInitialize** for initialization.</span></span> <span data-ttu-id="03818-106">有关详细信息，请参阅[IPropData: IMAPIProp](ipropdataimapiprop.md)， [ITableData: IUnknown](itabledataiunknown.md)，和[MAPIInitialize](mapiinitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="03818-106">For more information, see [IPropData : IMAPIProp](ipropdataimapiprop.md), [ITableData : IUnknown](itabledataiunknown.md), and [MAPIInitialize](mapiinitialize.md).</span></span> <span data-ttu-id="03818-107">相反，调用**ScInitMapiUtil**函数。</span><span class="sxs-lookup"><span data-stu-id="03818-107">Instead, call the **ScInitMapiUtil** function.</span></span> <span data-ttu-id="03818-108">有关详细信息，请参阅[ScInitMapiUtil](scinitmapiutil.md)。</span><span class="sxs-lookup"><span data-stu-id="03818-108">For more information, see [ScInitMapiUtil](scinitmapiutil.md).</span></span> <span data-ttu-id="03818-109">**ScInitMapiUtil**允许客户端应用程序使用实用工具函数和需要 MAPI 分配器，但的不要求其明确的方法。</span><span class="sxs-lookup"><span data-stu-id="03818-109">**ScInitMapiUtil** enables client applications to use utility functions and methods that require MAPI allocators, but that do not ask for them explicitly.</span></span> 
  
<span data-ttu-id="03818-110">在关闭时，请调用**DeinitMapiUtil**以释放资源连接到实用程序。</span><span class="sxs-lookup"><span data-stu-id="03818-110">At shutdown time, make a call to **DeinitMapiUtil** to free resources connected to the utilities.</span></span> <span data-ttu-id="03818-111">不要调用**MAPIUninitialize**。</span><span class="sxs-lookup"><span data-stu-id="03818-111">Do not call **MAPIUninitialize**.</span></span> <span data-ttu-id="03818-112">有关详细信息，请参阅[DeinitMapiUtil](deinitmapiutil.md)和[MAPIUninitialize](mapiuninitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="03818-112">For more information, see [DeinitMapiUtil](deinitmapiutil.md) and [MAPIUninitialize](mapiuninitialize.md).</span></span>
  
<span data-ttu-id="03818-113">注意**ITableData**接口不支持的客户端的以前呼叫过**ScInitMapiUtil** ，而不是**MAPIInitialize**表通知。</span><span class="sxs-lookup"><span data-stu-id="03818-113">Be aware that the **ITableData** interface does not support table notifications for clients that have called **ScInitMapiUtil** rather than **MAPIInitialize**.</span></span> 
  

