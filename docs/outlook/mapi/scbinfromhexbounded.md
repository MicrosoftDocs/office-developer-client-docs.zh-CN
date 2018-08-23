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
ms.openlocfilehash: 135db8d690d4d4bd610bd15893c358fedddb4605
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589278"
---
# <a name="scbinfromhexbounded"></a><span data-ttu-id="bc4ef-103">ScBinFromHexBounded</span><span class="sxs-lookup"><span data-stu-id="bc4ef-103">ScBinFromHexBounded</span></span>

  
  
<span data-ttu-id="bc4ef-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc4ef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc4ef-105">指定的部分的字符串表示形式的十六进制数转换为二进制数。</span><span class="sxs-lookup"><span data-stu-id="bc4ef-105">Converts the specified portion of a string representation of a hexadecimal number into a binary number.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bc4ef-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bc4ef-106">Header file:</span></span>  <br/> |<span data-ttu-id="bc4ef-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="bc4ef-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="bc4ef-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="bc4ef-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="bc4ef-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="bc4ef-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="bc4ef-110">调用：</span><span class="sxs-lookup"><span data-stu-id="bc4ef-110">Called by:</span></span>  <br/> |<span data-ttu-id="bc4ef-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="bc4ef-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScBinFromHexBounded(
  LPSTR sz,
  LPBYTE pb,
  ULONG cb
);
```

## <a name="parameters"></a><span data-ttu-id="bc4ef-112">参数</span><span class="sxs-lookup"><span data-stu-id="bc4ef-112">Parameters</span></span>

 <span data-ttu-id="bc4ef-113">_sz_</span><span class="sxs-lookup"><span data-stu-id="bc4ef-113">_sz_</span></span>
  
> <span data-ttu-id="bc4ef-114">[in]指向以 null 结尾的字符串，要转换的指针。</span><span class="sxs-lookup"><span data-stu-id="bc4ef-114">[in] Pointer to the null-terminated string to be converted.</span></span> <span data-ttu-id="bc4ef-115">有效字符包括十六进制字符 0-9 和两个大写字母和小写字母字符 a 到 f。</span><span class="sxs-lookup"><span data-stu-id="bc4ef-115">Valid characters include the hexadecimal characters 0 through 9 and both uppercase and lowercase characters a through f.</span></span>
    
 <span data-ttu-id="bc4ef-116">_pb_</span><span class="sxs-lookup"><span data-stu-id="bc4ef-116">_pb_</span></span>
  
> <span data-ttu-id="bc4ef-117">[输出]指向返回二进制数。</span><span class="sxs-lookup"><span data-stu-id="bc4ef-117">[out] Pointer to the returned binary number.</span></span>
    
 <span data-ttu-id="bc4ef-118">_cb_</span><span class="sxs-lookup"><span data-stu-id="bc4ef-118">_cb_</span></span>
  
> <span data-ttu-id="bc4ef-119">[in]大小 （以字节为单位的_pb_参数）。</span><span class="sxs-lookup"><span data-stu-id="bc4ef-119">[in] Size, in bytes, of the  _pb_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="bc4ef-120">返回值</span><span class="sxs-lookup"><span data-stu-id="bc4ef-120">Return value</span></span>

<span data-ttu-id="bc4ef-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc4ef-121">S_OK</span></span>
  
> <span data-ttu-id="bc4ef-122">转换成功。</span><span class="sxs-lookup"><span data-stu-id="bc4ef-122">Conversion was successful.</span></span>
    
<span data-ttu-id="bc4ef-123">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="bc4ef-123">MAPI_E_CALL_FAILED</span></span>
  
> <span data-ttu-id="bc4ef-124">遇到了无效字符。</span><span class="sxs-lookup"><span data-stu-id="bc4ef-124">Invalid characters were encountered.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bc4ef-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc4ef-125">See also</span></span>



[<span data-ttu-id="bc4ef-126">FBinFromHex</span><span class="sxs-lookup"><span data-stu-id="bc4ef-126">FBinFromHex</span></span>](fbinfromhex.md)

