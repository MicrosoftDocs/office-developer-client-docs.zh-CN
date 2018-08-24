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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: faba91d813d27f7ea45e978724ce0d4707803cba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590104"
---
# <a name="scuncfromlocalpath"></a><span data-ttu-id="c5613-103">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="c5613-103">ScUNCFromLocalPath</span></span>

  
  
<span data-ttu-id="c5613-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c5613-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c5613-105">查找通用命名约定 (UNC) 路径对应的给定的本地路径。</span><span class="sxs-lookup"><span data-stu-id="c5613-105">Locates a universal naming convention (UNC) path counterpart to the given local path.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c5613-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c5613-106">Header file:</span></span>  <br/> |<span data-ttu-id="c5613-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c5613-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c5613-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="c5613-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="c5613-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="c5613-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="c5613-110">调用：</span><span class="sxs-lookup"><span data-stu-id="c5613-110">Called by:</span></span>  <br/> |<span data-ttu-id="c5613-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="c5613-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScUNCFromLocalPath(
  LPSTR szLocal,
  LPSTR szUNC,
  UINT cchUNC
);
```

## <a name="parameters"></a><span data-ttu-id="c5613-112">参数</span><span class="sxs-lookup"><span data-stu-id="c5613-112">Parameters</span></span>

 <span data-ttu-id="c5613-113">_szLocal_</span><span class="sxs-lookup"><span data-stu-id="c5613-113">_szLocal_</span></span>
  
> <span data-ttu-id="c5613-114">[in]格式中的路径 [_驱动器：_]\[ _路径_] 的文件或目录。</span><span class="sxs-lookup"><span data-stu-id="c5613-114">[in] A path in the format [ _drive:_]\[ _path_] of a file or directory.</span></span>
    
 <span data-ttu-id="c5613-115">_szUNC_</span><span class="sxs-lookup"><span data-stu-id="c5613-115">_szUNC_</span></span>
  
> <span data-ttu-id="c5613-116">[输出]格式中的路径\\[_服务器_]\[ _共享_]\[ _路径_] 的相同的文件或目录相同_szLocal_参数。</span><span class="sxs-lookup"><span data-stu-id="c5613-116">[out] A path in the format \\[ _server_]\[ _share_]\[ _path_] of the same file or directory as for the  _szLocal_ parameter.</span></span> 
    
 <span data-ttu-id="c5613-117">_cchUNC_</span><span class="sxs-lookup"><span data-stu-id="c5613-117">_cchUNC_</span></span>
  
> <span data-ttu-id="c5613-118">[in]输出字符串缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="c5613-118">[in] Size of the buffer for the output string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c5613-119">返回值</span><span class="sxs-lookup"><span data-stu-id="c5613-119">Return value</span></span>

<span data-ttu-id="c5613-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5613-120">S_OK</span></span>
  
> <span data-ttu-id="c5613-121">UNC 路径相应已成功找到。</span><span class="sxs-lookup"><span data-stu-id="c5613-121">The UNC path counterpart was successfully located.</span></span>
    
<span data-ttu-id="c5613-122">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="c5613-122">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="c5613-123">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="c5613-123">One or more parameters are invalid.</span></span>
    
<span data-ttu-id="c5613-124">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="c5613-124">MAPI_E_TOO_BIG</span></span>
  
>  <span data-ttu-id="c5613-125">_szUNC_未足以容纳结果。</span><span class="sxs-lookup"><span data-stu-id="c5613-125">_szUNC_ was not large enough to hold the result.</span></span> 
    
<span data-ttu-id="c5613-126">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c5613-126">S_FALSE</span></span>
  
> <span data-ttu-id="c5613-127">本地路径已经存在 UNC 字符串。</span><span class="sxs-lookup"><span data-stu-id="c5613-127">The local path was already a UNC string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c5613-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5613-128">See also</span></span>



[<span data-ttu-id="c5613-129">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="c5613-129">ScLocalPathFromUNC</span></span>](sclocalpathfromunc.md)

