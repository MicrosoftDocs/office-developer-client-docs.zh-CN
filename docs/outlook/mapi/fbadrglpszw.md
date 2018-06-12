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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: da31da0ae0437e1578a681d9232b0693932b2aec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774905"
---
# <a name="fbadrglpszw"></a><span data-ttu-id="4761e-103">FBadRglpszW</span><span class="sxs-lookup"><span data-stu-id="4761e-103">FBadRglpszW</span></span>

  
  
<span data-ttu-id="4761e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4761e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4761e-105">验证的 Unicode 字符串数组中的所有字符串。</span><span class="sxs-lookup"><span data-stu-id="4761e-105">Validates all strings in an array of Unicode strings.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4761e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4761e-106">Header file:</span></span>  <br/> |<span data-ttu-id="4761e-107">Mapival.h</span><span class="sxs-lookup"><span data-stu-id="4761e-107">Mapival.h</span></span>  <br/> |
|<span data-ttu-id="4761e-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="4761e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="4761e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="4761e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="4761e-110">调用：</span><span class="sxs-lookup"><span data-stu-id="4761e-110">Called by:</span></span>  <br/> |<span data-ttu-id="4761e-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="4761e-111">Service providers</span></span>  <br/> |
   
```cpp
BOOL FBadRglpszW(
  LPWSTR FAR * lppszW,
  ULONG cStrings
);
```

## <a name="parameters"></a><span data-ttu-id="4761e-112">参数</span><span class="sxs-lookup"><span data-stu-id="4761e-112">Parameters</span></span>

 <span data-ttu-id="4761e-113">_lppszW_</span><span class="sxs-lookup"><span data-stu-id="4761e-113">_lppszW_</span></span>
  
> <span data-ttu-id="4761e-114">[in]指向 null 结尾的 Unicode 字符串数组。</span><span class="sxs-lookup"><span data-stu-id="4761e-114">[in] Pointer to an array of null-terminated Unicode strings.</span></span> 
    
 <span data-ttu-id="4761e-115">_Cstring_</span><span class="sxs-lookup"><span data-stu-id="4761e-115">_cStrings_</span></span>
  
> <span data-ttu-id="4761e-116">[in]由_lppszW_参数指向的字符串数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="4761e-116">[in] Count of strings in the array pointed to by the  _lppszW_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="4761e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="4761e-117">Return value</span></span>

<span data-ttu-id="4761e-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="4761e-118">TRUE</span></span> 
  
> <span data-ttu-id="4761e-119">一个或多个指定的数组中的字符串是无效。</span><span class="sxs-lookup"><span data-stu-id="4761e-119">One or more of the strings in the specified array are invalid.</span></span> 
    
<span data-ttu-id="4761e-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="4761e-120">FALSE</span></span> 
  
> <span data-ttu-id="4761e-121">指定数组中的字符串是有效的。</span><span class="sxs-lookup"><span data-stu-id="4761e-121">The strings in the specified array are valid.</span></span>
    

