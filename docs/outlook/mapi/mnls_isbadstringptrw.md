---
title: MNLS_IsBadStringPtrW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 293a0700-b950-4fc2-a2e5-148d6c846384
description: '上次修改时间: 2012 年2月20日'
ms.openlocfilehash: 0e64df38afdb8ecce35eb0151d36dde3da35f0a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356852"
---
# <a name="mnlsisbadstringptrw"></a><span data-ttu-id="6299f-103">MNLS_IsBadStringPtrW</span><span class="sxs-lookup"><span data-stu-id="6299f-103">MNLS_IsBadStringPtrW</span></span>

  
  
<span data-ttu-id="6299f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6299f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6299f-105">验证指向宽字符串的指针是否有效。</span><span class="sxs-lookup"><span data-stu-id="6299f-105">Verifies that a pointer to a wide string is valid.</span></span>
  
```cpp
BOOL MNLS_IsBadStringPtrW(
  LPCWSTR lpsz,
  UINT ucchMax);
```

## <a name="parameters"></a><span data-ttu-id="6299f-106">参数</span><span class="sxs-lookup"><span data-stu-id="6299f-106">Parameters</span></span>

 <span data-ttu-id="6299f-107">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="6299f-107">_lpsz_</span></span>
  
> <span data-ttu-id="6299f-108">实时指向宽字符字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="6299f-108">[in] A pointer to the wide character string.</span></span>
    
 <span data-ttu-id="6299f-109">_ucchMax_</span><span class="sxs-lookup"><span data-stu-id="6299f-109">_ucchMax_</span></span>
  
> <span data-ttu-id="6299f-110">实时包含终止符在内的字符串的最大长度 (以字符数为单位)。</span><span class="sxs-lookup"><span data-stu-id="6299f-110">[in] The maximum length of the string in characters including terminator.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6299f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6299f-111">Return value</span></span>

<span data-ttu-id="6299f-112">返回一个 Boolean 类型的值, 如果字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="6299f-112">Returns a Boolean that is true if the string is bad.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6299f-113">注解</span><span class="sxs-lookup"><span data-stu-id="6299f-113">Remarks</span></span>

<span data-ttu-id="6299f-114">此函数将包装[IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6299f-114">This function wraps [IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx).</span></span> <span data-ttu-id="6299f-115">有关详细信息, 请参阅[IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6299f-115">For more information, see [IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx).</span></span>
  

