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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439007"
---
# <a name="ufromsz"></a><span data-ttu-id="8bf3f-103">UFromSz</span><span class="sxs-lookup"><span data-stu-id="8bf3f-103">UFromSz</span></span>

  
  
<span data-ttu-id="8bf3f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8bf3f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8bf3f-105">将小数位数的以 null 结尾的字符串转换为无符号整数。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-105">Converts a null-terminated string of decimal digits into an unsigned integer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8bf3f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8bf3f-106">Header file:</span></span>  <br/> |<span data-ttu-id="8bf3f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8bf3f-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="8bf3f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="8bf3f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="8bf3f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="8bf3f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="8bf3f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="8bf3f-110">Called by:</span></span>  <br/> |<span data-ttu-id="8bf3f-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="8bf3f-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
UINT UFromSz(
  LPCSTR lpsz
);
```

## <a name="parameters"></a><span data-ttu-id="8bf3f-112">参数</span><span class="sxs-lookup"><span data-stu-id="8bf3f-112">Parameters</span></span>

 <span data-ttu-id="8bf3f-113">_lpsz_</span><span class="sxs-lookup"><span data-stu-id="8bf3f-113">_lpsz_</span></span>
  
> <span data-ttu-id="8bf3f-114">[in]指向要转换的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="8bf3f-115">_lpsz_ 参数不能超过 65536 个字符。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-115">The  _lpsz_ parameter must not exceed 65536 characters.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="8bf3f-116">返回值</span><span class="sxs-lookup"><span data-stu-id="8bf3f-116">Return value</span></span>

 <span data-ttu-id="8bf3f-117">**UFromSz** 返回无符号整数。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-117">**UFromSz** returns an unsigned integer.</span></span> <span data-ttu-id="8bf3f-118">如果字符串不以至少一个十进制数字开头，则返回零。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-118">If the string does not begin with at least one decimal digit, zero is returned.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="8bf3f-119">备注</span><span class="sxs-lookup"><span data-stu-id="8bf3f-119">Remarks</span></span>

<span data-ttu-id="8bf3f-120">**UFromSz** 函数在到达字符串中不是十进制数字的第一个字符时停止转换。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-120">The **UFromSz** function stops converting when it reaches the first character in the string that is not a decimal digit.</span></span> <span data-ttu-id="8bf3f-121">例如，在给定字符串"55"后 **，UFromSz** 将返回整数值 55。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-121">For example, given the string "55", **UFromSz** returns the integer value 55.</span></span> <span data-ttu-id="8bf3f-122">如果给定字符串"5a5b"，函数将返回整数值 5。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-122">Given the string "5a5b", the function returns the integer value 5.</span></span> <span data-ttu-id="8bf3f-123">在给定字符串"a5b5"后 **，UFromSz 将** 返回零。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-123">Given the string "a5b5", **UFromSz** returns zero.</span></span> 
  
 <span data-ttu-id="8bf3f-124">**UFromSz** 对音调差异敏感。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-124">**UFromSz** is sensitive to diacritical differences.</span></span> <span data-ttu-id="8bf3f-125">支持 Unicode 和 DBCS 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-125">Strings in the Unicode and DBCS formats are supported.</span></span> <span data-ttu-id="8bf3f-126">_lpsz_ 的长度限制为字符，不一定是字节。</span><span class="sxs-lookup"><span data-stu-id="8bf3f-126">The length limit on  _lpsz_ is in characters, not necessarily bytes.</span></span> 
  

