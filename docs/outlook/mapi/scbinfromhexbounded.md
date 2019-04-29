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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439756"
---
# <a name="scbinfromhexbounded"></a><span data-ttu-id="3520f-103">ScBinFromHexBounded</span><span class="sxs-lookup"><span data-stu-id="3520f-103">ScBinFromHexBounded</span></span>

  
  
<span data-ttu-id="3520f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3520f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3520f-105">将十六进制数的字符串表示形式的指定部分转换为二进制数。</span><span class="sxs-lookup"><span data-stu-id="3520f-105">Converts the specified portion of a string representation of a hexadecimal number into a binary number.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3520f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3520f-106">Header file:</span></span>  <br/> |<span data-ttu-id="3520f-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="3520f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3520f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="3520f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3520f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3520f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3520f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="3520f-110">Called by:</span></span>  <br/> |<span data-ttu-id="3520f-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="3520f-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScBinFromHexBounded(
  LPSTR sz,
  LPBYTE pb,
  ULONG cb
);
```

## <a name="parameters"></a><span data-ttu-id="3520f-112">参数</span><span class="sxs-lookup"><span data-stu-id="3520f-112">Parameters</span></span>

 <span data-ttu-id="3520f-113">_sz_</span><span class="sxs-lookup"><span data-stu-id="3520f-113">_sz_</span></span>
  
> <span data-ttu-id="3520f-114">实时指向要转换的以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="3520f-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="3520f-115">有效字符包括十六进制字符0到9以及大写和小写字符 a 到 f。</span><span class="sxs-lookup"><span data-stu-id="3520f-115">Valid characters include the hexadecimal characters 0 through 9 and both uppercase and lowercase characters a through f.</span></span>
    
 <span data-ttu-id="3520f-116">_pb_</span><span class="sxs-lookup"><span data-stu-id="3520f-116">_pb_</span></span>
  
> <span data-ttu-id="3520f-117">排除指向返回的二进制数的指针。</span><span class="sxs-lookup"><span data-stu-id="3520f-117">[out] Pointer to the returned binary number.</span></span>
    
 <span data-ttu-id="3520f-118">_cb_</span><span class="sxs-lookup"><span data-stu-id="3520f-118">_cb_</span></span>
  
> <span data-ttu-id="3520f-119">实时_pb_参数的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="3520f-119">[in] Size, in bytes, of the  _pb_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3520f-120">返回值</span><span class="sxs-lookup"><span data-stu-id="3520f-120">Return value</span></span>

<span data-ttu-id="3520f-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="3520f-121">S_OK</span></span>
  
> <span data-ttu-id="3520f-122">转换成功。</span><span class="sxs-lookup"><span data-stu-id="3520f-122">Conversion was successful.</span></span>
    
<span data-ttu-id="3520f-123">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="3520f-123">MAPI_E_CALL_FAILED</span></span>
  
> <span data-ttu-id="3520f-124">遇到无效字符。</span><span class="sxs-lookup"><span data-stu-id="3520f-124">Invalid characters were encountered.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3520f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3520f-125">See also</span></span>



[<span data-ttu-id="3520f-126">FBinFromHex</span><span class="sxs-lookup"><span data-stu-id="3520f-126">FBinFromHex</span></span>](fbinfromhex.md)

