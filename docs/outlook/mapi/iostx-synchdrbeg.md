---
title: IOSTXSyncHdrBeg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncHdrBeg
api_type:
- COM
ms.assetid: 7f8ca7cf-ac0b-9b77-c1dd-9f1d0871d603
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 49ef9862d5156a1bed242652df32baab9a0123fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317155"
---
# <a name="iostxsynchdrbeg"></a><span data-ttu-id="358dd-103">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="358dd-103">IOSTX::SyncHdrBeg</span></span>

  
  
<span data-ttu-id="358dd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="358dd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="358dd-105">启动邮件头同步。</span><span class="sxs-lookup"><span data-stu-id="358dd-105">Starts synchronization for a message header.</span></span>
  
```cpp
HRESULT SyncHdrBeg( 
    ULONG cbeid, 
    LPENTRYID lpeid, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a><span data-ttu-id="358dd-106">参数</span><span class="sxs-lookup"><span data-stu-id="358dd-106">Parameters</span></span>

 <span data-ttu-id="358dd-107">_cbeid_</span><span class="sxs-lookup"><span data-stu-id="358dd-107">_cbeid_</span></span>
  
> <span data-ttu-id="358dd-108">实时邮件的条目 ID 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="358dd-108">[in] The number of bytes in the entry ID for the message.</span></span>
    
 <span data-ttu-id="358dd-109">_lpeid_</span><span class="sxs-lookup"><span data-stu-id="358dd-109">_lpeid_</span></span>
  
> <span data-ttu-id="358dd-110">实时邮件的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="358dd-110">[in] The entry ID for the message.</span></span>
    
 <span data-ttu-id="358dd-111">_ppv_</span><span class="sxs-lookup"><span data-stu-id="358dd-111">_ppv_</span></span>
  
>  <span data-ttu-id="358dd-112">[in]/[out] 指针, 指向邮件头的**[HDRSYNC](hdrsync.md)** 结构。</span><span class="sxs-lookup"><span data-stu-id="358dd-112">[in]/[out] Pointer to the **[HDRSYNC](hdrsync.md)** structure for the message header.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="358dd-113">注解</span><span class="sxs-lookup"><span data-stu-id="358dd-113">Remarks</span></span>

<span data-ttu-id="358dd-114">在**IOSTX:: SyncHdrBeg**中, 本地存储将转换为[下载邮件头状态](download-message-header-state.md)。</span><span class="sxs-lookup"><span data-stu-id="358dd-114">Upon **IOSTX::SyncHdrBeg**, the local store transitions to the [download message header state](download-message-header-state.md).</span></span> <span data-ttu-id="358dd-115">Outlook 为客户端初始化存储和父文件夹中的邮件头的当前表示形式的**HDRSYNC**结构。</span><span class="sxs-lookup"><span data-stu-id="358dd-115">Outlook initializes for the client the **HDRSYNC** structure with the current representation of the message header in the store and the parent folder.</span></span> <span data-ttu-id="358dd-116">然后, 客户端必须下载完整的邮件项目 (在**HDRSYNC**中为*pmsgFull* )。</span><span class="sxs-lookup"><span data-stu-id="358dd-116">The client must then download a full message item (as  *pmsgFull*  in **HDRSYNC** ).</span></span> <span data-ttu-id="358dd-117">如果成功, 客户端还会将**HDRSYNC**中的*ulFlags*设置为**HSF_OK**。</span><span class="sxs-lookup"><span data-stu-id="358dd-117">If this was successful, the client also sets  *ulFlags*  in **HDRSYNC** as **HSF_OK**.</span></span> <span data-ttu-id="358dd-118">在**[IOSTX:: SyncHdrEnd](iostx-synchdrend.md)** 上, Outlook 检查**HDRSYNC**中的结果, 并使用**HDRSYNC**中的信息更新本地邮件头。</span><span class="sxs-lookup"><span data-stu-id="358dd-118">Upon **[IOSTX::SyncHdrEnd](iostx-synchdrend.md)**, Outlook checks the result in **HDRSYNC** and uses the information in **HDRSYNC** to update the local message header.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="358dd-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="358dd-119">See also</span></span>



[<span data-ttu-id="358dd-120">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="358dd-120">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="358dd-121">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="358dd-121">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="358dd-122">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="358dd-122">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="358dd-123">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="358dd-123">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="358dd-124">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="358dd-124">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="358dd-125">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="358dd-125">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="358dd-126">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="358dd-126">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="358dd-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="358dd-127">MAPI Constants</span></span>](mapi-constants.md)

