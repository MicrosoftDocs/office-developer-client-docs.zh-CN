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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 364914df1c5897241dfeb89cce2cc3c62018ce24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332149"
---
# <a name="iostxsyncend"></a><span data-ttu-id="ddb7f-103">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="ddb7f-103">IOSTX::SyncEnd</span></span>

  
  
<span data-ttu-id="ddb7f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ddb7f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ddb7f-105">在当前状态结束同步并退出该状态。</span><span class="sxs-lookup"><span data-stu-id="ddb7f-105">Ends synchronization in the current state and exits that state.</span></span>
  
```cpp
HRESULT SyncEnd();
```

## <a name="remarks"></a><span data-ttu-id="ddb7f-106">注解</span><span class="sxs-lookup"><span data-stu-id="ddb7f-106">Remarks</span></span>

<span data-ttu-id="ddb7f-107">客户端必须调用对[IOSTX:: SyncBeg](iostx-syncbeg.md)的每个调用的**IOSTX:: SyncEnd** 。</span><span class="sxs-lookup"><span data-stu-id="ddb7f-107">The client must call **IOSTX::SyncEnd** for each call to [IOSTX::SyncBeg](iostx-syncbeg.md).</span></span> <span data-ttu-id="ddb7f-108">相应的数据结构包含用于指示客户端是否已成功完成当前状态的信息, 以便 Outlook 能够清除其内部状态。</span><span class="sxs-lookup"><span data-stu-id="ddb7f-108">The corresponding data structure holds information to indicate whether the client has successfully completed the current state so that Outlook can clean up its internal state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ddb7f-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb7f-109">See also</span></span>



[<span data-ttu-id="ddb7f-110">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="ddb7f-110">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="ddb7f-111">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="ddb7f-111">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="ddb7f-112">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="ddb7f-112">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="ddb7f-113">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="ddb7f-113">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="ddb7f-114">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="ddb7f-114">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="ddb7f-115">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="ddb7f-115">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="ddb7f-116">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ddb7f-116">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="ddb7f-117">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="ddb7f-117">MAPI Constants</span></span>](mapi-constants.md)

