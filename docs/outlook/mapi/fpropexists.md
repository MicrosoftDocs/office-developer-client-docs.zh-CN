---
title: FPropExists
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FPropExists
api_type:
- COM
ms.assetid: 33c00752-cdc1-4cbe-8fca-6b06c78bd362
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d016c83678d9c1c94ee4ad4b8e12723c03f7bda
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570434"
---
# <a name="fpropexists"></a><span data-ttu-id="259e5-103">FPropExists</span><span class="sxs-lookup"><span data-stu-id="259e5-103">FPropExists</span></span>

  
  
<span data-ttu-id="259e5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="259e5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="259e5-105">从**IMAPIProp**，如[IMessage](imessageimapiprop.md)或[IMAPIFolder](imapifolderimapicontainer.md)派生给定的属性标记[IMAPIProp](imapipropiunknown.md)接口或接口中的搜索。</span><span class="sxs-lookup"><span data-stu-id="259e5-105">Searches for a given property tag in an [IMAPIProp](imapipropiunknown.md) interface or an interface derived from **IMAPIProp**, such as [IMessage](imessageimapiprop.md) or [IMAPIFolder](imapifolderimapicontainer.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="259e5-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="259e5-106">Header file:</span></span>  <br/> |<span data-ttu-id="259e5-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="259e5-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="259e5-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="259e5-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="259e5-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="259e5-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="259e5-110">调用：</span><span class="sxs-lookup"><span data-stu-id="259e5-110">Called by:</span></span>  <br/> |<span data-ttu-id="259e5-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="259e5-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FPropExists(
  LPMAPIPROP pobj,
  ULONG ulPropTag
);
```

## <a name="parameters"></a><span data-ttu-id="259e5-112">参数</span><span class="sxs-lookup"><span data-stu-id="259e5-112">Parameters</span></span>

 <span data-ttu-id="259e5-113">_pobj_</span><span class="sxs-lookup"><span data-stu-id="259e5-113">_pobj_</span></span>
  
> <span data-ttu-id="259e5-114">[in]指向**IMAPIProp**接口或派生自**IMAPIProp**在其中搜索属性标记的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="259e5-114">[in] Pointer to the **IMAPIProp** interface or interface derived from **IMAPIProp** within which to search for the property tag.</span></span> 
    
 <span data-ttu-id="259e5-115">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="259e5-115">_ulPropTag_</span></span>
  
> <span data-ttu-id="259e5-116">[in]要搜索的属性标记。</span><span class="sxs-lookup"><span data-stu-id="259e5-116">[in] Property tag for which to search.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="259e5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="259e5-117">Return value</span></span>

<span data-ttu-id="259e5-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="259e5-118">TRUE</span></span> 
  
> <span data-ttu-id="259e5-119">找到给定的属性标记匹配。</span><span class="sxs-lookup"><span data-stu-id="259e5-119">A match for the given property tag was found.</span></span> 
    
<span data-ttu-id="259e5-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="259e5-120">FALSE</span></span> 
  
> <span data-ttu-id="259e5-121">找不到给定的属性标记匹配。</span><span class="sxs-lookup"><span data-stu-id="259e5-121">A match for the given property tag was not found.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="259e5-122">注解</span><span class="sxs-lookup"><span data-stu-id="259e5-122">Remarks</span></span>

<span data-ttu-id="259e5-123">如果_ulPropTag_参数中的属性标记具有类型 PT_UNSPECIFIED， **FPropExists**函数查找匹配仅根据属性标识符。</span><span class="sxs-lookup"><span data-stu-id="259e5-123">If the property tag in the  _ulPropTag_ parameter has type PT_UNSPECIFIED, the **FPropExists** function looks for a match based only on the property identifier.</span></span> <span data-ttu-id="259e5-124">否则，匹配是整个属性标记，包括类型。</span><span class="sxs-lookup"><span data-stu-id="259e5-124">Otherwise, the match is for the entire property tag, including the type.</span></span> 
  

