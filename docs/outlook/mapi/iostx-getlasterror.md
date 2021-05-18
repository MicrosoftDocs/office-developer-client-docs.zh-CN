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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9c29011ae2e9b59a7a0a38148fa6c5b673fd9590
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422297"
---
# <a name="iostxgetlasterror"></a><span data-ttu-id="06fbf-103">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="06fbf-103">IOSTX::GetLastError</span></span>

  
  
<span data-ttu-id="06fbf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="06fbf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="06fbf-105">获取有关最后一个错误的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="06fbf-105">Gets extended information about the last error.</span></span>
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a><span data-ttu-id="06fbf-106">参数</span><span class="sxs-lookup"><span data-stu-id="06fbf-106">Parameters</span></span>

 <span data-ttu-id="06fbf-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="06fbf-107">_hResult_</span></span>
  
>  <span data-ttu-id="06fbf-108">[in]错误代码。</span><span class="sxs-lookup"><span data-stu-id="06fbf-108">[in] Error code.</span></span> 
    
 <span data-ttu-id="06fbf-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="06fbf-109">_ulFlags_</span></span>
  
>  <span data-ttu-id="06fbf-110">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="06fbf-110">[in] Flags to modify behavior.</span></span> <span data-ttu-id="06fbf-111">这必须为 0。</span><span class="sxs-lookup"><span data-stu-id="06fbf-111">This must be 0.</span></span> 
    
 <span data-ttu-id="06fbf-112">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="06fbf-112">_lppMAPIError_</span></span>
  
>  <span data-ttu-id="06fbf-113">[out]指向 **MAPIERROR** 结构的指针，其中包含错误的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="06fbf-113">[out] Pointer to the **MAPIERROR** structure that contains the extended information for the error.</span></span> <span data-ttu-id="06fbf-114">有关 **LPMAPIERROR** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="06fbf-114">See mapidefs.h for the type definition of **LPMAPIERROR**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="06fbf-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06fbf-115">See also</span></span>



[<span data-ttu-id="06fbf-116">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="06fbf-116">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="06fbf-117">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="06fbf-117">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="06fbf-118">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="06fbf-118">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="06fbf-119">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="06fbf-119">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="06fbf-120">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="06fbf-120">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="06fbf-121">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="06fbf-121">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="06fbf-122">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="06fbf-122">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="06fbf-123">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="06fbf-123">MAPI Constants</span></span>](mapi-constants.md)

