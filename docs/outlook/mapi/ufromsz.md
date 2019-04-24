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
ms.openlocfilehash: 9947558975098316a547abfaefcdf5e7d4cd2f41
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346534"
---
# <a name="ufromsz"></a><span data-ttu-id="2f634-103">UFromSz</span><span class="sxs-lookup"><span data-stu-id="2f634-103">UFromSz</span></span>

  
  
<span data-ttu-id="2f634-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f634-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f634-105">将以 null 结尾的十进制数字字符串转换为无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2f634-105">Converts a null-terminated string of decimal digits into an unsigned integer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f634-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2f634-106">Header file:</span></span>  <br/> |<span data-ttu-id="2f634-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2f634-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="2f634-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="2f634-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2f634-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2f634-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2f634-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="2f634-110">Called by:</span></span>  <br/> |<span data-ttu-id="2f634-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="2f634-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
UINT UFromSz(
  LPCSTR lpsz
);
```

## <a name="parameters"></a><span data-ttu-id="2f634-112">参数</span><span class="sxs-lookup"><span data-stu-id="2f634-112">Parameters</span></span>

 <span data-ttu-id="2f634-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="2f634-113">_lpsz_</span></span>
  
> <span data-ttu-id="2f634-114">实时指向要转换的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="2f634-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="2f634-115">_lpsz_参数不能超过65536个字符。</span><span class="sxs-lookup"><span data-stu-id="2f634-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2f634-116">返回值</span><span class="sxs-lookup"><span data-stu-id="2f634-116">Return value</span></span>

 <span data-ttu-id="2f634-117">**UFromSz**返回一个无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2f634-117">**UFromSz** returns an unsigned integer.</span></span> <span data-ttu-id="2f634-118">如果字符串不以至少一个十进制数字开头, 则返回零。</span><span class="sxs-lookup"><span data-stu-id="2f634-118">If the string does not begin with at least one decimal digit, zero is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="2f634-119">注解</span><span class="sxs-lookup"><span data-stu-id="2f634-119">Remarks</span></span>

<span data-ttu-id="2f634-120">**UFromSz**函数在到达不是十进制数字的字符串中的第一个字符时停止转换。</span><span class="sxs-lookup"><span data-stu-id="2f634-120">The **UFromSz** function stops converting when it reaches the first character in the string that is not a decimal digit.</span></span> <span data-ttu-id="2f634-121">例如, 在给定字符串 "55" 的情况下, **UFromSz**返回整数值55。</span><span class="sxs-lookup"><span data-stu-id="2f634-121">For example, given the string "55", **UFromSz** returns the integer value 55.</span></span> <span data-ttu-id="2f634-122">在给定字符串 "5a5b" 的情况下, 函数返回整数值5。</span><span class="sxs-lookup"><span data-stu-id="2f634-122">Given the string "5a5b", the function returns the integer value 5.</span></span> <span data-ttu-id="2f634-123">在给定字符串 "a5b5" 的情况下, **UFromSz**返回零。</span><span class="sxs-lookup"><span data-stu-id="2f634-123">Given the string "a5b5", **UFromSz** returns zero.</span></span> 
  
 <span data-ttu-id="2f634-124">**UFromSz**对变音符的区别非常敏感。</span><span class="sxs-lookup"><span data-stu-id="2f634-124">**UFromSz** is sensitive to diacritical differences.</span></span> <span data-ttu-id="2f634-125">支持 Unicode 和 DBCS 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="2f634-125">Strings in the Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="2f634-126">_lpsz_的长度限制是字符, 而不一定是字节。</span><span class="sxs-lookup"><span data-stu-id="2f634-126">The length limit on  _lpsz_ is in characters, not necessarily bytes.</span></span> 
  

