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
ms.openlocfilehash: 0b861a11b6bc1d590225a0c99b20f8be38edfd2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436648"
---
# <a name="imapigetsession--iunknown"></a><span data-ttu-id="f307e-103">IMAPIGetSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f307e-103">IMAPIGetSession : IUnknown</span></span>

  
  
<span data-ttu-id="f307e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f307e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f307e-105">提供对与支持对象相关联的当前 MAPI 会话的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f307e-105">Provides access to the current MAPI session associated with the support object.</span></span> <span data-ttu-id="f307e-106">mapi 提供程序可以查询其 MAPI 支持对象的此接口。</span><span class="sxs-lookup"><span data-stu-id="f307e-106">MAPI Providers can query their MAPI Support Object for this interface.</span></span> <span data-ttu-id="f307e-107">有关支持对象的详细信息, 请参阅[支持对象概述](support-object-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f307e-107">For more information on support objects, see [Support Object Overview](support-object-overview.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f307e-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f307e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f307e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f307e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f307e-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f307e-110">Called by:</span></span>  <br/> |<span data-ttu-id="f307e-111">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="f307e-111">MAPI Providers</span></span>  <br/> |
|<span data-ttu-id="f307e-112">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="f307e-112">Interface identifier:</span></span>  <br/> |<span data-ttu-id="f307e-113">IID_IMAPIGetSession</span><span class="sxs-lookup"><span data-stu-id="f307e-113">IID_IMAPIGetSession</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="f307e-114">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="f307e-114">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="f307e-115">GetMAPISession</span><span class="sxs-lookup"><span data-stu-id="f307e-115">GetMAPISession</span></span>](imapigetsession-getmapisession.md) <br/> |<span data-ttu-id="f307e-116">调用以获取指向当前 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="f307e-116">Called to obtain a pointer to the current MAPI session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f307e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f307e-117">See also</span></span>



[<span data-ttu-id="f307e-118">GetMAPISession</span><span class="sxs-lookup"><span data-stu-id="f307e-118">GetMAPISession</span></span>](imapigetsession-getmapisession.md)
  
[<span data-ttu-id="f307e-119">IMAPISupport</span><span class="sxs-lookup"><span data-stu-id="f307e-119">IMAPISupport</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="f307e-120">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="f307e-120">MAPI Interfaces</span></span>](mapi-interfaces.md)
  
[<span data-ttu-id="f307e-121">支持对象概述</span><span class="sxs-lookup"><span data-stu-id="f307e-121">Support Object Overview</span></span>](support-object-overview.md)

