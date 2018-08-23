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
ms.openlocfilehash: f8982bafc0678378ae46dc31a9417cc11bb695a7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563070"
---
# <a name="iostxsetsyncresult"></a><span data-ttu-id="40aaf-103">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="40aaf-103">IOSTX::SetSyncResult</span></span>

  
  
<span data-ttu-id="40aaf-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="40aaf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="40aaf-105">设置同步的结果。</span><span class="sxs-lookup"><span data-stu-id="40aaf-105">Sets the result of the synchronization.</span></span>
  
```cpp
HRESULT SetSyncResult( 
    HRESULT hrSync 
);
```

## <a name="parameters"></a><span data-ttu-id="40aaf-106">参数</span><span class="sxs-lookup"><span data-stu-id="40aaf-106">Parameters</span></span>

 <span data-ttu-id="40aaf-107">_hrSync_</span><span class="sxs-lookup"><span data-stu-id="40aaf-107">_hrSync_</span></span>
  
>  <span data-ttu-id="40aaf-108">[in]同步的结果。</span><span class="sxs-lookup"><span data-stu-id="40aaf-108">[in] The result of the synchronization.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="40aaf-109">注解</span><span class="sxs-lookup"><span data-stu-id="40aaf-109">Remarks</span></span>

<span data-ttu-id="40aaf-110">调用**IOSTX::SyncEnd** ，告知本地存储的结果的同步之前调用**IOSTX::SetSyncResult** 。</span><span class="sxs-lookup"><span data-stu-id="40aaf-110">Call **IOSTX::SetSyncResult** before calling **IOSTX::SyncEnd** to inform the local store of the result of synchronization.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="40aaf-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40aaf-111">See also</span></span>



[<span data-ttu-id="40aaf-112">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="40aaf-112">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="40aaf-113">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="40aaf-113">IOSTX::InitSync</span></span>](iostx-initsync.md)
  
[<span data-ttu-id="40aaf-114">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="40aaf-114">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="40aaf-115">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="40aaf-115">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="40aaf-116">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="40aaf-116">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="40aaf-117">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="40aaf-117">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)


[<span data-ttu-id="40aaf-118">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="40aaf-118">MAPI Constants</span></span>](mapi-constants.md)

