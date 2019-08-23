---
title: DNTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 77835b48-43aa-8518-9712-754e84f1e713
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 4716a6f42968d7451a5db36173c4e6a9e843c08e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337000"
---
# <a name="dntbl"></a><span data-ttu-id="d9755-103">DNTBL</span><span class="sxs-lookup"><span data-stu-id="d9755-103">DNTBL</span></span>
 
<span data-ttu-id="d9755-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9755-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9755-105">在[下载表状态](download-table-state.md)期间从服务器下载文件夹内容的信息，作为存储上内容完全同步的一部分。</span><span class="sxs-lookup"><span data-stu-id="d9755-105">Information for downloading the contents of a folder from the server during the [download table state](download-table-state.md), as part of a full synchronization for contents on a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d9755-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="d9755-106">Quick info</span></span>

```cpp
struct DNTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved1; 
    LPSTREAM pstmReserved2; 
    LPSTREAM pstmReserved3; 
    LPSTREAM pstmReserved4; 
    PXICC pxicc; 
    PXIHC pxihc; 
    LPSTR pszName; 
    FILETIME ftLastMod; 
    ULONG ulRights; 
    FEID feid; 
    UINT uintReserved; 
    DNTBLE rgte[2]; 
    LPSRestriction psrReserved; 
    BOOL boReserved; 
    void* pReserved1; 
    void* pReserved2; 
};

```

## <a name="members"></a><span data-ttu-id="d9755-107">成员</span><span class="sxs-lookup"><span data-stu-id="d9755-107">Members</span></span>

<span data-ttu-id="d9755-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d9755-108">_ulFlags_</span></span>
  
> <span data-ttu-id="d9755-109">[传入] 修改行为的标签</span><span class="sxs-lookup"><span data-stu-id="d9755-109">[in] Flags to modify behavior</span></span> 
    
  - <span data-ttu-id="d9755-110">DNT_OK</span><span class="sxs-lookup"><span data-stu-id="d9755-110">DNT_OK</span></span>
    
    - <span data-ttu-id="d9755-111">[传入] 下载成功。</span><span class="sxs-lookup"><span data-stu-id="d9755-111">[in] Download was successful.</span></span> <span data-ttu-id="d9755-112">客户端从服务器下载信息之后对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="d9755-112">The client sets this after downloading information from the server.</span></span>
    
<span data-ttu-id="d9755-113">_pstmReserved1_</span><span class="sxs-lookup"><span data-stu-id="d9755-113">_pstmReserved1_</span></span>
  
> <span data-ttu-id="d9755-114">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-114">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-115">_pstmReserved2_</span><span class="sxs-lookup"><span data-stu-id="d9755-115">_pstmReserved2_</span></span>
  
> <span data-ttu-id="d9755-116">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-116">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-117">_pstmReserved3_</span><span class="sxs-lookup"><span data-stu-id="d9755-117">_pstmReserved3_</span></span>
  
> <span data-ttu-id="d9755-118">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-118">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-119">_pstmReserved4_</span><span class="sxs-lookup"><span data-stu-id="d9755-119">_pstmReserved4_</span></span>
  
> <span data-ttu-id="d9755-120">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-120">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-121">_pxicc_</span><span class="sxs-lookup"><span data-stu-id="d9755-121">_pxicc_</span></span>
  
>  <span data-ttu-id="d9755-122">[传出] 指向支持下载内容更改的 **IExchangeImportContentsChanges** 内容界面的指针。</span><span class="sxs-lookup"><span data-stu-id="d9755-122">[out] Pointer to the **IExchangeImportContentsChanges** contents interface that supports downloading content changes.</span></span> <span data-ttu-id="d9755-123">有关 **IExchangeImportContentsChanges** 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d9755-123">For more information on **IExchangeImportContentsChanges**, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="d9755-124">_pxihc_</span><span class="sxs-lookup"><span data-stu-id="d9755-124">_pxihc_</span></span>
  
