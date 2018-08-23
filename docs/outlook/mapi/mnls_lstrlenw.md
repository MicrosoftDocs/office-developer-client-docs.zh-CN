---
title: MNLS_lstrlenW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d342a956-1164-4c9c-b0bb-7a0b72dc97fc
description: 上次修改时间： 2012 年 2 月 21 日
ms.openlocfilehash: 1135a8e07bf94a200d06db8b692ee39dfdb78272
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588886"
---
# <a name="mnlslstrlenw"></a><span data-ttu-id="babf0-103">MNLS_lstrlenW</span><span class="sxs-lookup"><span data-stu-id="babf0-103">MNLS_lstrlenW</span></span>

  
  
<span data-ttu-id="babf0-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="babf0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="babf0-105">确定指定的 Unicode 字符串，不包括 null 终止符的长度。</span><span class="sxs-lookup"><span data-stu-id="babf0-105">Determines the length of the specified Unicode string, excluding the terminating null character.</span></span>
  
> [!TIP]
> <span data-ttu-id="babf0-106">考虑使用[StringCchLength](http://msdn.microsoft.com/en-us/library/ms647539%28VS.85%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="babf0-106">Consider using [StringCchLength](http://msdn.microsoft.com/en-us/library/ms647539%28VS.85%29.aspx) instead.</span></span> 
  
```cpp
int MNLS_lstrlen(
  LPCWSTR lpsz);
```

## <a name="parameters"></a><span data-ttu-id="babf0-107">参数</span><span class="sxs-lookup"><span data-stu-id="babf0-107">Parameters</span></span>

 <span data-ttu-id="babf0-108">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="babf0-108">_lpsz_</span></span>
  
> <span data-ttu-id="babf0-109">[in]Null 结尾的 Unicode 字符串要检查。</span><span class="sxs-lookup"><span data-stu-id="babf0-109">[in] The null-terminated Unicode string to be checked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="babf0-110">返回值</span><span class="sxs-lookup"><span data-stu-id="babf0-110">Return value</span></span>

<span data-ttu-id="babf0-111">此函数返回字符串的长度为之间的整数。</span><span class="sxs-lookup"><span data-stu-id="babf0-111">The function returns an integer with the length of the string.</span></span> <span data-ttu-id="babf0-112">它是在字符串中，不包括 null 终止符的字符数。</span><span class="sxs-lookup"><span data-stu-id="babf0-112">It is a count of characters in the string, excluding the terminating null character.</span></span> <span data-ttu-id="babf0-113">如果_lpsz_为 NULL，则此函数将返回零。</span><span class="sxs-lookup"><span data-stu-id="babf0-113">If  _lpsz_ is NULL, the function returns zero.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="babf0-114">注解</span><span class="sxs-lookup"><span data-stu-id="babf0-114">Remarks</span></span>

<span data-ttu-id="babf0-115">此函数的换行**lstrlen**函数。</span><span class="sxs-lookup"><span data-stu-id="babf0-115">This function wraps the **lstrlen** function.</span></span> <span data-ttu-id="babf0-116">有关详细信息，请参阅[lstrlen](http://msdn.microsoft.com/en-us/library/ms647492%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="babf0-116">For more information, see [lstrlen](http://msdn.microsoft.com/en-us/library/ms647492%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="babf0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="babf0-117">See also</span></span>



[<span data-ttu-id="babf0-118">lstrlen</span><span class="sxs-lookup"><span data-stu-id="babf0-118">lstrlen</span></span>](http://msdn.microsoft.com/en-us/library/ms647492%28VS.85%29.aspx)
  
[<span data-ttu-id="babf0-119">StringCchLength</span><span class="sxs-lookup"><span data-stu-id="babf0-119">StringCchLength</span></span>](http://msdn.microsoft.com/en-us/library/ms647539%28VS.85%29.aspx)

