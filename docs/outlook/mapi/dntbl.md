---
title: DNTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 77835b48-43aa-8518-9712-754e84f1e713
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 6096118d72dfc51fb60025a55f581ebf97b000a7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774836"
---
# <a name="dntbl"></a><span data-ttu-id="16580-103">DNTBL</span><span class="sxs-lookup"><span data-stu-id="16580-103">DNTBL</span></span>
 
<span data-ttu-id="16580-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="16580-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="16580-105">文件夹内容从服务器下载过程中[下载表状态](download-table-state.md)，存储区上的内容的完全同步的一部分的信息。</span><span class="sxs-lookup"><span data-stu-id="16580-105">Information for downloading the contents of a folder from the server during the [download table state](download-table-state.md), as part of a full synchronization for contents on a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="16580-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="16580-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="16580-107">Members</span><span class="sxs-lookup"><span data-stu-id="16580-107">Members</span></span>

<span data-ttu-id="16580-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="16580-108">_ulFlags_</span></span>
  
> <span data-ttu-id="16580-109">[in]若要修改行为的标志</span><span class="sxs-lookup"><span data-stu-id="16580-109">[in] Flags to modify behavior</span></span> 
    
  - <span data-ttu-id="16580-110">DNT_OK</span><span class="sxs-lookup"><span data-stu-id="16580-110">DNT_OK</span></span>
    
    - <span data-ttu-id="16580-111">[in]下载成功。</span><span class="sxs-lookup"><span data-stu-id="16580-111">[in] Download was successful.</span></span> <span data-ttu-id="16580-112">客户端设置从服务器下载信息之后。</span><span class="sxs-lookup"><span data-stu-id="16580-112">The client sets this after downloading information from the server.</span></span>
    
<span data-ttu-id="16580-113">_pstmReserved1_</span><span class="sxs-lookup"><span data-stu-id="16580-113">_pstmReserved1_</span></span>
  
> <span data-ttu-id="16580-114">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-114">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-115">_pstmReserved2_</span><span class="sxs-lookup"><span data-stu-id="16580-115">_pstmReserved2_</span></span>
  
> <span data-ttu-id="16580-116">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-116">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-117">_pstmReserved3_</span><span class="sxs-lookup"><span data-stu-id="16580-117">_pstmReserved3_</span></span>
  
> <span data-ttu-id="16580-118">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-118">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-119">_pstmReserved4_</span><span class="sxs-lookup"><span data-stu-id="16580-119">_pstmReserved4_</span></span>
  
> <span data-ttu-id="16580-120">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-120">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-121">_pxicc_</span><span class="sxs-lookup"><span data-stu-id="16580-121">_pxicc_</span></span>
  
