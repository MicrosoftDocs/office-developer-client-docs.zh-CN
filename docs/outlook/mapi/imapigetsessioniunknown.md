---
title: IMAPIGetSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIGetSession
api_type:
- COM
ms.assetid: d1b662e2-1516-46b2-ba94-4092d79b5a39
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 90fe316bfd11d712f02187b6a569450b747a6409
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587927"
---
# <a name="imapigetsession--iunknown"></a><span data-ttu-id="b5496-103">IMAPIGetSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b5496-103">IMAPIGetSession : IUnknown</span></span>

  
  
<span data-ttu-id="b5496-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b5496-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b5496-105">提供对当前的 MAPI 会话与支持对象关联的访问。</span><span class="sxs-lookup"><span data-stu-id="b5496-105">Provides access to the current MAPI session associated with the support object.</span></span> <span data-ttu-id="b5496-106">MAPI 提供程序可以查询该接口其 MAPI 支持对象。</span><span class="sxs-lookup"><span data-stu-id="b5496-106">MAPI Providers can query their MAPI Support Object for this interface.</span></span> <span data-ttu-id="b5496-107">支持对象的详细信息，请参阅[支持对象概述](support-object-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b5496-107">For more information on support objects, see [Support Object Overview](support-object-overview.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b5496-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="b5496-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b5496-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b5496-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b5496-110">调用：</span><span class="sxs-lookup"><span data-stu-id="b5496-110">Called by:</span></span>  <br/> |<span data-ttu-id="b5496-111">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="b5496-111">MAPI Providers</span></span>  <br/> |
|<span data-ttu-id="b5496-112">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="b5496-112">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b5496-113">IID_IMAPIGetSession</span><span class="sxs-lookup"><span data-stu-id="b5496-113">IID_IMAPIGetSession</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b5496-114">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="b5496-114">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="b5496-115">GetMAPISession</span><span class="sxs-lookup"><span data-stu-id="b5496-115">GetMAPISession</span></span>](imapigetsession-getmapisession.md) <br/> |<span data-ttu-id="b5496-116">调用来获取当前的 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="b5496-116">Called to obtain a pointer to the current MAPI session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b5496-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5496-117">See also</span></span>



[<span data-ttu-id="b5496-118">GetMAPISession</span><span class="sxs-lookup"><span data-stu-id="b5496-118">GetMAPISession</span></span>](imapigetsession-getmapisession.md)
  
[<span data-ttu-id="b5496-119">IMAPISupport</span><span class="sxs-lookup"><span data-stu-id="b5496-119">IMAPISupport</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="b5496-120">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="b5496-120">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="b5496-121">支持对象概述</span><span class="sxs-lookup"><span data-stu-id="b5496-121">Support Object Overview</span></span>](support-object-overview.md)

