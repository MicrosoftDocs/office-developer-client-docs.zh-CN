---
title: IOSTXSyncHdrEnd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncHdrEnd
api_type:
- COM
ms.assetid: a0beb6eb-7978-c64e-dba1-89f0caf2090e
description: 上次修改时间： 2012 年 7 月 3 日
ms.openlocfilehash: a40d4e62a930219a738c7b431f3d2192007c3d9d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591329"
---
# <a name="iostxsynchdrend"></a><span data-ttu-id="f6902-103">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="f6902-103">IOSTX::SyncHdrEnd</span></span>

 
  
<span data-ttu-id="f6902-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f6902-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f6902-105">邮件头的两端同步。</span><span class="sxs-lookup"><span data-stu-id="f6902-105">Ends synchronization for a message header.</span></span>
  
```cpp
HRESULT SyncHdrEnd( 
    LPMAPIPROGRESS pprog 
);
```

## <a name="parameters"></a><span data-ttu-id="f6902-106">参数</span><span class="sxs-lookup"><span data-stu-id="f6902-106">Parameters</span></span>

 <span data-ttu-id="f6902-107">_pprog_</span><span class="sxs-lookup"><span data-stu-id="f6902-107">_pprog_</span></span>
  
> <span data-ttu-id="f6902-108">[in]用于同步的**[IMAPIProgress](imapiprogressiunknown.md)** 界面移动或复制邮件。</span><span class="sxs-lookup"><span data-stu-id="f6902-108">[in] **[IMAPIProgress](imapiprogressiunknown.md)** interface for synchronization of moved or copied messages.</span></span> <span data-ttu-id="f6902-109">请参阅 mapidefs.h **LPMAPIPROGRESS**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="f6902-109">See mapidefs.h for the type definition of **LPMAPIPROGRESS**.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f6902-110">注解</span><span class="sxs-lookup"><span data-stu-id="f6902-110">Remarks</span></span>

<span data-ttu-id="f6902-111">时**[IOSTX::SyncBeg](iostx-syncbeg.md)**，本地存储进入[下载邮件头状态](download-message-header-state.md)。</span><span class="sxs-lookup"><span data-stu-id="f6902-111">Upon **[IOSTX::SyncBeg](iostx-syncbeg.md)**, the local store enters the [download message header state](download-message-header-state.md).</span></span> <span data-ttu-id="f6902-112">客户端下载完整邮件项目 （作为中**[HDRSYNC](hdrsync.md)** *pmsgFull* )。</span><span class="sxs-lookup"><span data-stu-id="f6902-112">The client downloads a full message item (as  *pmsgFull*  in **[HDRSYNC](hdrsync.md)** ).</span></span> <span data-ttu-id="f6902-113">如果这是成功，客户端还*ulFlags*中设置**HDRSYNC** **HSF_OK**。</span><span class="sxs-lookup"><span data-stu-id="f6902-113">If this is successful, the client also sets  *ulFlags*  in **HDRSYNC** as **HSF_OK**.</span></span> <span data-ttu-id="f6902-114">时**IOSTX::SyncHdrEnd**，Outlook 检查**HDRSYNC**结果，并使用在**HDRSYNC** *pprog*和信息，来更新本地邮件头。</span><span class="sxs-lookup"><span data-stu-id="f6902-114">Upon **IOSTX::SyncHdrEnd**, Outlook checks the result in **HDRSYNC** and uses  *pprog*  and the information in **HDRSYNC** to update the local message header.</span></span> 
  
<span data-ttu-id="f6902-115">本地存储返回到上述**[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** 之前的状态。</span><span class="sxs-lookup"><span data-stu-id="f6902-115">The local store returns to the state it was in before the preceding **[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f6902-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6902-116">See also</span></span>



[<span data-ttu-id="f6902-117">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="f6902-117">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="f6902-118">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="f6902-118">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="f6902-119">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="f6902-119">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="f6902-120">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="f6902-120">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="f6902-121">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="f6902-121">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="f6902-122">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="f6902-122">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="f6902-123">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f6902-123">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="f6902-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f6902-124">MAPI Constants</span></span>](mapi-constants.md)

