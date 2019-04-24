---
title: FBadRglpszW
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBadRglpszW
api_type:
- COM
ms.assetid: 880eb35d-7045-4fdd-bb33-0f14557a7316
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ca436bc83d5170d55475c1dd9702a9d54e4b9d5a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341053"
---
# <a name="fbadrglpszw"></a><span data-ttu-id="517b2-103">FBadRglpszW</span><span class="sxs-lookup"><span data-stu-id="517b2-103">FBadRglpszW</span></span>

  
  
<span data-ttu-id="517b2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="517b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="517b2-105">验证 Unicode 字符串数组中的所有字符串。</span><span class="sxs-lookup"><span data-stu-id="517b2-105">Validates all strings in an array of Unicode strings.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="517b2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="517b2-106">Header file:</span></span>  <br/> |<span data-ttu-id="517b2-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="517b2-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="517b2-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="517b2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="517b2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="517b2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="517b2-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="517b2-110">Called by:</span></span>  <br/> |<span data-ttu-id="517b2-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="517b2-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadRglpszW(
  LPWSTR FAR * lppszW,
  ULONG cStrings
);
```

## <a name="parameters"></a><span data-ttu-id="517b2-112">参数</span><span class="sxs-lookup"><span data-stu-id="517b2-112">Parameters</span></span>

 <span data-ttu-id="517b2-113">_lppszW_</span><span class="sxs-lookup"><span data-stu-id="517b2-113">_lppszW_</span></span>
  
> <span data-ttu-id="517b2-114">实时指向以 null 结尾的 Unicode 字符串数组的指针。</span><span class="sxs-lookup"><span data-stu-id="517b2-114">[in] Pointer to an array of null-terminated Unicode strings.</span></span> 
    
 <span data-ttu-id="517b2-115">_cStrings_</span><span class="sxs-lookup"><span data-stu-id="517b2-115">_cStrings_</span></span>
  
> <span data-ttu-id="517b2-116">实时由_lppszW_参数指向的数组中的字符串计数。</span><span class="sxs-lookup"><span data-stu-id="517b2-116">[in] Count of strings in the array pointed to by the  _lppszW_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="517b2-117">返回值</span><span class="sxs-lookup"><span data-stu-id="517b2-117">Return value</span></span>

<span data-ttu-id="517b2-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="517b2-118">TRUE</span></span> 
  
> <span data-ttu-id="517b2-119">指定数组中的一个或多个字符串无效。</span><span class="sxs-lookup"><span data-stu-id="517b2-119">One or more of the strings in the specified array are invalid.</span></span> 
    
<span data-ttu-id="517b2-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="517b2-120">FALSE</span></span> 
  
> <span data-ttu-id="517b2-121">指定数组中的字符串有效。</span><span class="sxs-lookup"><span data-stu-id="517b2-121">The strings in the specified array are valid.</span></span>
    

