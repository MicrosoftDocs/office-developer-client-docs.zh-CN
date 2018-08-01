---
title: UlFromSzHex
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlFromSzHex
api_type:
- COM
ms.assetid: e2d6b6bf-f96d-460c-859a-21961ac9237c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d5ba7e7bc52ba041e9fe6c9a01b35dc91d3b947b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779032"
---
# <a name="ulfromszhex"></a><span data-ttu-id="a4e50-103">UlFromSzHex</span><span class="sxs-lookup"><span data-stu-id="a4e50-103">UlFromSzHex</span></span>

  
  
<span data-ttu-id="a4e50-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a4e50-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a4e50-105">十六进制数字组成的以 null 结尾的字符串转换为无符号的长整数。</span><span class="sxs-lookup"><span data-stu-id="a4e50-105">Converts a null-terminated string of hexadecimal digits into an unsigned long integer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a4e50-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a4e50-106">Header file:</span></span>  <br/> |<span data-ttu-id="a4e50-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a4e50-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="a4e50-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a4e50-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a4e50-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a4e50-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a4e50-110">调用：</span><span class="sxs-lookup"><span data-stu-id="a4e50-110">Called by:</span></span>  <br/> |<span data-ttu-id="a4e50-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a4e50-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlFromSzHex(
LPCSTR lpsz
);
```

## <a name="parameters"></a><span data-ttu-id="a4e50-112">参数</span><span class="sxs-lookup"><span data-stu-id="a4e50-112">Parameters</span></span>

 <span data-ttu-id="a4e50-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="a4e50-113">_lpsz_</span></span>
  
> <span data-ttu-id="a4e50-114">[in]指向以 null 结尾的字符串，要转换的指针。</span><span class="sxs-lookup"><span data-stu-id="a4e50-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="a4e50-115">_Lpsz_参数不能超过 65536 个字符。</span><span class="sxs-lookup"><span data-stu-id="a4e50-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a4e50-116">返回值</span><span class="sxs-lookup"><span data-stu-id="a4e50-116">Return value</span></span>

 <span data-ttu-id="a4e50-117">**UlFromSzHex**返回无符号的长整数。</span><span class="sxs-lookup"><span data-stu-id="a4e50-117">**UlFromSzHex** returns an unsigned long integer.</span></span> <span data-ttu-id="a4e50-118">如果字符串未开始与至少一个十六进制数字，将返回零。</span><span class="sxs-lookup"><span data-stu-id="a4e50-118">If the string does not begin with at least one hexadecimal digit, zero is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a4e50-119">说明</span><span class="sxs-lookup"><span data-stu-id="a4e50-119">Remarks</span></span>

<span data-ttu-id="a4e50-120">**UlFromSzHex**函数将停止转换时到达不是一个十六进制数字字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="a4e50-120">The **UlFromSzHex** function stops converting when it reaches the first character in the string that is not a hexadecimal digit.</span></span> <span data-ttu-id="a4e50-121">**UlFromSzHex**给定"5a"的字符串，例如，返回 90 的整数值。</span><span class="sxs-lookup"><span data-stu-id="a4e50-121">For example, given the string "5a", **UlFromSzHex** returns the integer value 90.</span></span> <span data-ttu-id="a4e50-122">给定字符串"5g5h"，则函数返回 5 的整数值。</span><span class="sxs-lookup"><span data-stu-id="a4e50-122">Given the string "5g5h", the function returns the integer value 5.</span></span> <span data-ttu-id="a4e50-123">**UlFromSzHex**给定字符串"g5h5"，将返回零。</span><span class="sxs-lookup"><span data-stu-id="a4e50-123">Given the string "g5h5", **UlFromSzHex** returns zero.</span></span> 
  
 <span data-ttu-id="a4e50-124">**UlFromSzHex**非常重视发音差异，但允许同时 a 到 f 和 A 到 F 的十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="a4e50-124">**UlFromSzHex** is sensitive to diacritical differences but allows both 'a' through 'f' and 'A' through 'F' for hexadecimal digits.</span></span> <span data-ttu-id="a4e50-125">支持 Unicode 和 DBCS 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="a4e50-125">Strings in the Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="a4e50-126">以字符为单位，不必字节_lpsz_的长度限制。</span><span class="sxs-lookup"><span data-stu-id="a4e50-126">The length limit on  _lpsz_ is in characters, not necessarily bytes.</span></span> 
  

