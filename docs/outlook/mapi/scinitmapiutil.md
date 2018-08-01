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
ms.openlocfilehash: 771b466e58bf57a7eb4285c6f6ce94c815ec7288
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778693"
---
# <a name="scinitmapiutil"></a><span data-ttu-id="22e59-103">ScInitMapiUtil</span><span class="sxs-lookup"><span data-stu-id="22e59-103">ScInitMapiUtil</span></span>

  
  
<span data-ttu-id="22e59-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="22e59-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="22e59-105">当正在使用仅选择实用工具函数替换[MAPIInitialize](mapiinitialize.md) 。</span><span class="sxs-lookup"><span data-stu-id="22e59-105">Replaces [MAPIInitialize](mapiinitialize.md) when only select utility functions are being used.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="22e59-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="22e59-106">Header file:</span></span>  <br/> |<span data-ttu-id="22e59-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="22e59-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="22e59-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="22e59-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="22e59-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="22e59-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="22e59-110">调用：</span><span class="sxs-lookup"><span data-stu-id="22e59-110">Called by:</span></span>  <br/> |<span data-ttu-id="22e59-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="22e59-111">Client applications</span></span>  <br/> |
   
```cpp
SCODE ScInitMapiUtil(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="22e59-112">参数</span><span class="sxs-lookup"><span data-stu-id="22e59-112">Parameters</span></span>

 <span data-ttu-id="22e59-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="22e59-113">_ulFlags_</span></span>
  
> <span data-ttu-id="22e59-114">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="22e59-114">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="22e59-115">返回值</span><span class="sxs-lookup"><span data-stu-id="22e59-115">Return value</span></span>

<span data-ttu-id="22e59-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="22e59-116">S_OK</span></span> 
  
> <span data-ttu-id="22e59-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="22e59-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="22e59-118">说明</span><span class="sxs-lookup"><span data-stu-id="22e59-118">Remarks</span></span>

<span data-ttu-id="22e59-119">**ScInitMapiUtil**和[DeinitMapiUtil](deinitmapiutil.md)函数共同呼叫并释放选择实用工具函数，而不是[MAPIInitialize](mapiinitialize.md)，后者核心以及实用程序函数。</span><span class="sxs-lookup"><span data-stu-id="22e59-119">The **ScInitMapiUtil** and [DeinitMapiUtil](deinitmapiutil.md) functions cooperate to call and release select utility functions, as opposed to [MAPIInitialize](mapiinitialize.md), which calls core as well as utility functions.</span></span> <span data-ttu-id="22e59-120">当**ScInitMapiUtil**调用实用工具函数时，它还初始化所需的内存。</span><span class="sxs-lookup"><span data-stu-id="22e59-120">When **ScInitMapiUtil** calls utility functions, it also initializes the necessary memory.</span></span> 
  
<span data-ttu-id="22e59-121">使用的呼叫**ScInitMapiUtil**函数完成后， **DeinitMapiUtil**必须明确调用其发布。</span><span class="sxs-lookup"><span data-stu-id="22e59-121">When use of the functions that **ScInitMapiUtil** has called is complete, **DeinitMapiUtil** must be explicitly called to release them.</span></span> <span data-ttu-id="22e59-122">相比之下， **MAPIInitialize**隐式调用**DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="22e59-122">In contrast, **MAPIInitialize** implicitly calls **DeinitMapiUtil**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="22e59-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22e59-123">See also</span></span>



[<span data-ttu-id="22e59-124">MAPIUninitialize</span><span class="sxs-lookup"><span data-stu-id="22e59-124">MAPIUninitialize</span></span>](mapiuninitialize.md)