>  <span data-ttu-id="d9755-125">[传出] 指向支持下载增量层次结构更改的 **IExchangeImportHierarchyChanges** 层次结构界面的指针。</span><span class="sxs-lookup"><span data-stu-id="d9755-125">[out] Pointer to the **IExchangeImportHierarchyChanges** hierarchy interface that supports downloading incremental hierarchy changes.</span></span> <span data-ttu-id="d9755-126">有关 **IExchangeImportHierarchyChanges** 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d9755-126">For more information on **IExchangeImportHierarchyChanges**, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="d9755-127">_pszName_</span><span class="sxs-lookup"><span data-stu-id="d9755-127">_pszName_</span></span>
  
>  <span data-ttu-id="d9755-128">[传出] 文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="d9755-128">[out] Name of the folder.</span></span> 
    
<span data-ttu-id="d9755-129">_ftLastMod_</span><span class="sxs-lookup"><span data-stu-id="d9755-129">_ftLastMod_</span></span>
  
>  <span data-ttu-id="d9755-130">[传出] 文件夹的上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="d9755-130">[out] Last modification time of the folder.</span></span> 
    
<span data-ttu-id="d9755-131">_ulRights_</span><span class="sxs-lookup"><span data-stu-id="d9755-131">_ulRights_</span></span>
  
>  <span data-ttu-id="d9755-132">[传出] 文件夹的 **[PR_RIGHTS](https://msdn.microsoft.com/library/ee238052%28v=EXCHG.80%29.aspx)** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="d9755-132">[out] Value of the **[PR_RIGHTS](https://msdn.microsoft.com/library/ee238052%28v=EXCHG.80%29.aspx)** property of the folder.</span></span> 
    
<span data-ttu-id="d9755-133">_feid_</span><span class="sxs-lookup"><span data-stu-id="d9755-133">_feid_</span></span>
  
>  <span data-ttu-id="d9755-134">[传出] 文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="d9755-134">[out] Entry ID of the folder.</span></span> 
    
<span data-ttu-id="d9755-135">_uintReserved_</span><span class="sxs-lookup"><span data-stu-id="d9755-135">_uintReserved_</span></span>
  
>  <span data-ttu-id="d9755-136">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-136">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-137">_rgte_</span><span class="sxs-lookup"><span data-stu-id="d9755-137">_rgte_</span></span>
  
> <span data-ttu-id="d9755-138">[传出] 普通（或非隐藏）和关联（或隐藏）项的更改。</span><span class="sxs-lookup"><span data-stu-id="d9755-138">[out] Changes for normal (or non-hidden) and associated (or hidden) items.</span></span>  <span data-ttu-id="d9755-139">*rgte[0]* 用于普通项，*rgte[1]* 用于关联项。</span><span class="sxs-lookup"><span data-stu-id="d9755-139">*rgte[0]*  is for normal items, and  *rgte[1]*  is for associated items.</span></span> <span data-ttu-id="d9755-140">Outlook 在下载期间使用增量更改同步 (ICS) 填充此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-140">Outlook populates this member during the downloading when using Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="d9755-141">有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d9755-141">For more information on ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="d9755-142">_lpsrReserved_</span><span class="sxs-lookup"><span data-stu-id="d9755-142">_lpsrReserved_</span></span>
  
>  <span data-ttu-id="d9755-143">[传入] /[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-143">[in]/[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-144">_boReserved_</span><span class="sxs-lookup"><span data-stu-id="d9755-144">_boReserved_</span></span>
  
>  <span data-ttu-id="d9755-145">[传入] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-145">[in]This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-146">_pReserved1_</span><span class="sxs-lookup"><span data-stu-id="d9755-146">_pReserved1_</span></span>
  
>  <span data-ttu-id="d9755-147">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-147">[out]This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="d9755-148">_pReserved2_</span><span class="sxs-lookup"><span data-stu-id="d9755-148">_pReserved2_</span></span>
  
>  <span data-ttu-id="d9755-149">[传入] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="d9755-149">[in]This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="d9755-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9755-150">See also</span></span>

- [<span data-ttu-id="d9755-151">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="d9755-151">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)  
- [<span data-ttu-id="d9755-152">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d9755-152">MAPI Constants</span></span>](mapi-constants.md) 
- [<span data-ttu-id="d9755-153">DNTBLE</span><span class="sxs-lookup"><span data-stu-id="d9755-153">DNTBLE</span></span>](dntble.md)

