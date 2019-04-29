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
ms.openlocfilehash: b53dd9aaaf18dba5c7e33e0bc7d984de757634a4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414534"
---
# <a name="scuncfromlocalpath"></a><span data-ttu-id="af1bd-103">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="af1bd-103">ScUNCFromLocalPath</span></span>

  
  
<span data-ttu-id="af1bd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af1bd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af1bd-105">查找给定本地路径对应的通用命名约定 (UNC) 路径。</span><span class="sxs-lookup"><span data-stu-id="af1bd-105">Locates a universal naming convention (UNC) path counterpart to the given local path.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="af1bd-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="af1bd-106">Header file:</span></span>  <br/> |<span data-ttu-id="af1bd-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="af1bd-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="af1bd-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="af1bd-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="af1bd-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="af1bd-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="af1bd-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="af1bd-110">Called by:</span></span>  <br/> |<span data-ttu-id="af1bd-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="af1bd-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScUNCFromLocalPath(
  LPSTR szLocal,
  LPSTR szUNC,
  UINT cchUNC
);
```

## <a name="parameters"></a><span data-ttu-id="af1bd-112">参数</span><span class="sxs-lookup"><span data-stu-id="af1bd-112">Parameters</span></span>

 <span data-ttu-id="af1bd-113">_szLocal_</span><span class="sxs-lookup"><span data-stu-id="af1bd-113">_szLocal_</span></span>
  
> <span data-ttu-id="af1bd-114">实时文件或目录的格式 [_驱动器:_]\[ _路径_] 中的路径。</span><span class="sxs-lookup"><span data-stu-id="af1bd-114">[in] A path in the format [ _drive:_]\[ _path_] of a file or directory.</span></span>
    
 <span data-ttu-id="af1bd-115">_szUNC_</span><span class="sxs-lookup"><span data-stu-id="af1bd-115">_szUNC_</span></span>
  
> <span data-ttu-id="af1bd-116">排除与_szLocal_参数的文件\\或目录的格式 [ _server_]\[ _share_]\[ _path_] 中的路径。</span><span class="sxs-lookup"><span data-stu-id="af1bd-116">[out] A path in the format \\[ _server_]\[ _share_]\[ _path_] of the same file or directory as for the  _szLocal_ parameter.</span></span> 
    
 <span data-ttu-id="af1bd-117">_cchUNC_</span><span class="sxs-lookup"><span data-stu-id="af1bd-117">_cchUNC_</span></span>
  
> <span data-ttu-id="af1bd-118">实时输出字符串的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="af1bd-118">[in] Size of the buffer for the output string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="af1bd-119">返回值</span><span class="sxs-lookup"><span data-stu-id="af1bd-119">Return value</span></span>

<span data-ttu-id="af1bd-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="af1bd-120">S_OK</span></span>
  
> <span data-ttu-id="af1bd-121">已成功找到对应的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="af1bd-121">The UNC path counterpart was successfully located.</span></span>
    
<span data-ttu-id="af1bd-122">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="af1bd-122">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="af1bd-123">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="af1bd-123">One or more parameters are invalid.</span></span>
    
<span data-ttu-id="af1bd-124">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="af1bd-124">MAPI_E_TOO_BIG</span></span>
  
>  <span data-ttu-id="af1bd-125">_szUNC_的大小不足以容纳结果。</span><span class="sxs-lookup"><span data-stu-id="af1bd-125">_szUNC_ was not large enough to hold the result.</span></span> 
    
<span data-ttu-id="af1bd-126">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="af1bd-126">S_FALSE</span></span>
  
> <span data-ttu-id="af1bd-127">本地路径已是 UNC 字符串。</span><span class="sxs-lookup"><span data-stu-id="af1bd-127">The local path was already a UNC string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="af1bd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af1bd-128">See also</span></span>



[<span data-ttu-id="af1bd-129">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="af1bd-129">ScLocalPathFromUNC</span></span>](sclocalpathfromunc.md)

