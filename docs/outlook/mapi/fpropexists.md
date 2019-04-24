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
ms.openlocfilehash: 7190065c687524302bae362a2e25d3848e17d1bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327270"
---
# <a name="fpropexists"></a><span data-ttu-id="d643a-103">FPropExists</span><span class="sxs-lookup"><span data-stu-id="d643a-103">FPropExists</span></span>

  
  
<span data-ttu-id="d643a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d643a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d643a-105">在[IMAPIProp](imapipropiunknown.md)接口或从**IMAPIProp**派生的接口 (如[IMessage](imessageimapiprop.md)或[IMAPIFolder](imapifolderimapicontainer.md)) 中搜索给定的属性标记。</span><span class="sxs-lookup"><span data-stu-id="d643a-105">Searches for a given property tag in an [IMAPIProp](imapipropiunknown.md) interface or an interface derived from **IMAPIProp**, such as [IMessage](imessageimapiprop.md) or [IMAPIFolder](imapifolderimapicontainer.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d643a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d643a-106">Header file:</span></span>  <br/> |<span data-ttu-id="d643a-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="d643a-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d643a-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d643a-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d643a-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d643a-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d643a-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d643a-110">Called by:</span></span>  <br/> |<span data-ttu-id="d643a-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d643a-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FPropExists(
  LPMAPIPROP pobj,
  ULONG ulPropTag
);
```

## <a name="parameters"></a><span data-ttu-id="d643a-112">参数</span><span class="sxs-lookup"><span data-stu-id="d643a-112">Parameters</span></span>

 <span data-ttu-id="d643a-113">_pobj_</span><span class="sxs-lookup"><span data-stu-id="d643a-113">_pobj_</span></span>
  
> <span data-ttu-id="d643a-114">实时指向从**IMAPIProp**派生的**IMAPIProp**接口或接口的指针, 可在其中搜索属性标记。</span><span class="sxs-lookup"><span data-stu-id="d643a-114">[in] Pointer to the **IMAPIProp** interface or interface derived from **IMAPIProp** within which to search for the property tag.</span></span> 
    
 <span data-ttu-id="d643a-115">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="d643a-115">_ulPropTag_</span></span>
  
> <span data-ttu-id="d643a-116">实时要搜索的属性标记。</span><span class="sxs-lookup"><span data-stu-id="d643a-116">[in] Property tag for which to search.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d643a-117">返回值</span><span class="sxs-lookup"><span data-stu-id="d643a-117">Return value</span></span>

<span data-ttu-id="d643a-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="d643a-118">TRUE</span></span> 
  
> <span data-ttu-id="d643a-119">找到给定属性标记的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d643a-119">A match for the given property tag was found.</span></span> 
    
<span data-ttu-id="d643a-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="d643a-120">FALSE</span></span> 
  
> <span data-ttu-id="d643a-121">找不到给定属性标记的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d643a-121">A match for the given property tag was not found.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d643a-122">注解</span><span class="sxs-lookup"><span data-stu-id="d643a-122">Remarks</span></span>

<span data-ttu-id="d643a-123">如果_ulPropTag_参数中的属性标记具有类型 PT_UNSPECIFIED, 则**FPropExists**函数将基于属性标识符查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="d643a-123">If the property tag in the  _ulPropTag_ parameter has type PT_UNSPECIFIED, the **FPropExists** function looks for a match based only on the property identifier.</span></span> <span data-ttu-id="d643a-124">否则, 将对整个属性标记 (包括类型) 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="d643a-124">Otherwise, the match is for the entire property tag, including the type.</span></span> 
  

