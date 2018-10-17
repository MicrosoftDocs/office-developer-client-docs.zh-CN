---
title: IOSTXSyncEnd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncEnd
api_type:
- COM
ms.assetid: da9de705-bdab-6cb8-35ea-61f03cdc4ff5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fd5b2ed23eba30cbe861a20c4fd100cb8ea1aeb0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568838"
---
# <a name="iostxsyncend"></a><span data-ttu-id="bc5a1-103">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="bc5a1-103">IOSTX::SyncEnd</span></span>

  
  
<span data-ttu-id="bc5a1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc5a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc5a1-105">结束同步中的当前状态并退出该状态。</span><span class="sxs-lookup"><span data-stu-id="bc5a1-105">Ends synchronization in the current state and exits that state.</span></span>
  
```cpp
HRESULT SyncEnd();
```

## <a name="remarks"></a><span data-ttu-id="bc5a1-106">注解</span><span class="sxs-lookup"><span data-stu-id="bc5a1-106">Remarks</span></span>

<span data-ttu-id="bc5a1-107">客户端必须[IOSTX::SyncBeg](iostx-syncbeg.md)到每个呼叫的呼叫**IOSTX::SyncEnd** 。</span><span class="sxs-lookup"><span data-stu-id="bc5a1-107">The client must call **IOSTX::SyncEnd** for each call to [IOSTX::SyncBeg](iostx-syncbeg.md).</span></span> <span data-ttu-id="bc5a1-108">相应的数据结构包含信息，以指示是否以便其内部状态可以清除，Outlook，客户端已成功完成的当前状态。</span><span class="sxs-lookup"><span data-stu-id="bc5a1-108">The corresponding data structure holds information to indicate whether the client has successfully completed the current state so that Outlook can clean up its internal state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bc5a1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc5a1-109">See also</span></span>



[<span data-ttu-id="bc5a1-110">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="bc5a1-110">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="bc5a1-111">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="bc5a1-111">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="bc5a1-112">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="bc5a1-112">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="bc5a1-113">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="bc5a1-113">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="bc5a1-114">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="bc5a1-114">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="bc5a1-115">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="bc5a1-115">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="bc5a1-116">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bc5a1-116">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="bc5a1-117">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="bc5a1-117">MAPI Constants</span></span>](mapi-constants.md)
