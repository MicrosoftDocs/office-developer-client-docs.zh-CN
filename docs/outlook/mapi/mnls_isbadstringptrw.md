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
ms.openlocfilehash: 0052d0bd6b485340a92cca9f22ca65c9e2442df6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589565"
---
# <a name="mnlsisbadstringptrw"></a><span data-ttu-id="30d1c-103">MNLS_IsBadStringPtrW</span><span class="sxs-lookup"><span data-stu-id="30d1c-103">MNLS_IsBadStringPtrW</span></span>

  
  
<span data-ttu-id="30d1c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="30d1c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="30d1c-105">验证为宽字符串的指针有效。</span><span class="sxs-lookup"><span data-stu-id="30d1c-105">Verifies that a pointer to a wide string is valid.</span></span>
  
```cpp
BOOL MNLS_IsBadStringPtrW(
  LPCWSTR lpsz,
  UINT ucchMax);
```

## <a name="parameters"></a><span data-ttu-id="30d1c-106">参数</span><span class="sxs-lookup"><span data-stu-id="30d1c-106">Parameters</span></span>

 <span data-ttu-id="30d1c-107">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="30d1c-107">_lpsz_</span></span>
  
> <span data-ttu-id="30d1c-108">[in]一个指向宽字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="30d1c-108">[in] A pointer to the wide character string.</span></span>
    
 <span data-ttu-id="30d1c-109">_ucchMax_</span><span class="sxs-lookup"><span data-stu-id="30d1c-109">_ucchMax_</span></span>
  
> <span data-ttu-id="30d1c-110">[in]中包括终止符的字符的字符串的最大长度。</span><span class="sxs-lookup"><span data-stu-id="30d1c-110">[in] The maximum length of the string in characters including terminator.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="30d1c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="30d1c-111">Return value</span></span>

<span data-ttu-id="30d1c-112">返回一个 boolean 类型的值的字符串为错误时为 true。</span><span class="sxs-lookup"><span data-stu-id="30d1c-112">Returns a Boolean that is true if the string is bad.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="30d1c-113">注解</span><span class="sxs-lookup"><span data-stu-id="30d1c-113">Remarks</span></span>

<span data-ttu-id="30d1c-114">此函数的换行[IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="30d1c-114">This function wraps [IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx).</span></span> <span data-ttu-id="30d1c-115">有关详细信息，请参阅[IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="30d1c-115">For more information, see [IsBadStringPtr](http://msdn.microsoft.com/en-us/library/aa366714%28VS.85%29.aspx).</span></span>
  

