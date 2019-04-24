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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351245"
---
# <a name="sclocalpathfromunc"></a><span data-ttu-id="fab94-103">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="fab94-103">ScLocalPathFromUNC</span></span>

  
  
<span data-ttu-id="fab94-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fab94-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fab94-105">查找给定的通用命名约定 (UNC) 路径对应的本地路径。</span><span class="sxs-lookup"><span data-stu-id="fab94-105">Locates a local path counterpart to the given universal naming convention (UNC) path.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fab94-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fab94-106">Header file:</span></span>  <br/> |<span data-ttu-id="fab94-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="fab94-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="fab94-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="fab94-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fab94-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="fab94-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="fab94-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="fab94-110">Called by:</span></span>  <br/> |<span data-ttu-id="fab94-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="fab94-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScLocalPathFromUNC(
  LPSTR szUNC,
  LPSTR szLocal,
  UINT cchLocal
);
```

## <a name="parameters"></a><span data-ttu-id="fab94-112">参数</span><span class="sxs-lookup"><span data-stu-id="fab94-112">Parameters</span></span>

 <span data-ttu-id="fab94-113">_szUNC_</span><span class="sxs-lookup"><span data-stu-id="fab94-113">_szUNC_</span></span>
  
> <span data-ttu-id="fab94-114">实时文件或目录的格式\\[ _server_]\[ _share_]\[ _path_] 中的路径。</span><span class="sxs-lookup"><span data-stu-id="fab94-114">[in] A path in the format \\[ _server_]\[ _share_]\[ _path_] of a file or directory.</span></span>
    
 <span data-ttu-id="fab94-115">_szLocal_</span><span class="sxs-lookup"><span data-stu-id="fab94-115">_szLocal_</span></span>
  
> <span data-ttu-id="fab94-116">排除与_szUNC_参数的文件或目录的格式 [ _drive:_]\[ _路径_] 的路径。</span><span class="sxs-lookup"><span data-stu-id="fab94-116">[out] A path in the format [ _drive:_]\[ _path_] of the same file or directory as for the  _szUNC_ parameter.</span></span> 
    
 <span data-ttu-id="fab94-117">_cchLocal_</span><span class="sxs-lookup"><span data-stu-id="fab94-117">_cchLocal_</span></span>
  
> <span data-ttu-id="fab94-118">实时输出字符串的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="fab94-118">[in] Size of the buffer for the output string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fab94-119">返回值</span><span class="sxs-lookup"><span data-stu-id="fab94-119">Return value</span></span>

<span data-ttu-id="fab94-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="fab94-120">S_OK</span></span>
  
> <span data-ttu-id="fab94-121">已成功定位本地路径。</span><span class="sxs-lookup"><span data-stu-id="fab94-121">A local path was successfully located.</span></span>
    
<span data-ttu-id="fab94-122">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="fab94-122">MAPI_E_TOO_BIG</span></span>
  
>  <span data-ttu-id="fab94-123">_szLocal_的大小不足以容纳结果。</span><span class="sxs-lookup"><span data-stu-id="fab94-123">_szLocal_ was not large enough to hold the result.</span></span> 
    
<span data-ttu-id="fab94-124">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fab94-124">S_FALSE</span></span>
  
> <span data-ttu-id="fab94-125">UNC 字符串已经是本地路径。</span><span class="sxs-lookup"><span data-stu-id="fab94-125">The UNC string was already a local path.</span></span>
    
<span data-ttu-id="fab94-126">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="fab94-126">MAPI_E_NOT_FOUND</span></span>
  
> <span data-ttu-id="fab94-127">找不到本地路径。</span><span class="sxs-lookup"><span data-stu-id="fab94-127">A local path was not found.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fab94-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fab94-128">See also</span></span>



[<span data-ttu-id="fab94-129">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="fab94-129">ScUNCFromLocalPath</span></span>](scuncfromlocalpath.md)

