---
title: UPMOV
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 098743a5-f265-639a-8ba6-1412705bee0a
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: a7588d5fed2e059be7e628d8a76a12f76aea734d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393381"
---
# <a name="upmov"></a><span data-ttu-id="68573-103">UPMOV</span><span class="sxs-lookup"><span data-stu-id="68573-103">UPMOV</span></span>
 
<span data-ttu-id="68573-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68573-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68573-105">用于上载已移动的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="68573-105">Information for uploading items that have been moved.</span></span> <span data-ttu-id="68573-106">[上载删除状态状态](upload-delete-status-state.md)和[上载表状态](upload-table-state.md)期间使用此信息。</span><span class="sxs-lookup"><span data-stu-id="68573-106">This information is used during the [upload delete status state](upload-delete-status-state.md) and [upload table state](upload-table-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="68573-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="68573-107">Quick info</span></span>

```cpp
struct UPMOV 
{ 
      ULONG          ulFlags; 
      LPVOID         pReserved; 
      LPSTREAM       pstmReserved; 
      LPSTR          pszName; 
      FEID           feid; 
      LPMAPIFOLDER   pfld; 
      PXICC          pxicc; 
      DWORD          dwReserved; 
      PUPMOV         pupmovNext; 
      UINT           cEntMov; 
};
```

## <a name="members"></a><span data-ttu-id="68573-108">Members</span><span class="sxs-lookup"><span data-stu-id="68573-108">Members</span></span>

<span data-ttu-id="68573-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="68573-109">_ulFlags_</span></span>
  
> <span data-ttu-id="68573-110">[in]若要在上载过程中确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="68573-110">[in] Flags to determine the appropriate behavior during the upload.</span></span>
    
  - <span data-ttu-id="68573-111">UPV_ERROR</span><span class="sxs-lookup"><span data-stu-id="68573-111">UPV_ERROR</span></span>
    
    - <span data-ttu-id="68573-112">[in]打开服务器文件夹的问题。</span><span class="sxs-lookup"><span data-stu-id="68573-112">[in] Problem opening server folder.</span></span>
    
  - <span data-ttu-id="68573-113">UPV_DIRTY</span><span class="sxs-lookup"><span data-stu-id="68573-113">UPV_DIRTY</span></span>
    
    - <span data-ttu-id="68573-114">[in]上载状态已更改。</span><span class="sxs-lookup"><span data-stu-id="68573-114">[in] The upload state has changed.</span></span> <span data-ttu-id="68573-115">客户端使用此跟踪状态本地存储中的更改。</span><span class="sxs-lookup"><span data-stu-id="68573-115">This is used by the client to track the change in state for the local store.</span></span>
    
  - <span data-ttu-id="68573-116">UPV_COMMIT</span><span class="sxs-lookup"><span data-stu-id="68573-116">UPV_COMMIT</span></span>
    
    - <span data-ttu-id="68573-117">[in]提交上载状态。</span><span class="sxs-lookup"><span data-stu-id="68573-117">[in] Commit upload state.</span></span>
    
<span data-ttu-id="68573-118">_保留_</span><span class="sxs-lookup"><span data-stu-id="68573-118">_pReserved_</span></span>
  
>  <span data-ttu-id="68573-119">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="68573-119">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="68573-120">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="68573-120">_pstmReserved_</span></span>
  
>  <span data-ttu-id="68573-121">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="68573-121">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="68573-122">_pszName_</span><span class="sxs-lookup"><span data-stu-id="68573-122">_pszName_</span></span>
  
>  <span data-ttu-id="68573-123">[输出]目标文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="68573-123">[out] Name of the destination folder.</span></span> 
    
  > [!NOTE]
  > <span data-ttu-id="68573-124">此成员不支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="68573-124">This member does not support UNICODE.</span></span> 
  
<span data-ttu-id="68573-125">_feid_</span><span class="sxs-lookup"><span data-stu-id="68573-125">_feid_</span></span>
  
>  <span data-ttu-id="68573-126">[输出]目标文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="68573-126">[out] Entry ID of destination folder.</span></span> 
    
<span data-ttu-id="68573-127">_pfld_</span><span class="sxs-lookup"><span data-stu-id="68573-127">_pfld_</span></span>
  
>  <span data-ttu-id="68573-128">[in]指向服务器文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="68573-128">[in] Pointer to server folder.</span></span> 
    
<span data-ttu-id="68573-129">_pxicc_</span><span class="sxs-lookup"><span data-stu-id="68573-129">_pxicc_</span></span>
  
>  <span data-ttu-id="68573-130">[in]支持上载内容更改时使用增量更改同步 (ICS) 的**IExchangeImportContentsChanges**内容接口的指针。</span><span class="sxs-lookup"><span data-stu-id="68573-130">[in] Pointer to the **IExchangeImportContentsChanges** contents interface that supports uploading content changes when using Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="68573-131">**IExchangeImportContentsChanges**和 ICS 的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="68573-131">For more information on **IExchangeImportContentsChanges** and ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="68573-132">_dwReserved_</span><span class="sxs-lookup"><span data-stu-id="68573-132">_dwReserved_</span></span>
  
>  <span data-ttu-id="68573-133">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="68573-133">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="68573-134">_pupmovNext_</span><span class="sxs-lookup"><span data-stu-id="68573-134">_pupmovNext_</span></span>
  
>  <span data-ttu-id="68573-135">[输出]接下来移动上下文。</span><span class="sxs-lookup"><span data-stu-id="68573-135">[out] Next move context.</span></span> 
    
<span data-ttu-id="68573-136">_cEntMov_</span><span class="sxs-lookup"><span data-stu-id="68573-136">_cEntMov_</span></span>
  
>  <span data-ttu-id="68573-137">[in]项目数移至此处。</span><span class="sxs-lookup"><span data-stu-id="68573-137">[in] Number of items moved here.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="68573-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68573-138">See also</span></span>

- [<span data-ttu-id="68573-139">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="68573-139">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="68573-140">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="68573-140">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="68573-141">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="68573-141">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="68573-142">FEID</span><span class="sxs-lookup"><span data-stu-id="68573-142">FEID</span></span>](feid.md)
