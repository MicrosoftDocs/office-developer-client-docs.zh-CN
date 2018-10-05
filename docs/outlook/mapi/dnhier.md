---
title: DNHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3953dc9d-0146-3689-63f0-c6ba78566b8b
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 06f30b4856fc10127aec99975652e28a5e8dda30
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389083"
---
# <a name="dnhier"></a><span data-ttu-id="5e2ed-103">DNHIER</span><span class="sxs-lookup"><span data-stu-id="5e2ed-103">DNHIER</span></span>

<span data-ttu-id="5e2ed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e2ed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5e2ed-105">层次结构从服务器下载过程中[下载层次结构状态](download-hierarchy-state.md)，这完整的层次结构同步的信息。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-105">Information for downloading a hierarchy from the server during the [download hierarchy state](download-hierarchy-state.md), which is part of a full hierarchy synchronization.</span></span> <span data-ttu-id="5e2ed-106">此下载的过程使用 Microsoft Exchange 增量更改同步 (ICS)。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-106">This downloading process uses Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="5e2ed-107">ICS 的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-107">For more information on ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5e2ed-108">快速信息</span><span class="sxs-lookup"><span data-stu-id="5e2ed-108">Quick info</span></span>

```cpp
struct DNHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    PXIHC pxihc; 
    UINT cEntNew; 
   UINT cEntMod; 
    UINT cEntDel; 
};
```

## <a name="members"></a><span data-ttu-id="5e2ed-109">Members</span><span class="sxs-lookup"><span data-stu-id="5e2ed-109">Members</span></span>

<span data-ttu-id="5e2ed-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5e2ed-110">_ulFlags_</span></span>
  
>  <span data-ttu-id="5e2ed-111">[in]若要下载过程确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-111">[in] Flags to determine the appropriate behavior during the download.</span></span> 
    
   - <span data-ttu-id="5e2ed-112">DNH_OK</span><span class="sxs-lookup"><span data-stu-id="5e2ed-112">DNH_OK</span></span>
    
   - <span data-ttu-id="5e2ed-113">[in]下载成功。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-113">[in] Download was successful.</span></span> <span data-ttu-id="5e2ed-114">客户端设置从服务器下载信息之后。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-114">The client sets this after downloading information from the server.</span></span>
    
<span data-ttu-id="5e2ed-115">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="5e2ed-115">_pstmReserved_</span></span>
  
> <span data-ttu-id="5e2ed-116">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-116">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="5e2ed-117">_pxihc_</span><span class="sxs-lookup"><span data-stu-id="5e2ed-117">_pxihc_</span></span>
  
>  <span data-ttu-id="5e2ed-118">[输出]支持下载增量层次结构更改的**IExchangeImportHierarchyChanges**层次结构接口的指针。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-118">[out] Pointer to the **IExchangeImportHierarchyChanges** hierarchy interface that supports downloading incremental hierarchy changes.</span></span> <span data-ttu-id="5e2ed-119">**IExchangeImportHierarchyChanges**的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-119">For more information on **IExchangeImportHierarchyChanges**, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="5e2ed-120">_cEntNew_</span><span class="sxs-lookup"><span data-stu-id="5e2ed-120">_cEntNew_</span></span>
  
> <span data-ttu-id="5e2ed-121">[输出]添加到本地存储的文件夹的数量。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-121">[out] Number of folders added to the local store.</span></span> <span data-ttu-id="5e2ed-122">Outlook 时使用 ICS 下载期间填充此值。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-122">Outlook populates this value during the downloading when using ICS.</span></span>
    
<span data-ttu-id="5e2ed-123">_cEntMod_</span><span class="sxs-lookup"><span data-stu-id="5e2ed-123">_cEntMod_</span></span>
  
> <span data-ttu-id="5e2ed-124">[输出]文件夹上的本地存储修改数。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-124">[out] Number of folders to be modified on the local store.</span></span> <span data-ttu-id="5e2ed-125">Outlook 时使用 ICS 下载期间填充此值。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-125">Outlook populates this value during the downloading when using ICS.</span></span>
    
<span data-ttu-id="5e2ed-126">_cEntDel_</span><span class="sxs-lookup"><span data-stu-id="5e2ed-126">_cEntDel_</span></span>
  
> <span data-ttu-id="5e2ed-127">[输出]要删除对本地存储的文件夹的数量。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-127">[out] Number of folders to be deleted on the local store.</span></span> <span data-ttu-id="5e2ed-128">Outlook 时使用 ICS 下载期间填充此值。</span><span class="sxs-lookup"><span data-stu-id="5e2ed-128">Outlook populates this value during the downloading when using ICS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5e2ed-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e2ed-129">See also</span></span>

- [<span data-ttu-id="5e2ed-130">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="5e2ed-130">About the Replication State Machine</span></span>](about-the-replication-state-machine.md) 
- [<span data-ttu-id="5e2ed-131">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="5e2ed-131">MAPI Constants</span></span>](mapi-constants.md)

