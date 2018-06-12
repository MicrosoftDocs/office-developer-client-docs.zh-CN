---
title: MNLS_lstrcmpW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d26c59d7-c839-426f-8693-727fc6bef67e
description: 上次修改时间： 2012 年 6 月 18 日
ms.openlocfilehash: 8ffd3c8337edcd96af6c3c4e425d274b21fee9f6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776513"
---
# <a name="mnlslstrcmpw"></a><span data-ttu-id="f1c86-103">MNLS_lstrcmpW</span><span class="sxs-lookup"><span data-stu-id="f1c86-103">MNLS_lstrcmpW</span></span>

 
  
<span data-ttu-id="f1c86-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f1c86-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f1c86-105">比较两个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="f1c86-105">Compares two Unicode strings.</span></span>
  
```cpp
int MNLS_lstrcmpW(
  LPCWSTR lpString1,
  LPCWSTR lpString2);
```

## <a name="parameters"></a><span data-ttu-id="f1c86-106">参数</span><span class="sxs-lookup"><span data-stu-id="f1c86-106">Parameters</span></span>

 <span data-ttu-id="f1c86-107">_lpString1_</span><span class="sxs-lookup"><span data-stu-id="f1c86-107">_lpString1_</span></span>
  
> <span data-ttu-id="f1c86-108">[in]指向要比较的第一个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="f1c86-108">[in] Pointer to the first Unicode string to compare.</span></span>
    
 <span data-ttu-id="f1c86-109">_lpString2_</span><span class="sxs-lookup"><span data-stu-id="f1c86-109">_lpString2_</span></span>
  
> <span data-ttu-id="f1c86-110">[in]指向要比较的第二个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="f1c86-110">[in] Pointer to the second Unicode string to compare.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f1c86-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f1c86-111">Return value</span></span>

<span data-ttu-id="f1c86-112">返回到除 CSTR_EQUAL **MNLS_CompareStringW**等效呼叫的描述的值。</span><span class="sxs-lookup"><span data-stu-id="f1c86-112">Returns the values described for an equivalent call to **MNLS_CompareStringW** except for CSTR_EQUAL.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="f1c86-113">备注</span><span class="sxs-lookup"><span data-stu-id="f1c86-113">Remarks</span></span>

 <span data-ttu-id="f1c86-114">_MNLS_lstrcmpW_通过调用[MNLS_CompareStringW](mnls_comparestringw.md)与 GetUserDefaultLCID，用于标志，0 的区域设置执行比较和 cch1 和 cch2-1。</span><span class="sxs-lookup"><span data-stu-id="f1c86-114">_MNLS_lstrcmpW_ performs a comparison by calling [MNLS_CompareStringW](mnls_comparestringw.md) with a locale of GetUserDefaultLCID, 0 for flags, and -1 for cch1 and cch2.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f1c86-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c86-115">See also</span></span>



[<span data-ttu-id="f1c86-116">GetUserDefaultLCID</span><span class="sxs-lookup"><span data-stu-id="f1c86-116">GetUserDefaultLCID</span></span>](http://msdn.microsoft.com/en-us/library/dd318135%28VS.85%29.aspx)

