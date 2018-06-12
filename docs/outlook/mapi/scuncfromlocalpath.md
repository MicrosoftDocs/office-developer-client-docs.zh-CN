---
title: ScUNCFromLocalPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScUNCFromLocalPath
api_type:
- COM
ms.assetid: cc4abf1a-c08c-4462-9d7c-6af506dc07c9
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 667eda2a018d2a5d712950a31e05ec0ba9bb32ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778718"
---
# <a name="scuncfromlocalpath"></a><span data-ttu-id="d37f4-103">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="d37f4-103">ScUNCFromLocalPath</span></span>

  
  
<span data-ttu-id="d37f4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d37f4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d37f4-105">查找通用命名约定 (UNC) 路径对应的给定的本地路径。</span><span class="sxs-lookup"><span data-stu-id="d37f4-105">Locates a universal naming convention (UNC) path counterpart to the given local path.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d37f4-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="d37f4-106">Header file:</span></span>  <br/> |<span data-ttu-id="d37f4-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d37f4-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d37f4-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="d37f4-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d37f4-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d37f4-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d37f4-110">调用：</span><span class="sxs-lookup"><span data-stu-id="d37f4-110">Called by:</span></span>  <br/> |<span data-ttu-id="d37f4-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="d37f4-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScUNCFromLocalPath(
  LPSTR szLocal,
  LPSTR szUNC,
  UINT cchUNC
);
```

## <a name="parameters"></a><span data-ttu-id="d37f4-112">参数</span><span class="sxs-lookup"><span data-stu-id="d37f4-112">Parameters</span></span>

 <span data-ttu-id="d37f4-113">_szLocal_</span><span class="sxs-lookup"><span data-stu-id="d37f4-113">_szLocal_</span></span>
  
> <span data-ttu-id="d37f4-114">[in]格式中的路径 [_驱动器：_]\[ _路径_] 的文件或目录。</span><span class="sxs-lookup"><span data-stu-id="d37f4-114">[in] A path in the format [ _drive:_]\[ _path_] of a file or directory.</span></span>
    
 <span data-ttu-id="d37f4-115">_szUNC_</span><span class="sxs-lookup"><span data-stu-id="d37f4-115">_szUNC_</span></span>
  
> <span data-ttu-id="d37f4-116">[输出]格式中的路径\\[_服务器_]\[ _共享_]\[ _路径_] 的相同的文件或目录相同_szLocal_参数。</span><span class="sxs-lookup"><span data-stu-id="d37f4-116">[out] A path in the format \\[ _server_]\[ _share_]\[ _path_] of the same file or directory as for the  _szLocal_ parameter.</span></span> 
    
 <span data-ttu-id="d37f4-117">_cchUNC_</span><span class="sxs-lookup"><span data-stu-id="d37f4-117">_cchUNC_</span></span>
  
> <span data-ttu-id="d37f4-118">[in]输出字符串缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="d37f4-118">[in] Size of the buffer for the output string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d37f4-119">返回值</span><span class="sxs-lookup"><span data-stu-id="d37f4-119">Return value</span></span>

<span data-ttu-id="d37f4-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="d37f4-120">S_OK</span></span>
  
> <span data-ttu-id="d37f4-121">UNC 路径相应已成功找到。</span><span class="sxs-lookup"><span data-stu-id="d37f4-121">The UNC path counterpart was successfully located.</span></span>
    
<span data-ttu-id="d37f4-122">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d37f4-122">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="d37f4-123">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="d37f4-123">One or more parameters are invalid.</span></span>
    
<span data-ttu-id="d37f4-124">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="d37f4-124">MAPI_E_TOO_BIG</span></span>
  
>  <span data-ttu-id="d37f4-125">_szUNC_未足以容纳结果。</span><span class="sxs-lookup"><span data-stu-id="d37f4-125">_szUNC_ was not large enough to hold the result.</span></span> 
    
<span data-ttu-id="d37f4-126">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d37f4-126">S_FALSE</span></span>
  
> <span data-ttu-id="d37f4-127">本地路径已经存在 UNC 字符串。</span><span class="sxs-lookup"><span data-stu-id="d37f4-127">The local path was already a UNC string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d37f4-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d37f4-128">See also</span></span>



[<span data-ttu-id="d37f4-129">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="d37f4-129">ScLocalPathFromUNC</span></span>](sclocalpathfromunc.md)

