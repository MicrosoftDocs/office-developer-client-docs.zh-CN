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
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: 864c2d2dfd17c285b0d8a401d59ce5b7d0463864
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332184"
---
# <a name="iostxsynchdrend"></a><span data-ttu-id="0d1d4-103">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="0d1d4-103">IOSTX::SyncHdrEnd</span></span>

 
  
<span data-ttu-id="0d1d4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d1d4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d1d4-105">结束邮件头同步。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-105">Ends synchronization for a message header.</span></span>
  
```cpp
HRESULT SyncHdrEnd( 
    LPMAPIPROGRESS pprog 
);
```

## <a name="parameters"></a><span data-ttu-id="0d1d4-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d1d4-106">Parameters</span></span>

 <span data-ttu-id="0d1d4-107">_pprog_</span><span class="sxs-lookup"><span data-stu-id="0d1d4-107">_pprog_</span></span>
  
> <span data-ttu-id="0d1d4-108">实时用于同步已移动或已复制邮件的**[IMAPIProgress](imapiprogressiunknown.md)** 接口。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-108">[in] **[IMAPIProgress](imapiprogressiunknown.md)** interface for synchronization of moved or copied messages.</span></span> <span data-ttu-id="0d1d4-109">有关**LPMAPIPROGRESS**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-109">See mapidefs.h for the type definition of **LPMAPIPROGRESS**.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0d1d4-110">注解</span><span class="sxs-lookup"><span data-stu-id="0d1d4-110">Remarks</span></span>

<span data-ttu-id="0d1d4-111">在**[IOSTX:: SyncBeg](iostx-syncbeg.md)** 中, 本地存储将进入[下载邮件头状态](download-message-header-state.md)。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-111">Upon **[IOSTX::SyncBeg](iostx-syncbeg.md)**, the local store enters the [download message header state](download-message-header-state.md).</span></span> <span data-ttu-id="0d1d4-112">客户端下载完整的邮件项目 (在**[HDRSYNC](hdrsync.md)** 中为*pmsgFull* )。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-112">The client downloads a full message item (as  *pmsgFull*  in **[HDRSYNC](hdrsync.md)** ).</span></span> <span data-ttu-id="0d1d4-113">如果成功, 客户端还会将**HDRSYNC**中的*ulFlags*设置为**HSF_OK**。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-113">If this is successful, the client also sets  *ulFlags*  in **HDRSYNC** as **HSF_OK**.</span></span> <span data-ttu-id="0d1d4-114">在**IOSTX:: SyncHdrEnd**中, Outlook 检查**HDRSYNC**中的结果, 并使用*pprog*和**HDRSYNC**中的信息更新本地邮件头。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-114">Upon **IOSTX::SyncHdrEnd**, Outlook checks the result in **HDRSYNC** and uses  *pprog*  and the information in **HDRSYNC** to update the local message header.</span></span> 
  
<span data-ttu-id="0d1d4-115">本地存储将返回到它在前面的**[IOSTX:: SyncHdrBeg](iostx-synchdrbeg.md)** 之前的状态。</span><span class="sxs-lookup"><span data-stu-id="0d1d4-115">The local store returns to the state it was in before the preceding **[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0d1d4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d1d4-116">See also</span></span>



[<span data-ttu-id="0d1d4-117">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="0d1d4-117">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="0d1d4-118">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="0d1d4-118">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="0d1d4-119">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="0d1d4-119">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="0d1d4-120">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="0d1d4-120">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="0d1d4-121">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="0d1d4-121">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="0d1d4-122">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="0d1d4-122">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="0d1d4-123">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0d1d4-123">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="0d1d4-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="0d1d4-124">MAPI Constants</span></span>](mapi-constants.md)

