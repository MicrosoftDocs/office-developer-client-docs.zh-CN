---
title: IOSTXGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.GetLastError
api_type:
- COM
ms.assetid: b25c9288-b391-6303-3643-5a5b66b75c48
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 69853dbec46b08c4dc402012fb7f1074f30ebf52
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775945"
---
# <a name="iostxgetlasterror"></a><span data-ttu-id="46421-103">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="46421-103">IOSTX::GetLastError</span></span>

  
  
<span data-ttu-id="46421-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="46421-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="46421-105">获取有关扩展的信息的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="46421-105">Gets extended information about the last error.</span></span>
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a><span data-ttu-id="46421-106">参数</span><span class="sxs-lookup"><span data-stu-id="46421-106">Parameters</span></span>

 <span data-ttu-id="46421-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="46421-107">_hResult_</span></span>
  
>  <span data-ttu-id="46421-108">[in]错误代码。</span><span class="sxs-lookup"><span data-stu-id="46421-108">[in] Error code.</span></span> 
    
 <span data-ttu-id="46421-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="46421-109">_ulFlags_</span></span>
  
>  <span data-ttu-id="46421-110">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="46421-110">[in] Flags to modify behavior.</span></span> <span data-ttu-id="46421-111">这必须是 0。</span><span class="sxs-lookup"><span data-stu-id="46421-111">This must be 0.</span></span> 
    
 <span data-ttu-id="46421-112">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="46421-112">_lppMAPIError_</span></span>
  
>  <span data-ttu-id="46421-113">[输出]指向包含错误的扩展的信息**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="46421-113">[out] Pointer to the **MAPIERROR** structure that contains the extended information for the error.</span></span> <span data-ttu-id="46421-114">请参阅 mapidefs.h **LPMAPIERROR**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="46421-114">See mapidefs.h for the type definition of **LPMAPIERROR**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="46421-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46421-115">See also</span></span>



[<span data-ttu-id="46421-116">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="46421-116">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="46421-117">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="46421-117">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="46421-118">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="46421-118">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="46421-119">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="46421-119">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="46421-120">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="46421-120">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="46421-121">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="46421-121">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="46421-122">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="46421-122">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="46421-123">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="46421-123">MAPI Constants</span></span>](mapi-constants.md)

