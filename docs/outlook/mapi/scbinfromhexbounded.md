---
title: ScBinFromHexBounded
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScBinFromHexBounded
api_type:
- COM
ms.assetid: edac715c-6edb-4b05-82e5-c08c3c7cb6d4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 813fab28e3e865c9f04f85c854b292ce7229dad5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357496"
---
# <a name="scbinfromhexbounded"></a><span data-ttu-id="ad9ed-103">ScBinFromHexBounded</span><span class="sxs-lookup"><span data-stu-id="ad9ed-103">ScBinFromHexBounded</span></span>

  
  
<span data-ttu-id="ad9ed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad9ed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad9ed-105">将十六进制数的字符串表示形式的指定部分转换为二进制数。</span><span class="sxs-lookup"><span data-stu-id="ad9ed-105">Converts the specified portion of a string representation of a hexadecimal number into a binary number.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ad9ed-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ad9ed-106">Header file:</span></span>  <br/> |<span data-ttu-id="ad9ed-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="ad9ed-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ad9ed-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ad9ed-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ad9ed-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ad9ed-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ad9ed-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ad9ed-110">Called by:</span></span>  <br/> |<span data-ttu-id="ad9ed-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="ad9ed-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScBinFromHexBounded(
  LPSTR sz,
  LPBYTE pb,
  ULONG cb
);
```

## <a name="parameters"></a><span data-ttu-id="ad9ed-112">参数</span><span class="sxs-lookup"><span data-stu-id="ad9ed-112">Parameters</span></span>

 <span data-ttu-id="ad9ed-113">_sz_</span><span class="sxs-lookup"><span data-stu-id="ad9ed-113">_sz_</span></span>
  
> <span data-ttu-id="ad9ed-114">实时指向要转换的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="ad9ed-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="ad9ed-115">有效字符包括十六进制字符0到9以及大写和小写字符 a 到 f。</span><span class="sxs-lookup"><span data-stu-id="ad9ed-115">Valid characters include the hexadecimal characters 0 through 9 and both uppercase and lowercase characters a through f.</span></span>
    
 <span data-ttu-id="ad9ed-116">_pb_</span><span class="sxs-lookup"><span data-stu-id="ad9ed-116">_pb_</span></span>
  
> <span data-ttu-id="ad9ed-117">排除指向返回的二进制数的指针。</span><span class="sxs-lookup"><span data-stu-id="ad9ed-117">[out] Pointer to the returned binary number.</span></span>
    
 <span data-ttu-id="ad9ed-118">_cb_</span><span class="sxs-lookup"><span data-stu-id="ad9ed-118">_cb_</span></span>
  
> <span data-ttu-id="ad9ed-119">实时_pb_参数的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ad9ed-119">[in] Size, in bytes, of the  _pb_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ad9ed-120">返回值</span><span class="sxs-lookup"><span data-stu-id="ad9ed-120">Return value</span></span>

<span data-ttu-id="ad9ed-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad9ed-121">S_OK</span></span>
  
> <span data-ttu-id="ad9ed-122">转换成功。</span><span class="sxs-lookup"><span data-stu-id="ad9ed-122">Conversion was successful.</span></span>
    
<span data-ttu-id="ad9ed-123">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="ad9ed-123">MAPI_E_CALL_FAILED</span></span>
  
> <span data-ttu-id="ad9ed-124">遇到无效字符。</span><span class="sxs-lookup"><span data-stu-id="ad9ed-124">Invalid characters were encountered.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ad9ed-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad9ed-125">See also</span></span>



[<span data-ttu-id="ad9ed-126">FBinFromHex</span><span class="sxs-lookup"><span data-stu-id="ad9ed-126">FBinFromHex</span></span>](fbinfromhex.md)

