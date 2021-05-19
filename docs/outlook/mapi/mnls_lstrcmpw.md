---
title: MNLS_lstrcmpW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d26c59d7-c839-426f-8693-727fc6bef67e
description: 上次修改时间：2012 年 6 月 18 日
ms.openlocfilehash: 03b0eb794b07bc56ec6dce4a567d89294b2c908a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356838"
---
# <a name="mnls_lstrcmpw"></a><span data-ttu-id="8c16a-103">MNLS_lstrcmpW</span><span class="sxs-lookup"><span data-stu-id="8c16a-103">MNLS_lstrcmpW</span></span>

 
  
<span data-ttu-id="8c16a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8c16a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8c16a-105">比较两个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="8c16a-105">Compares two Unicode strings.</span></span>
  
```cpp
int MNLS_lstrcmpW(
  LPCWSTR lpString1,
  LPCWSTR lpString2);
```

## <a name="parameters"></a><span data-ttu-id="8c16a-106">参数</span><span class="sxs-lookup"><span data-stu-id="8c16a-106">Parameters</span></span>

 <span data-ttu-id="8c16a-107">_lpString1_</span><span class="sxs-lookup"><span data-stu-id="8c16a-107">_lpString1_</span></span>
  
> <span data-ttu-id="8c16a-108">[in]指向要比较的第一个 Unicode 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="8c16a-108">[in] Pointer to the first Unicode string to compare.</span></span>
    
 <span data-ttu-id="8c16a-109">_lpString2_</span><span class="sxs-lookup"><span data-stu-id="8c16a-109">_lpString2_</span></span>
  
> <span data-ttu-id="8c16a-110">[in]指向要比较的第二个 Unicode 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="8c16a-110">[in] Pointer to the second Unicode string to compare.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8c16a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="8c16a-111">Return value</span></span>

<span data-ttu-id="8c16a-112">返回描述的等效调用的值，MNLS_CompareStringW，CSTR_EQUAL。 </span><span class="sxs-lookup"><span data-stu-id="8c16a-112">Returns the values described for an equivalent call to **MNLS_CompareStringW** except for CSTR_EQUAL.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="8c16a-113">备注</span><span class="sxs-lookup"><span data-stu-id="8c16a-113">Remarks</span></span>

 <span data-ttu-id="8c16a-114">_MNLS_lstrcmpW_ 调用 MNLS_CompareStringW GetUserDefaultLCID、0（用于标志）和 -1（对于 cch1 和 cch2）区域设置执行比较。 [](mnls_comparestringw.md)</span><span class="sxs-lookup"><span data-stu-id="8c16a-114">_MNLS_lstrcmpW_ performs a comparison by calling [MNLS_CompareStringW](mnls_comparestringw.md) with a locale of GetUserDefaultLCID, 0 for flags, and -1 for cch1 and cch2.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8c16a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c16a-115">See also</span></span>



[<span data-ttu-id="8c16a-116">GetUserDefaultLCID</span><span class="sxs-lookup"><span data-stu-id="8c16a-116">GetUserDefaultLCID</span></span>](https://msdn.microsoft.com/library/dd318135%28VS.85%29.aspx)

