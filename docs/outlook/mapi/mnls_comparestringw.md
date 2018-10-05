---
title: MNLS_CompareStringW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8d0b7b9-2798-4d29-99e4-17da99039361
description: 上次修改时间： 2012 年 2 月 20 日
ms.openlocfilehash: dbb18ce712d7900106f2c8dd18404e47d8bdbdb7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396209"
---
# <a name="mnlscomparestringw"></a><span data-ttu-id="180e3-103">MNLS_CompareStringW</span><span class="sxs-lookup"><span data-stu-id="180e3-103">MNLS_CompareStringW</span></span>

  
  
<span data-ttu-id="180e3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="180e3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="180e3-105">比较两个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="180e3-105">Compares two Unicode strings.</span></span>
  
```cpp
int MNLS_CompareStringW (
  LCID lcid,
  DWORD dwFlags,
  LPCWSTR pstr1,
  int cch1,
  LPCWSTR pstr2,
  int cch2);
```

## <a name="parameters"></a><span data-ttu-id="180e3-106">参数</span><span class="sxs-lookup"><span data-stu-id="180e3-106">Parameters</span></span>

 <span data-ttu-id="180e3-107">_lcid_</span><span class="sxs-lookup"><span data-stu-id="180e3-107">_lcid_</span></span>
  
> <span data-ttu-id="180e3-108">[in]区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="180e3-108">[in] Locale identifier.</span></span> <span data-ttu-id="180e3-109">有关详细的定义，请参阅_Locale_参数的[CompareString](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="180e3-109">For detailed definitions, see the  _Locale_ parameter of [CompareString](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx).</span></span>
    
 <span data-ttu-id="180e3-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="180e3-110">_dwFlags_</span></span>
  
> <span data-ttu-id="180e3-111">[in]要忽略大小写和音调符号的标志。</span><span class="sxs-lookup"><span data-stu-id="180e3-111">[in] Flags to ignore case and diacritics.</span></span> <span data-ttu-id="180e3-112">有关详细的定义，请参阅[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)的_dwCmpFlags_参数。</span><span class="sxs-lookup"><span data-stu-id="180e3-112">For detailed definitions, see the  _dwCmpFlags_ parameter of [CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx).</span></span>
    
 <span data-ttu-id="180e3-113">_pstr1_</span><span class="sxs-lookup"><span data-stu-id="180e3-113">_pstr1_</span></span>
  
> <span data-ttu-id="180e3-114">[in]指向要比较的第一个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="180e3-114">[in] Pointer to the first Unicode string to compare.</span></span>
    
 <span data-ttu-id="180e3-115">_cch1_</span><span class="sxs-lookup"><span data-stu-id="180e3-115">_cch1_</span></span>
  
> <span data-ttu-id="180e3-116">[in]以字符数计不包括 null 终止符的第一个 Unicode 字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="180e3-116">[in] Length in characters of the first Unicode string, excluding the terminating null character.</span></span> <span data-ttu-id="180e3-117">如果 string 是 null 结尾，应用程序可以提供一个负值。</span><span class="sxs-lookup"><span data-stu-id="180e3-117">The application can supply a negative value if the string is null-terminated.</span></span> <span data-ttu-id="180e3-118">在这种情况下， **MNLS_CompareStringW**函数将自动确定长度。</span><span class="sxs-lookup"><span data-stu-id="180e3-118">In this case, the **MNLS_CompareStringW** function determines the length automatically.</span></span> 
    
 <span data-ttu-id="180e3-119">_pstr2_</span><span class="sxs-lookup"><span data-stu-id="180e3-119">_pstr2_</span></span>
  
> <span data-ttu-id="180e3-120">[in]指向要比较的第二个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="180e3-120">[in] Pointer to the second Unicode string to compare.</span></span>
    
 <span data-ttu-id="180e3-121">_cch2_</span><span class="sxs-lookup"><span data-stu-id="180e3-121">_cch2_</span></span>
  
> <span data-ttu-id="180e3-122">[in]在不包括 null 终止符的第二个 Unicode 字符串的字符的长度。</span><span class="sxs-lookup"><span data-stu-id="180e3-122">[in] Length in characters of the second Unicode string, excluding the terminating null character.</span></span> <span data-ttu-id="180e3-123">如果 string 是 null 结尾，应用程序可以提供一个负值。</span><span class="sxs-lookup"><span data-stu-id="180e3-123">The application can supply a negative value if the string is null-terminated.</span></span> <span data-ttu-id="180e3-124">在这种情况下，该函数将自动确定长度。</span><span class="sxs-lookup"><span data-stu-id="180e3-124">In this case, the function determines the length automatically.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="180e3-125">返回值</span><span class="sxs-lookup"><span data-stu-id="180e3-125">Return value</span></span>

<span data-ttu-id="180e3-126">返回 for [CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)所述的值。</span><span class="sxs-lookup"><span data-stu-id="180e3-126">Returns the values described for [CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="180e3-127">说明</span><span class="sxs-lookup"><span data-stu-id="180e3-127">Remarks</span></span>

<span data-ttu-id="180e3-128">此函数的换行[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="180e3-128">This function wraps [CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx).</span></span> <span data-ttu-id="180e3-129">**MNLS_CompareStringW**采用相同参数具有[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)相同的行为。</span><span class="sxs-lookup"><span data-stu-id="180e3-129">**MNLS_CompareStringW** takes the same parameters and has the same behavior as [CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="180e3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="180e3-130">See also</span></span>



[<span data-ttu-id="180e3-131">CompareStringW</span><span class="sxs-lookup"><span data-stu-id="180e3-131">CompareStringW</span></span>](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)
  
[<span data-ttu-id="180e3-132">CompareStringEx</span><span class="sxs-lookup"><span data-stu-id="180e3-132">CompareStringEx</span></span>](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)

