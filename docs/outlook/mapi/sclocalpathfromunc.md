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
ms.openlocfilehash: e303361f4f0dd3a08dbb362096d07b8b391a6d97
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594416"
---
# <a name="sclocalpathfromunc"></a><span data-ttu-id="eb9b2-103">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="eb9b2-103">ScLocalPathFromUNC</span></span>

  
  
<span data-ttu-id="eb9b2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eb9b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eb9b2-105">查找本地路径对应的给定的通用命名约定 (UNC) 路径。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-105">Locates a local path counterpart to the given universal naming convention (UNC) path.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="eb9b2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="eb9b2-106">Header file:</span></span>  <br/> |<span data-ttu-id="eb9b2-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="eb9b2-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="eb9b2-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="eb9b2-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="eb9b2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="eb9b2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="eb9b2-110">调用：</span><span class="sxs-lookup"><span data-stu-id="eb9b2-110">Called by:</span></span>  <br/> |<span data-ttu-id="eb9b2-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="eb9b2-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScLocalPathFromUNC(
  LPSTR szUNC,
  LPSTR szLocal,
  UINT cchLocal
);
```

## <a name="parameters"></a><span data-ttu-id="eb9b2-112">参数</span><span class="sxs-lookup"><span data-stu-id="eb9b2-112">Parameters</span></span>

 <span data-ttu-id="eb9b2-113">_szUNC_</span><span class="sxs-lookup"><span data-stu-id="eb9b2-113">_szUNC_</span></span>
  
> <span data-ttu-id="eb9b2-114">[in]格式中的路径\\[_服务器_]\[ _共享_]\[ _路径_] 的文件或目录。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-114">[in] A path in the format \\[ _server_]\[ _share_]\[ _path_] of a file or directory.</span></span>
    
 <span data-ttu-id="eb9b2-115">_szLocal_</span><span class="sxs-lookup"><span data-stu-id="eb9b2-115">_szLocal_</span></span>
  
> <span data-ttu-id="eb9b2-116">[输出]格式中的路径 [_驱动器：_]\[ _路径_] 的相同的文件或目录相同_szUNC_参数。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-116">[out] A path in the format [ _drive:_]\[ _path_] of the same file or directory as for the  _szUNC_ parameter.</span></span> 
    
 <span data-ttu-id="eb9b2-117">_cchLocal_</span><span class="sxs-lookup"><span data-stu-id="eb9b2-117">_cchLocal_</span></span>
  
> <span data-ttu-id="eb9b2-118">[in]输出字符串缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-118">[in] Size of the buffer for the output string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="eb9b2-119">返回值</span><span class="sxs-lookup"><span data-stu-id="eb9b2-119">Return value</span></span>

<span data-ttu-id="eb9b2-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb9b2-120">S_OK</span></span>
  
> <span data-ttu-id="eb9b2-121">本地路径已成功找到。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-121">A local path was successfully located.</span></span>
    
<span data-ttu-id="eb9b2-122">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="eb9b2-122">MAPI_E_TOO_BIG</span></span>
  
>  <span data-ttu-id="eb9b2-123">_szLocal_未足以容纳结果。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-123">_szLocal_ was not large enough to hold the result.</span></span> 
    
<span data-ttu-id="eb9b2-124">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="eb9b2-124">S_FALSE</span></span>
  
> <span data-ttu-id="eb9b2-125">UNC 字符串已本地路径。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-125">The UNC string was already a local path.</span></span>
    
<span data-ttu-id="eb9b2-126">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="eb9b2-126">MAPI_E_NOT_FOUND</span></span>
  
> <span data-ttu-id="eb9b2-127">找不到本地路径。</span><span class="sxs-lookup"><span data-stu-id="eb9b2-127">A local path was not found.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eb9b2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb9b2-128">See also</span></span>



[<span data-ttu-id="eb9b2-129">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="eb9b2-129">ScUNCFromLocalPath</span></span>](scuncfromlocalpath.md)

