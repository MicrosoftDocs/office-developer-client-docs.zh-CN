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
ms.openlocfilehash: 3f04c5be240f63d35ea8dba0f7abbf1085f2a41d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774903"
---
# <a name="fbadrglpnameid"></a><span data-ttu-id="79841-103">FBadRglpNameID</span><span class="sxs-lookup"><span data-stu-id="79841-103">FBadRglpNameID</span></span>

  
  
<span data-ttu-id="79841-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="79841-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="79841-105">验证数组介绍命名属性的结构，并验证其分配。</span><span class="sxs-lookup"><span data-stu-id="79841-105">Validates an array of structures that describe named properties and verifies their allocation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="79841-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="79841-106">Header file:</span></span>  <br/> |<span data-ttu-id="79841-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="79841-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="79841-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="79841-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="79841-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="79841-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="79841-110">调用：</span><span class="sxs-lookup"><span data-stu-id="79841-110">Called by:</span></span>  <br/> |<span data-ttu-id="79841-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="79841-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadRglpNameID(
  LPMAPINAMEID FAR * lppNameId,
  ULONG cNames
);
```

## <a name="parameters"></a><span data-ttu-id="79841-112">参数</span><span class="sxs-lookup"><span data-stu-id="79841-112">Parameters</span></span>

 <span data-ttu-id="79841-113">_lppNameId_</span><span class="sxs-lookup"><span data-stu-id="79841-113">_lppNameId_</span></span>
  
> <span data-ttu-id="79841-114">[in]指向[MAPINAMEID](mapinameid.md)结构描述命名的属性的数组。</span><span class="sxs-lookup"><span data-stu-id="79841-114">[in] Pointer to an array of [MAPINAMEID](mapinameid.md) structures describing the named properties.</span></span> 
    
 <span data-ttu-id="79841-115">_Cname_</span><span class="sxs-lookup"><span data-stu-id="79841-115">_cNames_</span></span>
  
> <span data-ttu-id="79841-116">[in]由_lppNameId_参数指向的数组中的命名的属性结构的计数。</span><span class="sxs-lookup"><span data-stu-id="79841-116">[in] Count of named property structures in the array pointed to by the  _lppNameId_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="79841-117">返回值</span><span class="sxs-lookup"><span data-stu-id="79841-117">Return value</span></span>

<span data-ttu-id="79841-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="79841-118">TRUE</span></span> 
  
> <span data-ttu-id="79841-119">一个或多个指定的属性名称结构无效。</span><span class="sxs-lookup"><span data-stu-id="79841-119">One or more of the specified property name structures is invalid.</span></span> 
    
<span data-ttu-id="79841-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="79841-120">FALSE</span></span> 
  
> <span data-ttu-id="79841-121">指定的属性名称结构均有效。</span><span class="sxs-lookup"><span data-stu-id="79841-121">The specified property name structures are all valid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="79841-122">说明</span><span class="sxs-lookup"><span data-stu-id="79841-122">Remarks</span></span>

<span data-ttu-id="79841-123">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)或[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)设置时，可以使用**FBadRglpNameID**函数。</span><span class="sxs-lookup"><span data-stu-id="79841-123">The **FBadRglpNameID** function can be used when setting up for a call to [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) or [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md).</span></span> 
  

