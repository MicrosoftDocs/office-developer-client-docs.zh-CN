---
title: IPSTXGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX.GetLastError
api_type:
- COM
ms.assetid: 68dc0ecc-881e-de69-faaa-90acb9857031
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e061808c57f25f881cc17fa5251e46ed5d524acd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776068"
---
# <a name="ipstxgetlasterror"></a><span data-ttu-id="ed647-103">IPSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="ed647-103">IPSTX::GetLastError</span></span>

  
  
<span data-ttu-id="ed647-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ed647-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ed647-105">获取有关扩展的信息的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="ed647-105">Gets extended information about the last error.</span></span>
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a><span data-ttu-id="ed647-106">参数</span><span class="sxs-lookup"><span data-stu-id="ed647-106">Parameters</span></span>

 <span data-ttu-id="ed647-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="ed647-107">_hResult_</span></span>
  
>  <span data-ttu-id="ed647-108">[in]错误代码。</span><span class="sxs-lookup"><span data-stu-id="ed647-108">[in] Error code.</span></span> 
    
 <span data-ttu-id="ed647-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ed647-109">_ulFlags_</span></span>
  
>  <span data-ttu-id="ed647-110">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="ed647-110">[in] Flags to modify behavior.</span></span> <span data-ttu-id="ed647-111">这必须是 0。</span><span class="sxs-lookup"><span data-stu-id="ed647-111">This must be 0.</span></span> 
    
 <span data-ttu-id="ed647-112">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="ed647-112">_lppMAPIError_</span></span>
  
>  <span data-ttu-id="ed647-113">[输出]指向包含错误的扩展的信息**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="ed647-113">[out] Pointer to the **MAPIERROR** structure that contains the extended information for the error.</span></span> <span data-ttu-id="ed647-114">请参阅 mapidefs.h **LPMAPIERROR**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="ed647-114">See mapidefs.h for the type definition of **LPMAPIERROR**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="ed647-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed647-115">See also</span></span>



[<span data-ttu-id="ed647-116">IPSTX::EmulateSpooler</span><span class="sxs-lookup"><span data-stu-id="ed647-116">IPSTX::EmulateSpooler</span></span>](ipstx-emulatespooler.md)
  
[<span data-ttu-id="ed647-117">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="ed647-117">IPSTX::GetSyncObject</span></span>](ipstx-getsyncobject.md)

