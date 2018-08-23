---
title: MNLS_lstrcpyW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0f92c2d-b5ba-4558-b8a2-484b2db32bec
description: 上次修改时间： 2012 年 6 月 18 日
ms.openlocfilehash: 4d3210c098d0a7c83721798c8c32ffd9f1e5ebb4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575460"
---
# <a name="mnlslstrcpyw"></a><span data-ttu-id="ba614-103">MNLS_lstrcpyW</span><span class="sxs-lookup"><span data-stu-id="ba614-103">MNLS_lstrcpyW</span></span>

 
  
<span data-ttu-id="ba614-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba614-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba614-105">一个字符串复制到的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ba614-105">Copies a string to a buffer.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ba614-106">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="ba614-106">Do not use.</span></span> <span data-ttu-id="ba614-107">考虑使用[StringCchCopy](http://msdn.microsoft.com/en-us/library/ms647527%28VS.85%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="ba614-107">Consider using [StringCchCopy](http://msdn.microsoft.com/en-us/library/ms647527%28VS.85%29.aspx) instead.</span></span> 
  
```cpp
LPWSTR MNLS_lstrcpyW(
 LPWSTR lpString1,
LPCWSTR lpString2);
```

## <a name="parameters"></a><span data-ttu-id="ba614-108">参数</span><span class="sxs-lookup"><span data-stu-id="ba614-108">Parameters</span></span>

<span data-ttu-id="ba614-109">lpString1</span><span class="sxs-lookup"><span data-stu-id="ba614-109">lpString1</span></span>
  
> <span data-ttu-id="ba614-110">[输出]要接收 lpString2 参数指向的字符串的内容缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ba614-110">[out] A buffer to receive the contents of the string pointed to by the lpString2 parameter.</span></span>
    
<span data-ttu-id="ba614-111">lpString2</span><span class="sxs-lookup"><span data-stu-id="ba614-111">lpString2</span></span>
  
> <span data-ttu-id="ba614-112">[in]要复制的 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="ba614-112">[in] The null-terminated string to be copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ba614-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ba614-113">Return value</span></span>

<span data-ttu-id="ba614-114">如果函数成功，返回值是指向缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="ba614-114">If the function succeeds, the return value is a pointer to the buffer.</span></span>
  
<span data-ttu-id="ba614-115">如果函数失败，则返回值为 NULL，lpString1 可能无法在 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="ba614-115">If the function fails, the return value is NULL and lpString1 may not be null-terminated.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ba614-116">注解</span><span class="sxs-lookup"><span data-stu-id="ba614-116">Remarks</span></span>

<span data-ttu-id="ba614-117">此函数的换行**lstrcpy**函数。</span><span class="sxs-lookup"><span data-stu-id="ba614-117">This function wraps the **lstrcpy** function.</span></span> <span data-ttu-id="ba614-118">有关详细信息，请参阅[lstrcpy](http://msdn.microsoft.com/en-us/library/ms647490%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ba614-118">For more information, see [lstrcpy](http://msdn.microsoft.com/en-us/library/ms647490%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ba614-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba614-119">See also</span></span>



[<span data-ttu-id="ba614-120">lstrcpy</span><span class="sxs-lookup"><span data-stu-id="ba614-120">lstrcpy</span></span>](http://msdn.microsoft.com/en-us/library/ms647490%28VS.85%29.aspx)