>  <span data-ttu-id="16580-122">[输出]支持下载内容更改的**IExchangeImportContentsChanges**内容接口的指针。</span><span class="sxs-lookup"><span data-stu-id="16580-122">[out] Pointer to the **IExchangeImportContentsChanges** contents interface that supports downloading content changes.</span></span> <span data-ttu-id="16580-123">**IExchangeImportContentsChanges**的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="16580-123">For more information on **IExchangeImportContentsChanges**, see [ICS Evaluation Criteria](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="16580-124">_pxihc_</span><span class="sxs-lookup"><span data-stu-id="16580-124">_pxihc_</span></span>
  
>  <span data-ttu-id="16580-125">[输出]支持下载增量层次结构更改的**IExchangeImportHierarchyChanges**层次结构接口的指针。</span><span class="sxs-lookup"><span data-stu-id="16580-125">[out] Pointer to the **IExchangeImportHierarchyChanges** hierarchy interface that supports downloading incremental hierarchy changes.</span></span> <span data-ttu-id="16580-126">**IExchangeImportHierarchyChanges**的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="16580-126">For more information on **IExchangeImportHierarchyChanges**, see [ICS Evaluation Criteria](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="16580-127">_pszName_</span><span class="sxs-lookup"><span data-stu-id="16580-127">_pszName_</span></span>
  
>  <span data-ttu-id="16580-128">[输出]文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="16580-128">[out] Name of the folder.</span></span> 
    
<span data-ttu-id="16580-129">_ftLastMod_</span><span class="sxs-lookup"><span data-stu-id="16580-129">_ftLastMod_</span></span>
  
>  <span data-ttu-id="16580-130">[输出]文件夹的上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="16580-130">[out] Last modification time of the folder.</span></span> 
    
<span data-ttu-id="16580-131">_ulRights_</span><span class="sxs-lookup"><span data-stu-id="16580-131">_ulRights_</span></span>
  
>  <span data-ttu-id="16580-132">[输出]文件夹的**[PR_RIGHTS](http://msdn.microsoft.com/en-us/library/ee238052%28v=EXCHG.80%29.aspx)** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="16580-132">[out] Value of the **[PR_RIGHTS](http://msdn.microsoft.com/en-us/library/ee238052%28v=EXCHG.80%29.aspx)** property of the folder.</span></span> 
    
<span data-ttu-id="16580-133">_feid_</span><span class="sxs-lookup"><span data-stu-id="16580-133">_feid_</span></span>
  
>  <span data-ttu-id="16580-134">[输出]文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="16580-134">[out] Entry ID of the folder.</span></span> 
    
<span data-ttu-id="16580-135">_uintReserved_</span><span class="sxs-lookup"><span data-stu-id="16580-135">_uintReserved_</span></span>
  
>  <span data-ttu-id="16580-136">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-136">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-137">_rgte_</span><span class="sxs-lookup"><span data-stu-id="16580-137">_rgte_</span></span>
  
> <span data-ttu-id="16580-138">[输出]普通 （或非隐藏） 的更改和关联 （或隐藏） 的项目。</span><span class="sxs-lookup"><span data-stu-id="16580-138">[out] Changes for normal (or non-hidden) and associated (or hidden) items.</span></span>  <span data-ttu-id="16580-139">*rgte [0]* 的普通项目， *rgte [1]* 用于关联的项目。</span><span class="sxs-lookup"><span data-stu-id="16580-139">*rgte[0]*  is for normal items, and  *rgte[1]*  is for associated items.</span></span> <span data-ttu-id="16580-140">Outlook 时使用增量更改同步 (ICS) 下载期间填充此成员。</span><span class="sxs-lookup"><span data-stu-id="16580-140">Outlook populates this member during the downloading when using Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="16580-141">ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="16580-141">For more information on ICS, see [ICS Evaluation Criteria](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="16580-142">_lpsrReserved_</span><span class="sxs-lookup"><span data-stu-id="16580-142">_lpsrReserved_</span></span>
  
>  <span data-ttu-id="16580-143">[in] / [输出] 此成员保留供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-143">[in]/[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-144">_boReserved_</span><span class="sxs-lookup"><span data-stu-id="16580-144">_boReserved_</span></span>
  
>  <span data-ttu-id="16580-145">[in]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-145">[in]This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-146">_pReserved1_</span><span class="sxs-lookup"><span data-stu-id="16580-146">_pReserved1_</span></span>
  
>  <span data-ttu-id="16580-147">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-147">[out]This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="16580-148">_pReserved2_</span><span class="sxs-lookup"><span data-stu-id="16580-148">_pReserved2_</span></span>
  
>  <span data-ttu-id="16580-149">[in]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="16580-149">[in]This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="16580-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16580-150">See also</span></span>

- [<span data-ttu-id="16580-151">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="16580-151">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)  
- [<span data-ttu-id="16580-152">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="16580-152">MAPI Constants</span></span>](mapi-constants.md) 
- [<span data-ttu-id="16580-153">DNTBLE</span><span class="sxs-lookup"><span data-stu-id="16580-153">DNTBLE</span></span>](dntble.md)

