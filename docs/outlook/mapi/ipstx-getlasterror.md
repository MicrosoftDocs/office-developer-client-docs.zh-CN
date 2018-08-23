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
ms.openlocfilehash: f45b070464fe1b3c177088ff6aa3295f961d45f6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592589"
---
# <a name="ipstxgetlasterror"></a><span data-ttu-id="0aae4-103">IPSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="0aae4-103">IPSTX::GetLastError</span></span>

  
  
<span data-ttu-id="0aae4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0aae4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0aae4-105">获取有关扩展的信息的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="0aae4-105">Gets extended information about the last error.</span></span>
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a><span data-ttu-id="0aae4-106">参数</span><span class="sxs-lookup"><span data-stu-id="0aae4-106">Parameters</span></span>

 <span data-ttu-id="0aae4-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="0aae4-107">_hResult_</span></span>
  
>  <span data-ttu-id="0aae4-108">[in]错误代码。</span><span class="sxs-lookup"><span data-stu-id="0aae4-108">[in] Error code.</span></span> 
    
 <span data-ttu-id="0aae4-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0aae4-109">_ulFlags_</span></span>
  
>  <span data-ttu-id="0aae4-110">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="0aae4-110">[in] Flags to modify behavior.</span></span> <span data-ttu-id="0aae4-111">这必须是 0。</span><span class="sxs-lookup"><span data-stu-id="0aae4-111">This must be 0.</span></span> 
    
 <span data-ttu-id="0aae4-112">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="0aae4-112">_lppMAPIError_</span></span>
  
>  <span data-ttu-id="0aae4-113">[输出]指向包含错误的扩展的信息**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="0aae4-113">[out] Pointer to the **MAPIERROR** structure that contains the extended information for the error.</span></span> <span data-ttu-id="0aae4-114">请参阅 mapidefs.h **LPMAPIERROR**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="0aae4-114">See mapidefs.h for the type definition of **LPMAPIERROR**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="0aae4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0aae4-115">See also</span></span>



[<span data-ttu-id="0aae4-116">IPSTX::EmulateSpooler</span><span class="sxs-lookup"><span data-stu-id="0aae4-116">IPSTX::EmulateSpooler</span></span>](ipstx-emulatespooler.md)
  
[<span data-ttu-id="0aae4-117">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="0aae4-117">IPSTX::GetSyncObject</span></span>](ipstx-getsyncobject.md)

