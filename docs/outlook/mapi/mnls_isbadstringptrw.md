---
title: MNLS_IsBadStringPtrW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 293a0700-b950-4fc2-a2e5-148d6c846384
description: 上次修改时间： 2012 年 2 月 20 日
ms.openlocfilehash: dd7d310c8e801ba1246a0ce948aced9fa6a1a8af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776520"
---
# <a name="mnlsisbadstringptrw"></a><span data-ttu-id="4d1ac-103">MNLS_IsBadStringPtrW</span><span class="sxs-lookup"><span data-stu-id="4d1ac-103">MNLS_IsBadStringPtrW</span></span>

  
  
<span data-ttu-id="4d1ac-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4d1ac-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4d1ac-105">验证为宽字符串的指针有效。</span><span class="sxs-lookup"><span data-stu-id="4d1ac-105">Verifies that a pointer to a wide string is valid.</span></span>
  
```cpp
BOOL MNLS_IsBadStringPtrW(
  LPCWSTR lpsz,
  UINT ucchMax);
```

## <a name="parameters"></a><span data-ttu-id="4d1ac-106">参数</span><span class="sxs-lookup"><span data-stu-id="4d1ac-106">Parameters</span></span>

 <span data-ttu-id="4d1ac-107">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="4d1ac-107">_lpsz_</span></span>
  
> <span data-ttu-id="4d1ac-108">[in]一个指向宽字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="4d1ac-108">[in] A pointer to the wide character string.</span></span>
    
 <span data-ttu-id="4d1ac-109">_ucchMax_</span><span class="sxs-lookup"><span data-stu-id="4d1ac-109">_ucchMax_</span></span>
  
> <span data-ttu-id="4d1ac-110">[in]中包括终止符的字符的字符串的最大长度。</span><span class="sxs-lookup"><span data-stu-id="4d1ac-110">[in] The maximum length of the string in characters including terminator.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4d1ac-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4d1ac-111">Return value</span></span>

<span data-ttu-id="4d1ac-112">返回一个 boolean 类型的值的字符串为错误时为 true。</span><span class="sxs-lookup"><span data-stu-id="4d1ac-112">Returns a Boolean that is true if the string is bad.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4d1ac-113">说明</span><span class="sxs-lookup"><span data-stu-id="4d1ac-113">Remarks</span></span>

<span data-ttu-id="4d1ac-114">此函数的换行[IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4d1ac-114">This function wraps [IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx).</span></span> <span data-ttu-id="4d1ac-115">有关详细信息，请参阅[IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4d1ac-115">For more information, see [IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx).</span></span>
  

