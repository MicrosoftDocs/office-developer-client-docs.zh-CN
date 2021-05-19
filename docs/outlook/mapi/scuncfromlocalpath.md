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
# <a name="scuncfromlocalpath"></a><span data-ttu-id="7b1f3-103">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="7b1f3-103">ScUNCFromLocalPath</span></span>

  
  
<span data-ttu-id="7b1f3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7b1f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7b1f3-105">查找 UNC 中与给定本地 (对应的) 通用命名约定。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-105">Locates a universal naming convention (UNC) path counterpart to the given local path.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7b1f3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7b1f3-106">Header file:</span></span>  <br/> |<span data-ttu-id="7b1f3-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7b1f3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="7b1f3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7b1f3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7b1f3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7b1f3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7b1f3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7b1f3-110">Called by:</span></span>  <br/> |<span data-ttu-id="7b1f3-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="7b1f3-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScUNCFromLocalPath(
  LPSTR szLocal,
  LPSTR szUNC,
  UINT cchUNC
);
```

## <a name="parameters"></a><span data-ttu-id="7b1f3-112">参数</span><span class="sxs-lookup"><span data-stu-id="7b1f3-112">Parameters</span></span>

 <span data-ttu-id="7b1f3-113">_szLocal_</span><span class="sxs-lookup"><span data-stu-id="7b1f3-113">_szLocal_</span></span>
  
> <span data-ttu-id="7b1f3-114">[in]文件或目录的格式为 [ _drive：_] \[ _path_] 的路径。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-114">[in] A path in the format [ _drive:_]\[ _path_] of a file or directory.</span></span>
    
 <span data-ttu-id="7b1f3-115">_szUNC_</span><span class="sxs-lookup"><span data-stu-id="7b1f3-115">_szUNC_</span></span>
  
> <span data-ttu-id="7b1f3-116">[out]与 \\  \[  \[ _szLocal_ 参数相同的文件或目录的格式 [ server ] share ] path ] 的路径。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-116">[out] A path in the format \\[ _server_]\[ _share_]\[ _path_] of the same file or directory as for the  _szLocal_ parameter.</span></span> 
    
 <span data-ttu-id="7b1f3-117">_cchUNC_</span><span class="sxs-lookup"><span data-stu-id="7b1f3-117">_cchUNC_</span></span>
  
> <span data-ttu-id="7b1f3-118">[in]输出字符串的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-118">[in] Size of the buffer for the output string.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7b1f3-119">返回值</span><span class="sxs-lookup"><span data-stu-id="7b1f3-119">Return value</span></span>

<span data-ttu-id="7b1f3-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b1f3-120">S_OK</span></span>
  
> <span data-ttu-id="7b1f3-121">成功找到对应的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-121">The UNC path counterpart was successfully located.</span></span>
    
<span data-ttu-id="7b1f3-122">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="7b1f3-122">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="7b1f3-123">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-123">One or more parameters are invalid.</span></span>
    
<span data-ttu-id="7b1f3-124">MAPI_E_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="7b1f3-124">MAPI_E_TOO_BIG</span></span>
  
>  <span data-ttu-id="7b1f3-125">_szUNC_ 不够大，无法容纳结果。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-125">_szUNC_ was not large enough to hold the result.</span></span> 
    
<span data-ttu-id="7b1f3-126">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7b1f3-126">S_FALSE</span></span>
  
> <span data-ttu-id="7b1f3-127">本地路径已经是 UNC 字符串。</span><span class="sxs-lookup"><span data-stu-id="7b1f3-127">The local path was already a UNC string.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7b1f3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b1f3-128">See also</span></span>



[<span data-ttu-id="7b1f3-129">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="7b1f3-129">ScLocalPathFromUNC</span></span>](sclocalpathfromunc.md)

