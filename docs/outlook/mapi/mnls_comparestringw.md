---
title: MNLS_CompareStringW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8d0b7b9-2798-4d29-99e4-17da99039361
description: '上次修改时间: 2012 年2月20日'
ms.openlocfilehash: dbb18ce712d7900106f2c8dd18404e47d8bdbdb7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356845"
---
# <a name="mnlscomparestringw"></a><span data-ttu-id="9a202-103">MNLS_CompareStringW</span><span class="sxs-lookup"><span data-stu-id="9a202-103">MNLS_CompareStringW</span></span>

  
  
<span data-ttu-id="9a202-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9a202-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9a202-105">比较两个 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="9a202-105">Compares two Unicode strings.</span></span>
  
```cpp
int MNLS_CompareStringW (
  LCID lcid,
  DWORD dwFlags,
  LPCWSTR pstr1,
  int cch1,
  LPCWSTR pstr2,
  int cch2);
```

## <a name="parameters"></a><span data-ttu-id="9a202-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a202-106">Parameters</span></span>

 <span data-ttu-id="9a202-107">_lcid_</span><span class="sxs-lookup"><span data-stu-id="9a202-107">_lcid_</span></span>
  
> <span data-ttu-id="9a202-108">实时区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="9a202-108">[in] Locale identifier.</span></span> <span data-ttu-id="9a202-109">有关详细的定义, 请参阅[CompareString](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)的_Locale_参数。</span><span class="sxs-lookup"><span data-stu-id="9a202-109">For detailed definitions, see the  _Locale_ parameter of [CompareString](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx).</span></span>
    
 <span data-ttu-id="9a202-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="9a202-110">_dwFlags_</span></span>
  
> <span data-ttu-id="9a202-111">实时用于忽略大小写和音调符号的标志。</span><span class="sxs-lookup"><span data-stu-id="9a202-111">[in] Flags to ignore case and diacritics.</span></span> <span data-ttu-id="9a202-112">有关详细的定义, 请参阅[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)的_dwCmpFlags_参数。</span><span class="sxs-lookup"><span data-stu-id="9a202-112">For detailed definitions, see the  _dwCmpFlags_ parameter of [CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx).</span></span>
    
 <span data-ttu-id="9a202-113">_pstr1_</span><span class="sxs-lookup"><span data-stu-id="9a202-113">_pstr1_</span></span>
  
> <span data-ttu-id="9a202-114">实时指向要比较的第一个 Unicode 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="9a202-114">[in] Pointer to the first Unicode string to compare.</span></span>
    
 <span data-ttu-id="9a202-115">_cch1_</span><span class="sxs-lookup"><span data-stu-id="9a202-115">_cch1_</span></span>
  
> <span data-ttu-id="9a202-116">实时第一个 Unicode 字符串的长度 (以字符为单位), 不包括终止的 null 字符。</span><span class="sxs-lookup"><span data-stu-id="9a202-116">[in] Length in characters of the first Unicode string, excluding the terminating null character.</span></span> <span data-ttu-id="9a202-117">如果字符串是以 null 结尾的, 则应用程序可以提供一个负值值。</span><span class="sxs-lookup"><span data-stu-id="9a202-117">The application can supply a negative value if the string is null-terminated.</span></span> <span data-ttu-id="9a202-118">在这种情况下, **MNLS_CompareStringW**函数将自动确定长度。</span><span class="sxs-lookup"><span data-stu-id="9a202-118">In this case, the **MNLS_CompareStringW** function determines the length automatically.</span></span> 
    
 <span data-ttu-id="9a202-119">_pstr2_</span><span class="sxs-lookup"><span data-stu-id="9a202-119">_pstr2_</span></span>
  
> <span data-ttu-id="9a202-120">实时指向要比较的第二个 Unicode 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="9a202-120">[in] Pointer to the second Unicode string to compare.</span></span>
    
 <span data-ttu-id="9a202-121">_cch2_</span><span class="sxs-lookup"><span data-stu-id="9a202-121">_cch2_</span></span>
  
> <span data-ttu-id="9a202-122">实时第二个 Unicode 字符串的长度 (以字符为单位), 不包括终止的 null 字符。</span><span class="sxs-lookup"><span data-stu-id="9a202-122">[in] Length in characters of the second Unicode string, excluding the terminating null character.</span></span> <span data-ttu-id="9a202-123">如果字符串是以 null 结尾的, 则应用程序可以提供一个负值值。</span><span class="sxs-lookup"><span data-stu-id="9a202-123">The application can supply a negative value if the string is null-terminated.</span></span> <span data-ttu-id="9a202-124">在这种情况下, 函数将自动确定长度。</span><span class="sxs-lookup"><span data-stu-id="9a202-124">In this case, the function determines the length automatically.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9a202-125">返回值</span><span class="sxs-lookup"><span data-stu-id="9a202-125">Return value</span></span>

<span data-ttu-id="9a202-126">返回为[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)描述的值。</span><span class="sxs-lookup"><span data-stu-id="9a202-126">Returns the values described for [CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9a202-127">注解</span><span class="sxs-lookup"><span data-stu-id="9a202-127">Remarks</span></span>

<span data-ttu-id="9a202-128">此函数将包装[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9a202-128">This function wraps [CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx).</span></span> <span data-ttu-id="9a202-129">**MNLS_CompareStringW**采用相同的参数, 并具有与[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)相同的行为。</span><span class="sxs-lookup"><span data-stu-id="9a202-129">**MNLS_CompareStringW** takes the same parameters and has the same behavior as [CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a202-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a202-130">See also</span></span>



[<span data-ttu-id="9a202-131">CompareStringW</span><span class="sxs-lookup"><span data-stu-id="9a202-131">CompareStringW</span></span>](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)
  
[<span data-ttu-id="9a202-132">CompareStringEx</span><span class="sxs-lookup"><span data-stu-id="9a202-132">CompareStringEx</span></span>](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)

