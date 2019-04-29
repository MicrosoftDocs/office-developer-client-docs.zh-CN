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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 78ccf72f17ec350d77f2d22d0e6d2fa7c3d97543
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432868"
---
# <a name="iostxsetsyncresult"></a><span data-ttu-id="f170b-103">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="f170b-103">IOSTX::SetSyncResult</span></span>

  
  
<span data-ttu-id="f170b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f170b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f170b-105">设置同步的结果。</span><span class="sxs-lookup"><span data-stu-id="f170b-105">Sets the result of the synchronization.</span></span>
  
```cpp
HRESULT SetSyncResult( 
    HRESULT hrSync 
);
```

## <a name="parameters"></a><span data-ttu-id="f170b-106">参数</span><span class="sxs-lookup"><span data-stu-id="f170b-106">Parameters</span></span>

 <span data-ttu-id="f170b-107">_hrSync_</span><span class="sxs-lookup"><span data-stu-id="f170b-107">_hrSync_</span></span>
  
>  <span data-ttu-id="f170b-108">实时同步的结果。</span><span class="sxs-lookup"><span data-stu-id="f170b-108">[in] The result of the synchronization.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f170b-109">说明</span><span class="sxs-lookup"><span data-stu-id="f170b-109">Remarks</span></span>

<span data-ttu-id="f170b-110">调用**IOSTX:: SetSyncResult**之前调用**IOSTX:: SyncEnd**将同步结果的本地存储通知给本地存储。</span><span class="sxs-lookup"><span data-stu-id="f170b-110">Call **IOSTX::SetSyncResult** before calling **IOSTX::SyncEnd** to inform the local store of the result of synchronization.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f170b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f170b-111">See also</span></span>



[<span data-ttu-id="f170b-112">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="f170b-112">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="f170b-113">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="f170b-113">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="f170b-114">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="f170b-114">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="f170b-115">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="f170b-115">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="f170b-116">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="f170b-116">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="f170b-117">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="f170b-117">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)


[<span data-ttu-id="f170b-118">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f170b-118">MAPI Constants</span></span>](mapi-constants.md)

