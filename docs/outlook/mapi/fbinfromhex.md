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
ms.openlocfilehash: 64d205ee7f51c0ce6a6eb1e982659c6cda675f8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774926"
---
# <a name="fbinfromhex"></a><span data-ttu-id="30fa9-103">FBinFromHex</span><span class="sxs-lookup"><span data-stu-id="30fa9-103">FBinFromHex</span></span>

  
  
<span data-ttu-id="30fa9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="30fa9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="30fa9-105">将十六进制数的字符串表示形式转换为二进制数据。</span><span class="sxs-lookup"><span data-stu-id="30fa9-105">Converts a string representation of a hexadecimal number to binary data.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="30fa9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="30fa9-106">Header file:</span></span>  <br/> |<span data-ttu-id="30fa9-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="30fa9-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="30fa9-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="30fa9-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="30fa9-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="30fa9-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="30fa9-110">调用：</span><span class="sxs-lookup"><span data-stu-id="30fa9-110">Called by:</span></span>  <br/> |<span data-ttu-id="30fa9-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="30fa9-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
BOOL FBinFromHex(
  LPSTR sz,
  LPBYTE pb
);
```

## <a name="parameters"></a><span data-ttu-id="30fa9-112">参数</span><span class="sxs-lookup"><span data-stu-id="30fa9-112">Parameters</span></span>

 <span data-ttu-id="30fa9-113">_sz_</span><span class="sxs-lookup"><span data-stu-id="30fa9-113">_sz_</span></span>
  
> <span data-ttu-id="30fa9-114">[in]以 null 结尾的 ASCII 字符串要转换的指针。</span><span class="sxs-lookup"><span data-stu-id="30fa9-114">[in] Pointer to the null-terminated ASCII string to be converted.</span></span> <span data-ttu-id="30fa9-115">它不是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="30fa9-115">It is not a Unicode string.</span></span> <span data-ttu-id="30fa9-116">有效字符包括十六进制字符 0-9 和两个大写字母和小写字母字符 A 到 f。</span><span class="sxs-lookup"><span data-stu-id="30fa9-116">Valid characters include the hexadecimal characters zero through nine and both uppercase and lowercase characters A through F.</span></span>
    
 <span data-ttu-id="30fa9-117">_pb_</span><span class="sxs-lookup"><span data-stu-id="30fa9-117">_pb_</span></span>
  
> <span data-ttu-id="30fa9-118">[输出]指向返回二进制数。</span><span class="sxs-lookup"><span data-stu-id="30fa9-118">[out] Pointer to the returned binary number.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="30fa9-119">返回值</span><span class="sxs-lookup"><span data-stu-id="30fa9-119">Return value</span></span>

<span data-ttu-id="30fa9-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="30fa9-120">TRUE</span></span> 
  
> <span data-ttu-id="30fa9-121">该字符串已成功转换为二进制数。</span><span class="sxs-lookup"><span data-stu-id="30fa9-121">The string was successfully converted into a binary number.</span></span> 
    
<span data-ttu-id="30fa9-122">FALSE</span><span class="sxs-lookup"><span data-stu-id="30fa9-122">FALSE</span></span> 
  
> <span data-ttu-id="30fa9-123">输入的字符串包含无效的 ASCII 十六进制字符。</span><span class="sxs-lookup"><span data-stu-id="30fa9-123">The input string contains invalid ASCII hexadecimal characters.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="30fa9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30fa9-124">See also</span></span>



[<span data-ttu-id="30fa9-125">ScBinFromHexBounded</span><span class="sxs-lookup"><span data-stu-id="30fa9-125">ScBinFromHexBounded</span></span>](scbinfromhexbounded.md)

