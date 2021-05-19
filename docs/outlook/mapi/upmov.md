---
title: UPMOV
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 098743a5-f265-639a-8ba6-1412705bee0a
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: a7588d5fed2e059be7e628d8a76a12f76aea734d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339184"
---
# <a name="upmov"></a><span data-ttu-id="6bb2c-103">UPMOV</span><span class="sxs-lookup"><span data-stu-id="6bb2c-103">UPMOV</span></span>
 
<span data-ttu-id="6bb2c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6bb2c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6bb2c-105">有关上载已移动的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-105">Information for uploading items that have been moved.</span></span> <span data-ttu-id="6bb2c-106">此信息在上传删除状态[和上传表状态](upload-delete-status-state.md)[期间使用](upload-table-state.md)。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-106">This information is used during the [upload delete status state](upload-delete-status-state.md) and [upload table state](upload-table-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6bb2c-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="6bb2c-107">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="6bb2c-108">成员</span><span class="sxs-lookup"><span data-stu-id="6bb2c-108">Members</span></span>

<span data-ttu-id="6bb2c-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-109">_ulFlags_</span></span>
  
> <span data-ttu-id="6bb2c-110">[in]用于确定上载过程中的适当行为的标志。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-110">[in] Flags to determine the appropriate behavior during the upload.</span></span>
    
  - <span data-ttu-id="6bb2c-111">UPV_ERROR</span><span class="sxs-lookup"><span data-stu-id="6bb2c-111">UPV_ERROR</span></span>
    
    - <span data-ttu-id="6bb2c-112">[in]打开服务器文件夹时出现问题。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-112">[in] Problem opening server folder.</span></span>
    
  - <span data-ttu-id="6bb2c-113">UPV_DIRTY</span><span class="sxs-lookup"><span data-stu-id="6bb2c-113">UPV_DIRTY</span></span>
    
    - <span data-ttu-id="6bb2c-114">[in]上载状态已更改。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-114">[in] The upload state has changed.</span></span> <span data-ttu-id="6bb2c-115">客户端使用此功能跟踪本地存储的状态更改。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-115">This is used by the client to track the change in state for the local store.</span></span>
    
  - <span data-ttu-id="6bb2c-116">UPV_COMMIT</span><span class="sxs-lookup"><span data-stu-id="6bb2c-116">UPV_COMMIT</span></span>
    
    - <span data-ttu-id="6bb2c-117">[in]提交上传状态。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-117">[in] Commit upload state.</span></span>
    
<span data-ttu-id="6bb2c-118">_pReserved_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-118">_pReserved_</span></span>
  
>  <span data-ttu-id="6bb2c-119">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-119">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="6bb2c-120">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-120">_pstmReserved_</span></span>
  
>  <span data-ttu-id="6bb2c-121">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-121">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="6bb2c-122">_pszName_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-122">_pszName_</span></span>
  
>  <span data-ttu-id="6bb2c-123">[out]目标文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-123">[out] Name of the destination folder.</span></span> 
    
  > [!NOTE]
  > <span data-ttu-id="6bb2c-124">此成员不支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-124">This member does not support UNICODE.</span></span> 
  
<span data-ttu-id="6bb2c-125">_feid_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-125">_feid_</span></span>
  
>  <span data-ttu-id="6bb2c-126">[out]目标文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-126">[out] Entry ID of destination folder.</span></span> 
    
<span data-ttu-id="6bb2c-127">_pfld_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-127">_pfld_</span></span>
  
>  <span data-ttu-id="6bb2c-128">[in]指向服务器文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-128">[in] Pointer to server folder.</span></span> 
    
<span data-ttu-id="6bb2c-129">_pxicc_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-129">_pxicc_</span></span>
  
>  <span data-ttu-id="6bb2c-130">[in]指向 **IExchangeImportContentsChanges** 内容接口的指针，该接口支持在使用 ICS (时上载) 。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-130">[in] Pointer to the **IExchangeImportContentsChanges** contents interface that supports uploading content changes when using Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="6bb2c-131">有关 **IExchangeImportContentsChanges** 和 ICS 的信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-131">For more information on **IExchangeImportContentsChanges** and ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
    
<span data-ttu-id="6bb2c-132">_dwReserved_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-132">_dwReserved_</span></span>
  
>  <span data-ttu-id="6bb2c-133">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-133">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="6bb2c-134">_pupmovNext_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-134">_pupmovNext_</span></span>
  
>  <span data-ttu-id="6bb2c-135">[out]下一个移动上下文。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-135">[out] Next move context.</span></span> 
    
<span data-ttu-id="6bb2c-136">_cEntMov_</span><span class="sxs-lookup"><span data-stu-id="6bb2c-136">_cEntMov_</span></span>
  
>  <span data-ttu-id="6bb2c-137">[in]此处移动的项目数。</span><span class="sxs-lookup"><span data-stu-id="6bb2c-137">[in] Number of items moved here.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6bb2c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bb2c-138">See also</span></span>

- [<span data-ttu-id="6bb2c-139">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="6bb2c-139">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="6bb2c-140">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="6bb2c-140">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="6bb2c-141">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6bb2c-141">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="6bb2c-142">FEID</span><span class="sxs-lookup"><span data-stu-id="6bb2c-142">FEID</span></span>](feid.md)

