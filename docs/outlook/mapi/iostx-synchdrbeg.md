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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a5c754a209a3e1bce8888851b88e116f92920eb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775957"
---
# <a name="iostxsynchdrbeg"></a><span data-ttu-id="db647-103">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="db647-103">IOSTX::SyncHdrBeg</span></span>

  
  
<span data-ttu-id="db647-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="db647-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="db647-105">邮件头的启动同步。</span><span class="sxs-lookup"><span data-stu-id="db647-105">Starts synchronization for a message header.</span></span>
  
```cpp
HRESULT SyncHdrBeg( 
    ULONG cbeid, 
    LPENTRYID lpeid, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a><span data-ttu-id="db647-106">参数</span><span class="sxs-lookup"><span data-stu-id="db647-106">Parameters</span></span>

 <span data-ttu-id="db647-107">_cbeid_</span><span class="sxs-lookup"><span data-stu-id="db647-107">_cbeid_</span></span>
  
> <span data-ttu-id="db647-108">[in]中的邮件的条目 ID 的字节数。</span><span class="sxs-lookup"><span data-stu-id="db647-108">[in] The number of bytes in the entry ID for the message.</span></span>
    
 <span data-ttu-id="db647-109">_lpeid_</span><span class="sxs-lookup"><span data-stu-id="db647-109">_lpeid_</span></span>
  
> <span data-ttu-id="db647-110">[in]消息的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="db647-110">[in] The entry ID for the message.</span></span>
    
 <span data-ttu-id="db647-111">_ppv_</span><span class="sxs-lookup"><span data-stu-id="db647-111">_ppv_</span></span>
  
>  <span data-ttu-id="db647-112">[in] / [输出] 指向邮件头的**[HDRSYNC](hdrsync.md)** 结构。</span><span class="sxs-lookup"><span data-stu-id="db647-112">[in]/[out] Pointer to the **[HDRSYNC](hdrsync.md)** structure for the message header.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="db647-113">说明</span><span class="sxs-lookup"><span data-stu-id="db647-113">Remarks</span></span>

<span data-ttu-id="db647-114">时**IOSTX::SyncHdrBeg**，本地存储过渡到[下载邮件头状态](download-message-header-state.md)。</span><span class="sxs-lookup"><span data-stu-id="db647-114">Upon **IOSTX::SyncHdrBeg**, the local store transitions to the [download message header state](download-message-header-state.md).</span></span> <span data-ttu-id="db647-115">Outlook 客户端初始化**HDRSYNC**结构中的存储，并且父文件夹的邮件头的当前表示。</span><span class="sxs-lookup"><span data-stu-id="db647-115">Outlook initializes for the client the **HDRSYNC** structure with the current representation of the message header in the store and the parent folder.</span></span> <span data-ttu-id="db647-116">客户端必须然后下载完整邮件项目 （在**HDRSYNC** *pmsgFull* )。</span><span class="sxs-lookup"><span data-stu-id="db647-116">The client must then download a full message item (as  *pmsgFull*  in **HDRSYNC** ).</span></span> <span data-ttu-id="db647-117">如果这是成功，客户端还*ulFlags*中设置**HDRSYNC** **HSF_OK**。</span><span class="sxs-lookup"><span data-stu-id="db647-117">If this was successful, the client also sets  *ulFlags*  in **HDRSYNC** as **HSF_OK**.</span></span> <span data-ttu-id="db647-118">时**[IOSTX::SyncHdrEnd](iostx-synchdrend.md)**，Outlook 检查**HDRSYNC**结果，并使用**HDRSYNC**中的信息来更新本地邮件头。</span><span class="sxs-lookup"><span data-stu-id="db647-118">Upon **[IOSTX::SyncHdrEnd](iostx-synchdrend.md)**, Outlook checks the result in **HDRSYNC** and uses the information in **HDRSYNC** to update the local message header.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="db647-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db647-119">See also</span></span>



[<span data-ttu-id="db647-120">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="db647-120">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="db647-121">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="db647-121">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="db647-122">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="db647-122">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="db647-123">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="db647-123">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="db647-124">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="db647-124">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="db647-125">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="db647-125">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="db647-126">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="db647-126">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="db647-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="db647-127">MAPI Constants</span></span>](mapi-constants.md)

