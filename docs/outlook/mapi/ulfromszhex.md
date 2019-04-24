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
ms.openlocfilehash: 950f5513696a9dd9d52db7b7ee912d3f7d12cc48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315363"
---
# <a name="ulfromszhex"></a><span data-ttu-id="83c0e-103">UlFromSzHex</span><span class="sxs-lookup"><span data-stu-id="83c0e-103">UlFromSzHex</span></span>

  
  
<span data-ttu-id="83c0e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="83c0e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="83c0e-105">将以 null 结尾的十六进制数字字符串转换为无符号长整数。</span><span class="sxs-lookup"><span data-stu-id="83c0e-105">Converts a null-terminated string of hexadecimal digits into an unsigned long integer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="83c0e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="83c0e-106">Header file:</span></span>  <br/> |<span data-ttu-id="83c0e-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="83c0e-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="83c0e-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="83c0e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="83c0e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="83c0e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="83c0e-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="83c0e-110">Called by:</span></span>  <br/> |<span data-ttu-id="83c0e-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="83c0e-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlFromSzHex(
LPCSTR lpsz
);
```

## <a name="parameters"></a><span data-ttu-id="83c0e-112">参数</span><span class="sxs-lookup"><span data-stu-id="83c0e-112">Parameters</span></span>

 <span data-ttu-id="83c0e-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="83c0e-113">_lpsz_</span></span>
  
> <span data-ttu-id="83c0e-114">实时指向要转换的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="83c0e-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="83c0e-115">_lpsz_参数不能超过65536个字符。</span><span class="sxs-lookup"><span data-stu-id="83c0e-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="83c0e-116">返回值</span><span class="sxs-lookup"><span data-stu-id="83c0e-116">Return value</span></span>

 <span data-ttu-id="83c0e-117">**UlFromSzHex**返回一个无符号的长整型值。</span><span class="sxs-lookup"><span data-stu-id="83c0e-117">**UlFromSzHex** returns an unsigned long integer.</span></span> <span data-ttu-id="83c0e-118">如果字符串不以至少一个十六进制数字开头, 则返回零。</span><span class="sxs-lookup"><span data-stu-id="83c0e-118">If the string does not begin with at least one hexadecimal digit, zero is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="83c0e-119">注解</span><span class="sxs-lookup"><span data-stu-id="83c0e-119">Remarks</span></span>

<span data-ttu-id="83c0e-120">**UlFromSzHex**函数在到达不是十六进制数字的字符串中的第一个字符时停止转换。</span><span class="sxs-lookup"><span data-stu-id="83c0e-120">The **UlFromSzHex** function stops converting when it reaches the first character in the string that is not a hexadecimal digit.</span></span> <span data-ttu-id="83c0e-121">例如, 给定字符串 "5a", **UlFromSzHex**返回整数值90。</span><span class="sxs-lookup"><span data-stu-id="83c0e-121">For example, given the string "5a", **UlFromSzHex** returns the integer value 90.</span></span> <span data-ttu-id="83c0e-122">在给定字符串 "5g5h" 的情况下, 函数返回整数值5。</span><span class="sxs-lookup"><span data-stu-id="83c0e-122">Given the string "5g5h", the function returns the integer value 5.</span></span> <span data-ttu-id="83c0e-123">在给定字符串 "g5h5" 的情况下, **UlFromSzHex**返回零。</span><span class="sxs-lookup"><span data-stu-id="83c0e-123">Given the string "g5h5", **UlFromSzHex** returns zero.</span></span> 
  
 <span data-ttu-id="83c0e-124">**UlFromSzHex**对变音符的区别是敏感的, 但允许十六进制数字的 "a" 到 "f" 和 "a" 到 "f"。</span><span class="sxs-lookup"><span data-stu-id="83c0e-124">**UlFromSzHex** is sensitive to diacritical differences but allows both 'a' through 'f' and 'A' through 'F' for hexadecimal digits.</span></span> <span data-ttu-id="83c0e-125">支持 Unicode 和 DBCS 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="83c0e-125">Strings in the Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="83c0e-126">_lpsz_的长度限制是字符, 而不一定是字节。</span><span class="sxs-lookup"><span data-stu-id="83c0e-126">The length limit on  _lpsz_ is in characters, not necessarily bytes.</span></span> 
  

