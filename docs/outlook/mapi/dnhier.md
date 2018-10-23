---
title: DNHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3953dc9d-0146-3689-63f0-c6ba78566b8b
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 06f30b4856fc10127aec99975652e28a5e8dda30
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389083"
---
# <a name="dnhier"></a><span data-ttu-id="5b147-103">DNHIER</span><span class="sxs-lookup"><span data-stu-id="5b147-103">DNHIER</span></span>

<span data-ttu-id="5b147-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5b147-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5b147-105">在[下载层次结构状态](download-hierarchy-state.md)期间从服务器下载层次结构的信息，这是完整层次结构同步的一部分。</span><span class="sxs-lookup"><span data-stu-id="5b147-105">Information for downloading a hierarchy from the server during the [download hierarchy state](download-hierarchy-state.md), which is part of a full hierarchy synchronization.</span></span> <span data-ttu-id="5b147-106">这一下载过程使用 Microsoft Exchange 增量更改同步 (ICS)。</span><span class="sxs-lookup"><span data-stu-id="5b147-106">This downloading process uses Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="5b147-107">有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5b147-107">For more information on ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5b147-108">快速信息</span><span class="sxs-lookup"><span data-stu-id="5b147-108">Quick Info</span></span>

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

## <a name="members"></a><span data-ttu-id="5b147-109">成员</span><span class="sxs-lookup"><span data-stu-id="5b147-109">Members</span></span>

<span data-ttu-id="5b147-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5b147-110">_ulFlags_</span></span>
  
>  <span data-ttu-id="5b147-111">[传入] 用于确定下载期间的适当行为的标签。</span><span class="sxs-lookup"><span data-stu-id="5b147-111">[in] Flags to determine the appropriate behavior during the download.</span></span> 
    
   - <span data-ttu-id="5b147-112">DNH_OK</span><span class="sxs-lookup"><span data-stu-id="5b147-112">DNH_OK</span></span>
    
   - <span data-ttu-id="5b147-113">[传入] 下载成功。</span><span class="sxs-lookup"><span data-stu-id="5b147-113">[in] Download was successful.</span></span> <span data-ttu-id="5b147-114">客户端从服务器下载信息之后对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="5b147-114">The client sets this after downloading information from the server.</span></span>
    
<span data-ttu-id="5b147-115">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="5b147-115">_pstmReserved_</span></span>
  
> <span data-ttu-id="5b147-116">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="5b147-116">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="5b147-117">_pxihc_</span><span class="sxs-lookup"><span data-stu-id="5b147-117">_pxihc_</span></span>
  
>  <span data-ttu-id="5b147-118">[传出] 指向支持下载增量层次结构更改的 **IExchangeImportHierarchyChanges** 层次结构界面的指针。</span><span class="sxs-lookup"><span data-stu-id="5b147-118">[out] Pointer to the **IExchangeImportHierarchyChanges** hierarchy interface that supports downloading incremental hierarchy changes.</span></span> <span data-ttu-id="5b147-119">有关 **IExchangeImportHierarchyChanges** 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5b147-119">For more information on **IExchangeImportHierarchyChanges**, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="5b147-120">_cEntNew_</span><span class="sxs-lookup"><span data-stu-id="5b147-120">_cEntNew_</span></span>
  
> <span data-ttu-id="5b147-121">[传出] 添加到本地存储的文件夹的数量。</span><span class="sxs-lookup"><span data-stu-id="5b147-121">[out] Number of folders added to the local store.</span></span> <span data-ttu-id="5b147-122">Outlook 在下载期间使用 ICS 时填充此值。</span><span class="sxs-lookup"><span data-stu-id="5b147-122">Outlook populates this value during the downloading when using ICS.</span></span>
    
<span data-ttu-id="5b147-123">_cEntMod_</span><span class="sxs-lookup"><span data-stu-id="5b147-123">_cEntMod_</span></span>
  
> <span data-ttu-id="5b147-124">[传出] 本地存储上要修改的文件夹数量。</span><span class="sxs-lookup"><span data-stu-id="5b147-124">[out] Number of folders to be modified on the local store.</span></span> <span data-ttu-id="5b147-125">Outlook 在下载期间使用 ICS 时填充此值。</span><span class="sxs-lookup"><span data-stu-id="5b147-125">Outlook populates this value during the downloading when using ICS.</span></span>
    
<span data-ttu-id="5b147-126">_cEntDel_</span><span class="sxs-lookup"><span data-stu-id="5b147-126">_cEntDel_</span></span>
  
> <span data-ttu-id="5b147-127">[传出] 本地存储上要删除的文件夹数量。</span><span class="sxs-lookup"><span data-stu-id="5b147-127">[out] Number of folders to be deleted on the local store.</span></span> <span data-ttu-id="5b147-128">Outlook 在下载期间使用 ICS 时填充此值。</span><span class="sxs-lookup"><span data-stu-id="5b147-128">Outlook populates this value during the downloading when using ICS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5b147-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b147-129">See also</span></span>

- [<span data-ttu-id="5b147-130">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="5b147-130">About the Replication State Machine</span></span>](about-the-replication-state-machine.md) 
- [<span data-ttu-id="5b147-131">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="5b147-131">MAPI constants</span></span>](mapi-constants.md)

