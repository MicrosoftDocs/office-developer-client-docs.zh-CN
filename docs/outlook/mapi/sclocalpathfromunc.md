---
title: ScLocalPathFromUNC
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScLocalPathFromUNC
api_type:
- COM
ms.assetid: ef5eb5c6-251e-4a3a-8855-7c28804a29ab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7607a57da5b618a20d6c8e360c7e3cb4f933856
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432231"
---
# <a name="sclocalpathfromunc"></a><span data-ttu-id="7ee1f-103">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="7ee1f-103">ScLocalPathFromUNC</span></span>

  
  
<span data-ttu-id="7ee1f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ee1f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ee1f-105">查找 UNC 路径中给定通用命名约定 (本地) 路径。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-105">Locates a local path counterpart to the given universal naming convention (UNC) path.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ee1f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7ee1f-106">Header file:</span></span>  <br/> |<span data-ttu-id="7ee1f-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="7ee1f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="7ee1f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7ee1f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7ee1f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7ee1f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7ee1f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7ee1f-110">Called by:</span></span>  <br/> |<span data-ttu-id="7ee1f-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="7ee1f-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScLocalPathFromUNC(
  LPSTR szUNC,
  LPSTR szLocal,
  UINT cchLocal
);
```

## <a name="parameters"></a><span data-ttu-id="7ee1f-112">参数</span><span class="sxs-lookup"><span data-stu-id="7ee1f-112">Parameters</span></span>

 <span data-ttu-id="7ee1f-113">_szUNC_</span><span class="sxs-lookup"><span data-stu-id="7ee1f-113">_szUNC_</span></span>
  
> <span data-ttu-id="7ee1f-114">[in]文件或目录 \\ 的格式为 [ _server_] \[ _share_] \[ _path_] 的路径。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-114">[in] A path in the format \\[ _server_]\[ _share_]\[ _path_] of a file or directory.</span></span>
    
 <span data-ttu-id="7ee1f-115">_szLocal_</span><span class="sxs-lookup"><span data-stu-id="7ee1f-115">_szLocal_</span></span>
  
> <span data-ttu-id="7ee1f-116">[out]与 szUNC 参数相同的文件或目录的格式 [ _drive：_] \[ _path_  ] 的路径。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-116">[out] A path in the format [ _drive:_]\[ _path_] of the same file or directory as for the  _szUNC_ parameter.</span></span> 
    
 <span data-ttu-id="7ee1f-117">_cchLocal_</span><span class="sxs-lookup"><span data-stu-id="7ee1f-117">_cchLocal_</span></span>
  
> <span data-ttu-id="7ee1f-118">[in]输出字符串的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-118">[in] Size of the buffer for the output string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7ee1f-119">返回值</span><span class="sxs-lookup"><span data-stu-id="7ee1f-119">Return value</span></span>

<span data-ttu-id="7ee1f-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ee1f-120">S_OK</span></span>
  
> <span data-ttu-id="7ee1f-121">已成功找到本地路径。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-121">A local path was successfully located.</span></span>
    
<span data-ttu-id="7ee1f-122">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="7ee1f-122">MAPI_E_TOO_BIG</span></span>
  
>  <span data-ttu-id="7ee1f-123">_szLocal_ 不够大，不足以容纳结果。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-123">_szLocal_ was not large enough to hold the result.</span></span> 
    
<span data-ttu-id="7ee1f-124">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7ee1f-124">S_FALSE</span></span>
  
> <span data-ttu-id="7ee1f-125">UNC 字符串已经是本地路径。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-125">The UNC string was already a local path.</span></span>
    
<span data-ttu-id="7ee1f-126">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="7ee1f-126">MAPI_E_NOT_FOUND</span></span>
  
> <span data-ttu-id="7ee1f-127">未找到本地路径。</span><span class="sxs-lookup"><span data-stu-id="7ee1f-127">A local path was not found.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7ee1f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee1f-128">See also</span></span>



[<span data-ttu-id="7ee1f-129">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="7ee1f-129">ScUNCFromLocalPath</span></span>](scuncfromlocalpath.md)

