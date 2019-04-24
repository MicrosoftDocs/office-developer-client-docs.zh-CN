---
title: 初始化 MAPI 实用工具
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02b14285-bbef-44f2-b2a4-45d96395998a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5c5a9355e9edec28e08986ccd055fc43eec7b974
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317218"
---
# <a name="initializing-the-mapi-utilities"></a><span data-ttu-id="bccb1-103">初始化 MAPI 实用工具</span><span class="sxs-lookup"><span data-stu-id="bccb1-103">Initializing the MAPI Utilities</span></span>

  
  
<span data-ttu-id="bccb1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bccb1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bccb1-105">如果您需要使用的 MAPI 的唯一部分是实用程序, 则是在 MAPI 的 MAPIUTIL 中声明的接口和函数。H 头文件 (如**IPropData**和**ITableData** ) 不需要调用**MAPIInitialize**进行初始化。</span><span class="sxs-lookup"><span data-stu-id="bccb1-105">If the only part of MAPI that you need to use are the utilities — the interfaces and functions declared in MAPI's MAPIUTIL.H header file such as **IPropData** and **ITableData** — you do not need to call **MAPIInitialize** for initialization.</span></span> <span data-ttu-id="bccb1-106">有关详细信息, 请参阅[IPropData: IMAPIProp](ipropdataimapiprop.md)、 [ITableData: IUnknown](itabledataiunknown.md)和[MAPIInitialize](mapiinitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="bccb1-106">For more information, see [IPropData : IMAPIProp](ipropdataimapiprop.md), [ITableData : IUnknown](itabledataiunknown.md), and [MAPIInitialize](mapiinitialize.md).</span></span> <span data-ttu-id="bccb1-107">而是调用**ScInitMapiUtil**函数。</span><span class="sxs-lookup"><span data-stu-id="bccb1-107">Instead, call the **ScInitMapiUtil** function.</span></span> <span data-ttu-id="bccb1-108">有关详细信息, 请参阅[ScInitMapiUtil](scinitmapiutil.md)。</span><span class="sxs-lookup"><span data-stu-id="bccb1-108">For more information, see [ScInitMapiUtil](scinitmapiutil.md).</span></span> <span data-ttu-id="bccb1-109">**ScInitMapiUtil**使客户端应用程序能够使用需要 MAPI allocators 的实用工具函数和方法, 但这不会对其进行显式请求。</span><span class="sxs-lookup"><span data-stu-id="bccb1-109">**ScInitMapiUtil** enables client applications to use utility functions and methods that require MAPI allocators, but that do not ask for them explicitly.</span></span> 
  
<span data-ttu-id="bccb1-110">在关机时, 调用**DeinitMapiUtil**以释放连接到这些实用程序的资源。</span><span class="sxs-lookup"><span data-stu-id="bccb1-110">At shutdown time, make a call to **DeinitMapiUtil** to free resources connected to the utilities.</span></span> <span data-ttu-id="bccb1-111">请勿调用**MAPIUninitialize**。</span><span class="sxs-lookup"><span data-stu-id="bccb1-111">Do not call **MAPIUninitialize**.</span></span> <span data-ttu-id="bccb1-112">有关详细信息, 请参阅[DeinitMapiUtil](deinitmapiutil.md)和[MAPIUninitialize](mapiuninitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="bccb1-112">For more information, see [DeinitMapiUtil](deinitmapiutil.md) and [MAPIUninitialize](mapiuninitialize.md).</span></span>
  
<span data-ttu-id="bccb1-113">请注意, **ITableData**接口不支持已调用**ScInitMapiUtil**而不是**MAPIInitialize**的客户端的表通知。</span><span class="sxs-lookup"><span data-stu-id="bccb1-113">Be aware that the **ITableData** interface does not support table notifications for clients that have called **ScInitMapiUtil** rather than **MAPIInitialize**.</span></span> 
  

