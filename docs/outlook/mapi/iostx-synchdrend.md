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
description: 上次修改时间：2012 年 7 月 3 日
ms.openlocfilehash: 864c2d2dfd17c285b0d8a401d59ce5b7d0463864
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432770"
---
# <a name="iostxsynchdrend"></a><span data-ttu-id="e4489-103">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="e4489-103">IOSTX::SyncHdrEnd</span></span>

 
  
<span data-ttu-id="e4489-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4489-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4489-105">结束邮件头的同步。</span><span class="sxs-lookup"><span data-stu-id="e4489-105">Ends synchronization for a message header.</span></span>
  
```cpp
HRESULT SyncHdrEnd( 
    LPMAPIPROGRESS pprog 
);
```

## <a name="parameters"></a><span data-ttu-id="e4489-106">参数</span><span class="sxs-lookup"><span data-stu-id="e4489-106">Parameters</span></span>

 <span data-ttu-id="e4489-107">_pprog_</span><span class="sxs-lookup"><span data-stu-id="e4489-107">_pprog_</span></span>
  
> <span data-ttu-id="e4489-108">[in]用于同步移动或复制的消息的 **[IMAPIProgress](imapiprogressiunknown.md)** 接口。</span><span class="sxs-lookup"><span data-stu-id="e4489-108">[in] **[IMAPIProgress](imapiprogressiunknown.md)** interface for synchronization of moved or copied messages.</span></span> <span data-ttu-id="e4489-109">有关 **LPMAPIPROGRESS** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="e4489-109">See mapidefs.h for the type definition of **LPMAPIPROGRESS**.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="e4489-110">备注</span><span class="sxs-lookup"><span data-stu-id="e4489-110">Remarks</span></span>

<span data-ttu-id="e4489-111">在 **[IOSTX：：SyncBeg](iostx-syncbeg.md)** 时，本地存储将进入 [下载邮件头状态](download-message-header-state.md)。</span><span class="sxs-lookup"><span data-stu-id="e4489-111">Upon **[IOSTX::SyncBeg](iostx-syncbeg.md)**, the local store enters the [download message header state](download-message-header-state.md).</span></span> <span data-ttu-id="e4489-112">客户端下载完整邮件项目 (**[HDRSYNC](hdrsync.md)** *中为 pmsgFull* ) 。</span><span class="sxs-lookup"><span data-stu-id="e4489-112">The client downloads a full message item (as  *pmsgFull*  in **[HDRSYNC](hdrsync.md)** ).</span></span> <span data-ttu-id="e4489-113">如果此操作成功，客户端还会将 **HDRSYNC** 中的 *ulFlags* **HSF_OK。**</span><span class="sxs-lookup"><span data-stu-id="e4489-113">If this is successful, the client also sets  *ulFlags*  in **HDRSYNC** as **HSF_OK**.</span></span> <span data-ttu-id="e4489-114">当 **IOSTX：：SyncHdrEnd** 时，Outlook **在 HDRSYNC** 中检查结果，并使用 **HDRSYNC** 中的 *pprog* 和信息更新本地邮件头。</span><span class="sxs-lookup"><span data-stu-id="e4489-114">Upon **IOSTX::SyncHdrEnd**, Outlook checks the result in **HDRSYNC** and uses  *pprog*  and the information in **HDRSYNC** to update the local message header.</span></span> 
  
<span data-ttu-id="e4489-115">本地存储将返回到上一 **[IOSTX：：SyncHdrBeg 之前的状态](iostx-synchdrbeg.md)**。</span><span class="sxs-lookup"><span data-stu-id="e4489-115">The local store returns to the state it was in before the preceding **[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e4489-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4489-116">See also</span></span>



[<span data-ttu-id="e4489-117">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="e4489-117">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="e4489-118">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="e4489-118">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="e4489-119">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="e4489-119">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="e4489-120">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="e4489-120">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="e4489-121">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="e4489-121">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="e4489-122">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="e4489-122">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="e4489-123">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e4489-123">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="e4489-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e4489-124">MAPI Constants</span></span>](mapi-constants.md)

