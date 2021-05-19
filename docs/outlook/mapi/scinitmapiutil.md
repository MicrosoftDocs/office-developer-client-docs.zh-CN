---
title: ScInitMapiUtil
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ScInitMapiUtil
api_type:
- HeaderDef
ms.assetid: d83b8ea8-a3b8-4038-a226-de1869c5d722
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 090a73ed908d2a647d00de27b93538a77766c258
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420589"
---
# <a name="scinitmapiutil"></a><span data-ttu-id="6a390-103">ScInitMapiUtil</span><span class="sxs-lookup"><span data-stu-id="6a390-103">ScInitMapiUtil</span></span>

  
  
<span data-ttu-id="6a390-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a390-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a390-105">仅在使用选择实用程序函数时替换[MAPIInitialize。](mapiinitialize.md)</span><span class="sxs-lookup"><span data-stu-id="6a390-105">Replaces [MAPIInitialize](mapiinitialize.md) when only select utility functions are being used.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6a390-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6a390-106">Header file:</span></span>  <br/> |<span data-ttu-id="6a390-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="6a390-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="6a390-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="6a390-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6a390-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6a390-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6a390-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="6a390-110">Called by:</span></span>  <br/> |<span data-ttu-id="6a390-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="6a390-111">Client applications</span></span>  <br/> |
   
```cpp
SCODE ScInitMapiUtil(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="6a390-112">参数</span><span class="sxs-lookup"><span data-stu-id="6a390-112">Parameters</span></span>

 <span data-ttu-id="6a390-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6a390-113">_ulFlags_</span></span>
  
> <span data-ttu-id="6a390-114">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="6a390-114">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6a390-115">返回值</span><span class="sxs-lookup"><span data-stu-id="6a390-115">Return value</span></span>

<span data-ttu-id="6a390-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a390-116">S_OK</span></span> 
  
> <span data-ttu-id="6a390-117">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="6a390-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6a390-118">备注</span><span class="sxs-lookup"><span data-stu-id="6a390-118">Remarks</span></span>

<span data-ttu-id="6a390-119">**ScInitMapiUtil** 和 [DeinitMapiUtil](deinitmapiutil.md)函数共同调用和释放选择实用工具函数，而不是调用核心函数和实用程序函数的 [MAPIInitialize](mapiinitialize.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6a390-119">The **ScInitMapiUtil** and [DeinitMapiUtil](deinitmapiutil.md) functions cooperate to call and release select utility functions, as opposed to [MAPIInitialize](mapiinitialize.md), which calls core as well as utility functions.</span></span> <span data-ttu-id="6a390-120">当 **ScInitMapiUtil** 调用实用程序函数时，它还初始化必要的内存。</span><span class="sxs-lookup"><span data-stu-id="6a390-120">When **ScInitMapiUtil** calls utility functions, it also initializes the necessary memory.</span></span> 
  
<span data-ttu-id="6a390-121">使用 **ScInitMapiUtil** 调用的函数完成后，必须显式调用 **DeinitMapiUtil** 以释放它们。</span><span class="sxs-lookup"><span data-stu-id="6a390-121">When use of the functions that **ScInitMapiUtil** has called is complete, **DeinitMapiUtil** must be explicitly called to release them.</span></span> <span data-ttu-id="6a390-122">相比之下 **，MAPIInitialize** 隐式调用 **DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="6a390-122">In contrast, **MAPIInitialize** implicitly calls **DeinitMapiUtil**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6a390-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a390-123">See also</span></span>



[<span data-ttu-id="6a390-124">MAPIUninitialize</span><span class="sxs-lookup"><span data-stu-id="6a390-124">MAPIUninitialize</span></span>](mapiuninitialize.md)

