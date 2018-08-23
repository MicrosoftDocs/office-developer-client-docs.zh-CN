---
title: UFromSz
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UFromSz
api_type:
- COM
ms.assetid: 4a67faa2-8c2e-49a7-8c92-690a0a65c8f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7513e361f4c1c1bcc93cc420f3a1987e0d817c54
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580500"
---
# <a name="ufromsz"></a><span data-ttu-id="e451d-103">UFromSz</span><span class="sxs-lookup"><span data-stu-id="e451d-103">UFromSz</span></span>

  
  
<span data-ttu-id="e451d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e451d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e451d-105">小数位数以 null 结尾的字符串转换为无符号整数。</span><span class="sxs-lookup"><span data-stu-id="e451d-105">Converts a null-terminated string of decimal digits into an unsigned integer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e451d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e451d-106">Header file:</span></span>  <br/> |<span data-ttu-id="e451d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e451d-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="e451d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="e451d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="e451d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="e451d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="e451d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="e451d-110">Called by:</span></span>  <br/> |<span data-ttu-id="e451d-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="e451d-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
UINT UFromSz(
  LPCSTR lpsz
);
```

## <a name="parameters"></a><span data-ttu-id="e451d-112">参数</span><span class="sxs-lookup"><span data-stu-id="e451d-112">Parameters</span></span>

 <span data-ttu-id="e451d-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="e451d-113">_lpsz_</span></span>
  
> <span data-ttu-id="e451d-114">[in]指向以 null 结尾的字符串，要转换的指针。</span><span class="sxs-lookup"><span data-stu-id="e451d-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="e451d-115">_Lpsz_参数不能超过 65536 个字符。</span><span class="sxs-lookup"><span data-stu-id="e451d-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e451d-116">返回值</span><span class="sxs-lookup"><span data-stu-id="e451d-116">Return value</span></span>

 <span data-ttu-id="e451d-117">**UFromSz**返回无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="e451d-117">**UFromSz** returns an unsigned integer.</span></span> <span data-ttu-id="e451d-118">如果未与至少一个十进制开始字符串，则将返回零。</span><span class="sxs-lookup"><span data-stu-id="e451d-118">If the string does not begin with at least one decimal digit, zero is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e451d-119">注解</span><span class="sxs-lookup"><span data-stu-id="e451d-119">Remarks</span></span>

<span data-ttu-id="e451d-120">**UFromSz**函数将停止转换时到达不是小数数字字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="e451d-120">The **UFromSz** function stops converting when it reaches the first character in the string that is not a decimal digit.</span></span> <span data-ttu-id="e451d-121">**UFromSz**给定"55"的字符串，例如，返回 55 的整数值。</span><span class="sxs-lookup"><span data-stu-id="e451d-121">For example, given the string "55", **UFromSz** returns the integer value 55.</span></span> <span data-ttu-id="e451d-122">给定字符串"5a5b"，则函数返回 5 的整数值。</span><span class="sxs-lookup"><span data-stu-id="e451d-122">Given the string "5a5b", the function returns the integer value 5.</span></span> <span data-ttu-id="e451d-123">**UFromSz**给定字符串"a5b5"，将返回零。</span><span class="sxs-lookup"><span data-stu-id="e451d-123">Given the string "a5b5", **UFromSz** returns zero.</span></span> 
  
 <span data-ttu-id="e451d-124">对发音差异敏感**UFromSz** 。</span><span class="sxs-lookup"><span data-stu-id="e451d-124">**UFromSz** is sensitive to diacritical differences.</span></span> <span data-ttu-id="e451d-125">支持 Unicode 和 DBCS 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="e451d-125">Strings in the Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="e451d-126">以字符为单位，不必字节_lpsz_的长度限制。</span><span class="sxs-lookup"><span data-stu-id="e451d-126">The length limit on  _lpsz_ is in characters, not necessarily bytes.</span></span> 
  

