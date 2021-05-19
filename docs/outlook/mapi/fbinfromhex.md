---
title: FBinFromHex
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FBinFromHex
api_type:
- COM
ms.assetid: 47e6c576-bd99-4410-8e41-7dd3159b23b7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 55c7deec9d29ae22a07b2f5ccd1c832d56782c03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414933"
---
# <a name="fbinfromhex"></a><span data-ttu-id="1645f-103">FBinFromHex</span><span class="sxs-lookup"><span data-stu-id="1645f-103">FBinFromHex</span></span>

  
  
<span data-ttu-id="1645f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1645f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1645f-105">将十六进制数的字符串表示形式转换为二进制数据。</span><span class="sxs-lookup"><span data-stu-id="1645f-105">Converts a string representation of a hexadecimal number to binary data.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1645f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1645f-106">Header file:</span></span>  <br/> |<span data-ttu-id="1645f-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="1645f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="1645f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="1645f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1645f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1645f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1645f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="1645f-110">Called by:</span></span>  <br/> |<span data-ttu-id="1645f-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="1645f-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FBinFromHex(
  LPSTR sz,
  LPBYTE pb
);
```

## <a name="parameters"></a><span data-ttu-id="1645f-112">参数</span><span class="sxs-lookup"><span data-stu-id="1645f-112">Parameters</span></span>

 <span data-ttu-id="1645f-113">_sz_</span><span class="sxs-lookup"><span data-stu-id="1645f-113">_sz_</span></span>
  
> <span data-ttu-id="1645f-114">[in]指向要转换的以 null 结尾的 ASCII 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="1645f-114">[in] Pointer to the null-terminated ASCII string to be converted.</span></span> <span data-ttu-id="1645f-115">这不是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="1645f-115">It is not a Unicode string.</span></span> <span data-ttu-id="1645f-116">有效字符包括从 0 到 9 的十六进制字符以及大写和小写字符 A 到 F。</span><span class="sxs-lookup"><span data-stu-id="1645f-116">Valid characters include the hexadecimal characters zero through nine and both uppercase and lowercase characters A through F.</span></span>
    
 <span data-ttu-id="1645f-117">_pb_</span><span class="sxs-lookup"><span data-stu-id="1645f-117">_pb_</span></span>
  
> <span data-ttu-id="1645f-118">[out]指向返回的二进制数的指针。</span><span class="sxs-lookup"><span data-stu-id="1645f-118">[out] Pointer to the returned binary number.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1645f-119">返回值</span><span class="sxs-lookup"><span data-stu-id="1645f-119">Return value</span></span>

<span data-ttu-id="1645f-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="1645f-120">TRUE</span></span> 
  
> <span data-ttu-id="1645f-121">字符串已成功转换为二进制数。</span><span class="sxs-lookup"><span data-stu-id="1645f-121">The string was successfully converted into a binary number.</span></span> 
    
<span data-ttu-id="1645f-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="1645f-122">FALSE</span></span> 
  
> <span data-ttu-id="1645f-123">输入字符串包含无效的 ASCII 十六进制字符。</span><span class="sxs-lookup"><span data-stu-id="1645f-123">The input string contains invalid ASCII hexadecimal characters.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1645f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1645f-124">See also</span></span>



[<span data-ttu-id="1645f-125">ScBinFromHexBounded</span><span class="sxs-lookup"><span data-stu-id="1645f-125">ScBinFromHexBounded</span></span>](scbinfromhexbounded.md)

