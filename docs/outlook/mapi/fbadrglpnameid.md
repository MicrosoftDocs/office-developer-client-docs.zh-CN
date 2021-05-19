---
title: FBadRglpNameID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRglpNameID
api_type:
- COM
ms.assetid: fec5d5ac-bca6-4fff-b264-45cdb6b37f55
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4eef7c0b1078cb9e7ced21e2403f0b3948362d6c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434828"
---
# <a name="fbadrglpnameid"></a><span data-ttu-id="0be7e-103">FBadRglpNameID</span><span class="sxs-lookup"><span data-stu-id="0be7e-103">FBadRglpNameID</span></span>

  
  
<span data-ttu-id="0be7e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0be7e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0be7e-105">验证描述命名属性的结构数组并验证其分配。</span><span class="sxs-lookup"><span data-stu-id="0be7e-105">Validates an array of structures that describe named properties and verifies their allocation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0be7e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0be7e-106">Header file:</span></span>  <br/> |<span data-ttu-id="0be7e-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="0be7e-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="0be7e-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="0be7e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="0be7e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="0be7e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="0be7e-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="0be7e-110">Called by:</span></span>  <br/> |<span data-ttu-id="0be7e-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="0be7e-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadRglpNameID(
  LPMAPINAMEID FAR * lppNameId,
  ULONG cNames
);
```

## <a name="parameters"></a><span data-ttu-id="0be7e-112">参数</span><span class="sxs-lookup"><span data-stu-id="0be7e-112">Parameters</span></span>

 <span data-ttu-id="0be7e-113">_lppNameId_</span><span class="sxs-lookup"><span data-stu-id="0be7e-113">_lppNameId_</span></span>
  
> <span data-ttu-id="0be7e-114">[in]指向描述命名属性 [的 MAPINAMEID](mapinameid.md) 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="0be7e-114">[in] Pointer to an array of [MAPINAMEID](mapinameid.md) structures describing the named properties.</span></span> 
    
 <span data-ttu-id="0be7e-115">_cNames_</span><span class="sxs-lookup"><span data-stu-id="0be7e-115">_cNames_</span></span>
  
> <span data-ttu-id="0be7e-116">[in]  _lppNameId_ 参数指向的数组中的命名属性结构计数。</span><span class="sxs-lookup"><span data-stu-id="0be7e-116">[in] Count of named property structures in the array pointed to by the  _lppNameId_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0be7e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="0be7e-117">Return value</span></span>

<span data-ttu-id="0be7e-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="0be7e-118">TRUE</span></span> 
  
> <span data-ttu-id="0be7e-119">一个或多个指定的属性名称结构无效。</span><span class="sxs-lookup"><span data-stu-id="0be7e-119">One or more of the specified property name structures is invalid.</span></span> 
    
<span data-ttu-id="0be7e-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="0be7e-120">FALSE</span></span> 
  
> <span data-ttu-id="0be7e-121">指定的属性名称结构均有效。</span><span class="sxs-lookup"><span data-stu-id="0be7e-121">The specified property name structures are all valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0be7e-122">备注</span><span class="sxs-lookup"><span data-stu-id="0be7e-122">Remarks</span></span>

<span data-ttu-id="0be7e-123">在设置对 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)或 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md)的调用时，可以使用 **FBadRglpNameID** 函数。</span><span class="sxs-lookup"><span data-stu-id="0be7e-123">The **FBadRglpNameID** function can be used when setting up for a call to [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) or [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md).</span></span> 
  

