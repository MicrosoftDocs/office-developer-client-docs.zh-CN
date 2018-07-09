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
ms.openlocfilehash: 70c15970ce69e4bc075da6bf55320cb23116b7a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776543"
---
# <a name="mnlslstrlenw"></a><span data-ttu-id="0c7cc-103">MNLS_lstrlenW</span><span class="sxs-lookup"><span data-stu-id="0c7cc-103">MNLS_lstrlenW</span></span>

  
  
<span data-ttu-id="0c7cc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0c7cc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0c7cc-105">确定指定的 Unicode 字符串，不包括 null 终止符的长度。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-105">Determines the length of the specified Unicode string, excluding the terminating null character.</span></span>
  
> [!TIP]
> <span data-ttu-id="0c7cc-106">考虑使用[StringCchLength](http://msdn.microsoft.com/zh-cn/library/ms647539%28VS.85%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-106">Consider using [StringCchLength](http://msdn.microsoft.com/zh-cn/library/ms647539%28VS.85%29.aspx) instead.</span></span> 
  
```cpp
int MNLS_lstrlen(
  LPCWSTR lpsz);
```

## <a name="parameters"></a><span data-ttu-id="0c7cc-107">参数</span><span class="sxs-lookup"><span data-stu-id="0c7cc-107">Parameters</span></span>

 <span data-ttu-id="0c7cc-108">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="0c7cc-108">_lpsz_</span></span>
  
> <span data-ttu-id="0c7cc-109">[in]Null 结尾的 Unicode 字符串要检查。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-109">[in] The null-terminated Unicode string to be checked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0c7cc-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0c7cc-110">Return value</span></span>

<span data-ttu-id="0c7cc-111">此函数返回字符串的长度为之间的整数。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-111">The function returns an integer with the length of the string.</span></span> <span data-ttu-id="0c7cc-112">它是在字符串中，不包括 null 终止符的字符数。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-112">It is a count of characters in the string, excluding the terminating null character.</span></span> <span data-ttu-id="0c7cc-113">如果_lpsz_为 NULL，则此函数将返回零。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-113">If  _lpsz_ is NULL, the function returns zero.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0c7cc-114">备注</span><span class="sxs-lookup"><span data-stu-id="0c7cc-114">Remarks</span></span>

<span data-ttu-id="0c7cc-115">此函数的换行**lstrlen**函数。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-115">This function wraps the **lstrlen** function.</span></span> <span data-ttu-id="0c7cc-116">有关详细信息，请参阅[lstrlen](http://msdn.microsoft.com/zh-cn/library/ms647492%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-116">For more information, see [lstrlen](http://msdn.microsoft.com/zh-cn/library/ms647492%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c7cc-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c7cc-117">See also</span></span>



[<span data-ttu-id="0c7cc-118">lstrlen</span><span class="sxs-lookup"><span data-stu-id="0c7cc-118">lstrlen</span></span>](http://msdn.microsoft.com/zh-cn/library/ms647492%28VS.85%29.aspx)
  
[<span data-ttu-id="0c7cc-119">StringCchLength</span><span class="sxs-lookup"><span data-stu-id="0c7cc-119">StringCchLength</span></span>](http://msdn.microsoft.com/zh-cn/library/ms647539%28VS.85%29.aspx)

