---
title: MNLS_lstrcpyW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0f92c2d-b5ba-4558-b8a2-484b2db32bec
description: '上次修改时间: 2012 年6月18日'
ms.openlocfilehash: 1a1cf0a607dd4b57353eda74f9b14965e110c071
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341725"
---
# <a name="mnlslstrcpyw"></a><span data-ttu-id="14593-103">MNLS_lstrcpyW</span><span class="sxs-lookup"><span data-stu-id="14593-103">MNLS_lstrcpyW</span></span>

 
  
<span data-ttu-id="14593-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="14593-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="14593-105">将字符串复制到缓冲区。</span><span class="sxs-lookup"><span data-stu-id="14593-105">Copies a string to a buffer.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="14593-106">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="14593-106">Do not use.</span></span> <span data-ttu-id="14593-107">请考虑改用[StringCchCopy](https://msdn.microsoft.com/library/ms647527%28VS.85%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="14593-107">Consider using [StringCchCopy](https://msdn.microsoft.com/library/ms647527%28VS.85%29.aspx) instead.</span></span> 
  
```cpp
LPWSTR MNLS_lstrcpyW(
 LPWSTR lpString1,
LPCWSTR lpString2);
```

## <a name="parameters"></a><span data-ttu-id="14593-108">参数</span><span class="sxs-lookup"><span data-stu-id="14593-108">Parameters</span></span>

<span data-ttu-id="14593-109">lpString1</span><span class="sxs-lookup"><span data-stu-id="14593-109">lpString1</span></span>
  
> <span data-ttu-id="14593-110">排除一个缓冲区, 用于接收由 lpString2 参数指向的字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="14593-110">[out] A buffer to receive the contents of the string pointed to by the lpString2 parameter.</span></span>
    
<span data-ttu-id="14593-111">lpString2</span><span class="sxs-lookup"><span data-stu-id="14593-111">lpString2</span></span>
  
> <span data-ttu-id="14593-112">实时要复制的以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="14593-112">[in] The null-terminated string to be copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="14593-113">返回值</span><span class="sxs-lookup"><span data-stu-id="14593-113">Return value</span></span>

<span data-ttu-id="14593-114">如果函数成功, 则返回值为指向缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="14593-114">If the function succeeds, the return value is a pointer to the buffer.</span></span>
  
<span data-ttu-id="14593-115">如果函数失败, 则返回值为 null, lpString1 不能以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="14593-115">If the function fails, the return value is NULL and lpString1 may not be null-terminated.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="14593-116">注解</span><span class="sxs-lookup"><span data-stu-id="14593-116">Remarks</span></span>

<span data-ttu-id="14593-117">此函数将包装**lstrcpy**函数。</span><span class="sxs-lookup"><span data-stu-id="14593-117">This function wraps the **lstrcpy** function.</span></span> <span data-ttu-id="14593-118">有关详细信息, 请参阅[lstrcpy](https://msdn.microsoft.com/library/ms647490%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="14593-118">For more information, see [lstrcpy](https://msdn.microsoft.com/library/ms647490%28VS.85%29.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="14593-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14593-119">See also</span></span>



[<span data-ttu-id="14593-120">lstrcpy</span><span class="sxs-lookup"><span data-stu-id="14593-120">lstrcpy</span></span>](https://msdn.microsoft.com/library/ms647490%28VS.85%29.aspx)

