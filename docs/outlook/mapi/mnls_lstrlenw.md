---
title: MNLS_lstrlenW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d342a956-1164-4c9c-b0bb-7a0b72dc97fc
description: 上次修改时间：2012 年 2 月 21 日
ms.openlocfilehash: 31f699d1193e55a88e57a0f491658e0d537ef75d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338463"
---
# <a name="mnls_lstrlenw"></a><span data-ttu-id="96bde-103">MNLS_lstrlenW</span><span class="sxs-lookup"><span data-stu-id="96bde-103">MNLS_lstrlenW</span></span>

  
  
<span data-ttu-id="96bde-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96bde-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96bde-105">确定指定的 Unicode 字符串的长度，不包括终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="96bde-105">Determines the length of the specified Unicode string, excluding the terminating null character.</span></span>
  
> [!TIP]
> <span data-ttu-id="96bde-106">请考虑改为[使用 StringCchLength。](https://msdn.microsoft.com/library/ms647539%28VS.85%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="96bde-106">Consider using [StringCchLength](https://msdn.microsoft.com/library/ms647539%28VS.85%29.aspx) instead.</span></span> 
  
```cpp
int MNLS_lstrlen(
  LPCWSTR lpsz);
```

## <a name="parameters"></a><span data-ttu-id="96bde-107">参数</span><span class="sxs-lookup"><span data-stu-id="96bde-107">Parameters</span></span>

 <span data-ttu-id="96bde-108">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="96bde-108">_lpsz_</span></span>
  
> <span data-ttu-id="96bde-109">[in]要检查的以 null 结尾的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="96bde-109">[in] The null-terminated Unicode string to be checked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="96bde-110">返回值</span><span class="sxs-lookup"><span data-stu-id="96bde-110">Return value</span></span>

<span data-ttu-id="96bde-111">函数返回一个包含字符串长度的整数。</span><span class="sxs-lookup"><span data-stu-id="96bde-111">The function returns an integer with the length of the string.</span></span> <span data-ttu-id="96bde-112">它是字符串中的字符计数，不包括终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="96bde-112">It is a count of characters in the string, excluding the terminating null character.</span></span> <span data-ttu-id="96bde-113">如果  _lpsz_ 为 NULL，则函数返回零。</span><span class="sxs-lookup"><span data-stu-id="96bde-113">If  _lpsz_ is NULL, the function returns zero.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="96bde-114">备注</span><span class="sxs-lookup"><span data-stu-id="96bde-114">Remarks</span></span>

<span data-ttu-id="96bde-115">此函数包装 **lstrlen** 函数。</span><span class="sxs-lookup"><span data-stu-id="96bde-115">This function wraps the **lstrlen** function.</span></span> <span data-ttu-id="96bde-116">有关详细信息，请参阅 [lstrlen](https://msdn.microsoft.com/library/ms647492%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="96bde-116">For more information, see [lstrlen](https://msdn.microsoft.com/library/ms647492%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96bde-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96bde-117">See also</span></span>



[<span data-ttu-id="96bde-118">lstrlen</span><span class="sxs-lookup"><span data-stu-id="96bde-118">lstrlen</span></span>](https://msdn.microsoft.com/library/ms647492%28VS.85%29.aspx)
  
[<span data-ttu-id="96bde-119">StringCchLength</span><span class="sxs-lookup"><span data-stu-id="96bde-119">StringCchLength</span></span>](https://msdn.microsoft.com/library/ms647539%28VS.85%29.aspx)

