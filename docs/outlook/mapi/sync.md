---
title: SYNC
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3f07fddf-4c42-6ea7-162d-57022166a83f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e856044a1b6345c4e495a75dfb7ca0defa52ceec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433806"
---
# <a name="sync"></a><span data-ttu-id="a321d-103">SYNC</span><span class="sxs-lookup"><span data-stu-id="a321d-103">SYNC</span></span>

  
  
<span data-ttu-id="a321d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a321d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a321d-105">在本地存储与服务器之间启动同步的信息。</span><span class="sxs-lookup"><span data-stu-id="a321d-105">Information for starting synchronization between a local store and a server.</span></span> <span data-ttu-id="a321d-106">此信息在同步状态 [期间使用](synchronize-state.md)。</span><span class="sxs-lookup"><span data-stu-id="a321d-106">This information is used during the [synchronize state](synchronize-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a321d-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="a321d-107">Quick info</span></span>

```cpp
struct SYNC 
{ 
    ULONG ulFlags; 
    LPWSTR pwzPath; 
    FEID Reserved1; 
    MEID Reserved2; 
    LPENTRYLIST pel; 
    ULONG const * pulFolderOptions; 
};
```

## <a name="members"></a><span data-ttu-id="a321d-108">成员</span><span class="sxs-lookup"><span data-stu-id="a321d-108">Members</span></span>

 <span data-ttu-id="a321d-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a321d-109">_ulFlags_</span></span>
  
- <span data-ttu-id="a321d-110">[out]/[in] 在同步期间修改行为的以下标志的位掩码：</span><span class="sxs-lookup"><span data-stu-id="a321d-110">[out]/[in] A bitmask of the following flags that modifies the behavior during synchronization:</span></span>
    
- <span data-ttu-id="a321d-111">UPS_UPLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="a321d-111">UPS_UPLOAD_ONLY</span></span>
    
  - <span data-ttu-id="a321d-112">[in]客户端将仅执行上载。</span><span class="sxs-lookup"><span data-stu-id="a321d-112">[in] The client will be performing only upload.</span></span> <span data-ttu-id="a321d-113">Outlook返回本地修改的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a321d-113">Outlook only returns locally modified folders.</span></span>
    
- <span data-ttu-id="a321d-114">UPS_DNLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="a321d-114">UPS_DNLOAD_ONLY</span></span>
    
  - <span data-ttu-id="a321d-115">[in]客户端将仅执行下载。</span><span class="sxs-lookup"><span data-stu-id="a321d-115">[in] The client will be performing only download.</span></span> <span data-ttu-id="a321d-116">Outlook无法清除文件夹的上载位。</span><span class="sxs-lookup"><span data-stu-id="a321d-116">Outlook should not clear upload bits for folders.</span></span>
    
- <span data-ttu-id="a321d-117">UPS_THESE_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="a321d-117">UPS_THESE_FOLDERS</span></span>
    
  - <span data-ttu-id="a321d-118">[in]客户端将同步指定的文件夹集与提供的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="a321d-118">[in] The client will be synchronizing a specified set of folders with the provided entry IDs.</span></span> <span data-ttu-id="a321d-119">此标志可以与 UPS_UPLOAD_ONLY **或\*\*\*\*UPS_DNLOAD_ONLY** 标志结合使用。</span><span class="sxs-lookup"><span data-stu-id="a321d-119">This flag can be combined with either the **UPS_UPLOAD_ONLY** or **UPS_DNLOAD_ONLY** flag.</span></span> 
    
- <span data-ttu-id="a321d-120">UPS_OK</span><span class="sxs-lookup"><span data-stu-id="a321d-120">UPS_OK</span></span>
    
  - <span data-ttu-id="a321d-121">[out]同步成功。</span><span class="sxs-lookup"><span data-stu-id="a321d-121">[out] Synchronization was successful.</span></span> <span data-ttu-id="a321d-122">客户端在上载或完全同步完成后进行设置。</span><span class="sxs-lookup"><span data-stu-id="a321d-122">The client sets this after uploading or a full synchronization completes.</span></span>
    
- 
    
    > [!NOTE]
    > <span data-ttu-id="a321d-123">即使客户端可以上载或完全同步 (上载，然后使用复制 API 下载) 文件夹和项目，但客户端一次仅指定一个方向的  *ulFlags（* **UPS_UPLOAD_ONLY** 或 **UPS_DNLOAD_ONLY** 标记）。</span><span class="sxs-lookup"><span data-stu-id="a321d-123">Even though the client can either upload or fully synchronize (upload then download) folders and items with the Replication API, the client specifies  *ulFlags*  with only one direction of the replication at a time — either the **UPS_UPLOAD_ONLY** or **UPS_DNLOAD_ONLY** flag.</span></span> <span data-ttu-id="a321d-124">在完全同步的情况下，客户端首先执行具有 UPS_UPLOAD_ONLY 标志的上载， **然后** 执行具有 UPS_DNLOAD_ONLY **标记的** 下载。</span><span class="sxs-lookup"><span data-stu-id="a321d-124">In the case of a full synchronization, the client first does an upload with the **UPS_UPLOAD_ONLY** flag, and then a download with the **UPS_DNLOAD_ONLY** flag.</span></span> 
  
 <span data-ttu-id="a321d-125">_pwzPath_</span><span class="sxs-lookup"><span data-stu-id="a321d-125">_pwzPath_</span></span>
  
- <span data-ttu-id="a321d-126">[out]本地存储的路径。</span><span class="sxs-lookup"><span data-stu-id="a321d-126">[out] Path to the local store.</span></span>
    
 <span data-ttu-id="a321d-127">_Reserved1_</span><span class="sxs-lookup"><span data-stu-id="a321d-127">_Reserved1_</span></span>
  
- <span data-ttu-id="a321d-128">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="a321d-128">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="a321d-129">_Reserved2_</span><span class="sxs-lookup"><span data-stu-id="a321d-129">_Reserved2_</span></span>
  
- <span data-ttu-id="a321d-130">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="a321d-130">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="a321d-131">*pel*</span><span class="sxs-lookup"><span data-stu-id="a321d-131">*pel*</span></span> 
  
- <span data-ttu-id="a321d-132">[in]这是要同步的文件夹的条目 **UPS_THESE_FOLDERS已设置** 。</span><span class="sxs-lookup"><span data-stu-id="a321d-132">[in] This is the list of entry IDs of the folders to synchronize if **UPS_THESE_FOLDERS** has been set.</span></span> <span data-ttu-id="a321d-133">有关 **LPENTRYLIST** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="a321d-133">See mapidefs.h for the type definition of **LPENTRYLIST**.</span></span> 
    
 <span data-ttu-id="a321d-134">_将folderOptions_</span><span class="sxs-lookup"><span data-stu-id="a321d-134">_pulFolderOptions_</span></span>
  
- <span data-ttu-id="a321d-135">[in]这是  *pel*  中相应文件夹的文件夹选项数组（ **如果UPS_THESE_FOLDERS** 已设置）。</span><span class="sxs-lookup"><span data-stu-id="a321d-135">[in] This is an array of folder options for corresponding folders in  *pel*  if **UPS_THESE_FOLDERS** has been set.</span></span> <span data-ttu-id="a321d-136">在上传文件夹状态期间上传  *pel*  中列出的每个文件夹时，会使用这些 [文件夹选项](upload-folder-state.md)。</span><span class="sxs-lookup"><span data-stu-id="a321d-136">These folder options are used when uploading each of the folders listed in  *pel*  during the [upload folder state](upload-folder-state.md).</span></span> <span data-ttu-id="a321d-137">有关文件夹选项的详细信息，请参阅 **[UPFLD](upfld.md)**。</span><span class="sxs-lookup"><span data-stu-id="a321d-137">For more information about folder options, see **[UPFLD](upfld.md)**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="a321d-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a321d-138">See also</span></span>



[<span data-ttu-id="a321d-139">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="a321d-139">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="a321d-140">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="a321d-140">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="a321d-141">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="a321d-141">MAPI Constants</span></span>](mapi-constants.md)

