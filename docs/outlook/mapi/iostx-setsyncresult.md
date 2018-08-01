---
title: IOSTXSetSyncResult
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SetSyncResult
api_type:
- COM
ms.assetid: 7f083ee0-bf36-0059-1589-66e454fe0098
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 74a4e299da6c0637c3da70c329569266d43dbd9a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775955"
---
# <a name="iostxsetsyncresult"></a><span data-ttu-id="786de-103">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="786de-103">IOSTX::SetSyncResult</span></span>

  
  
<span data-ttu-id="786de-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="786de-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="786de-105">设置同步的结果。</span><span class="sxs-lookup"><span data-stu-id="786de-105">Sets the result of the synchronization.</span></span>
  
```cpp
HRESULT SetSyncResult( 
    HRESULT hrSync 
);
```

## <a name="parameters"></a><span data-ttu-id="786de-106">参数</span><span class="sxs-lookup"><span data-stu-id="786de-106">Parameters</span></span>

 <span data-ttu-id="786de-107">_hrSync_</span><span class="sxs-lookup"><span data-stu-id="786de-107">_hrSync_</span></span>
  
>  <span data-ttu-id="786de-108">[in]同步的结果。</span><span class="sxs-lookup"><span data-stu-id="786de-108">[in] The result of the synchronization.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="786de-109">说明</span><span class="sxs-lookup"><span data-stu-id="786de-109">Remarks</span></span>

<span data-ttu-id="786de-110">调用**IOSTX::SyncEnd** ，告知本地存储的结果的同步之前调用**IOSTX::SetSyncResult** 。</span><span class="sxs-lookup"><span data-stu-id="786de-110">Call **IOSTX::SetSyncResult** before calling **IOSTX::SyncEnd** to inform the local store of the result of synchronization.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="786de-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="786de-111">See also</span></span>



[<span data-ttu-id="786de-112">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="786de-112">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="786de-113">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="786de-113">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="786de-114">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="786de-114">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="786de-115">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="786de-115">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="786de-116">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="786de-116">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="786de-117">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="786de-117">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)


[<span data-ttu-id="786de-118">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="786de-118">MAPI Constants</span></span>](mapi-constants.md)

