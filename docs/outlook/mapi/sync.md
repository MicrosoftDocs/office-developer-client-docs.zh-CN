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
# <a name="sync"></a><span data-ttu-id="b7922-103">SYNC</span><span class="sxs-lookup"><span data-stu-id="b7922-103">SYNC</span></span>

  
  
<span data-ttu-id="b7922-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b7922-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b7922-105">有关在本地存储和服务器之间启动同步的信息。</span><span class="sxs-lookup"><span data-stu-id="b7922-105">Information for starting synchronization between a local store and a server.</span></span> <span data-ttu-id="b7922-106">此信息在[同步状态](synchronize-state.md)期间使用。</span><span class="sxs-lookup"><span data-stu-id="b7922-106">This information is used during the [synchronize state](synchronize-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b7922-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="b7922-107">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="b7922-108">成员</span><span class="sxs-lookup"><span data-stu-id="b7922-108">Members</span></span>

 <span data-ttu-id="b7922-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b7922-109">_ulFlags_</span></span>
  
- <span data-ttu-id="b7922-110">[输出]/[in] 在同步过程中修改行为的以下标志的位掩码:</span><span class="sxs-lookup"><span data-stu-id="b7922-110">[out]/[in] A bitmask of the following flags that modifies the behavior during synchronization:</span></span>
    
- <span data-ttu-id="b7922-111">UPS_UPLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="b7922-111">UPS_UPLOAD_ONLY</span></span>
    
  - <span data-ttu-id="b7922-112">实时客户端将只执行上载。</span><span class="sxs-lookup"><span data-stu-id="b7922-112">[in] The client will be performing only upload.</span></span> <span data-ttu-id="b7922-113">Outlook 仅返回本地修改的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b7922-113">Outlook only returns locally modified folders.</span></span>
    
- <span data-ttu-id="b7922-114">UPS_DNLOAD_ONLY</span><span class="sxs-lookup"><span data-stu-id="b7922-114">UPS_DNLOAD_ONLY</span></span>
    
  - <span data-ttu-id="b7922-115">实时客户端将仅执行下载。</span><span class="sxs-lookup"><span data-stu-id="b7922-115">[in] The client will be performing only download.</span></span> <span data-ttu-id="b7922-116">Outlook 不应清除文件夹的上传位。</span><span class="sxs-lookup"><span data-stu-id="b7922-116">Outlook should not clear upload bits for folders.</span></span>
    
- <span data-ttu-id="b7922-117">UPS_THESE_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="b7922-117">UPS_THESE_FOLDERS</span></span>
    
  - <span data-ttu-id="b7922-118">实时客户端将使用提供的条目 id 同步指定的文件夹集。</span><span class="sxs-lookup"><span data-stu-id="b7922-118">[in] The client will be synchronizing a specified set of folders with the provided entry IDs.</span></span> <span data-ttu-id="b7922-119">此标志可以与**UPS_UPLOAD_ONLY**或**UPS_DNLOAD_ONLY**标志组合使用。</span><span class="sxs-lookup"><span data-stu-id="b7922-119">This flag can be combined with either the **UPS_UPLOAD_ONLY** or **UPS_DNLOAD_ONLY** flag.</span></span> 
    
- <span data-ttu-id="b7922-120">UPS_OK</span><span class="sxs-lookup"><span data-stu-id="b7922-120">UPS_OK</span></span>
    
  - <span data-ttu-id="b7922-121">排除同步成功。</span><span class="sxs-lookup"><span data-stu-id="b7922-121">[out] Synchronization was successful.</span></span> <span data-ttu-id="b7922-122">在上传或完全同步完成后, 客户端会对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="b7922-122">The client sets this after uploading or a full synchronization completes.</span></span>
    
- 
    
    > [!NOTE]
    > <span data-ttu-id="b7922-123">即使客户端可以使用复制 API 上传或完全同步 (上载后下载) 文件夹和项目, 客户端也只指定一次复制的一个方向的*ulFlags* (无论是**UPS_UPLOAD_ONLY**还是**UPS_DNLOAD_ONLY**标志。</span><span class="sxs-lookup"><span data-stu-id="b7922-123">Even though the client can either upload or fully synchronize (upload then download) folders and items with the Replication API, the client specifies  *ulFlags*  with only one direction of the replication at a time — either the **UPS_UPLOAD_ONLY** or **UPS_DNLOAD_ONLY** flag.</span></span> <span data-ttu-id="b7922-124">在完全同步的情况下, 客户端首先使用**UPS_UPLOAD_ONLY**标志执行上载, 然后使用**UPS_DNLOAD_ONLY**标志进行下载。</span><span class="sxs-lookup"><span data-stu-id="b7922-124">In the case of a full synchronization, the client first does an upload with the **UPS_UPLOAD_ONLY** flag, and then a download with the **UPS_DNLOAD_ONLY** flag.</span></span> 
  
 <span data-ttu-id="b7922-125">_pwzPath_</span><span class="sxs-lookup"><span data-stu-id="b7922-125">_pwzPath_</span></span>
  
- <span data-ttu-id="b7922-126">排除指向本地存储区的路径。</span><span class="sxs-lookup"><span data-stu-id="b7922-126">[out] Path to the local store.</span></span>
    
 <span data-ttu-id="b7922-127">_Reserved1_</span><span class="sxs-lookup"><span data-stu-id="b7922-127">_Reserved1_</span></span>
  
- <span data-ttu-id="b7922-128">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7922-128">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="b7922-129">_Reserved2_</span><span class="sxs-lookup"><span data-stu-id="b7922-129">_Reserved2_</span></span>
  
- <span data-ttu-id="b7922-130">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7922-130">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="b7922-131">*pel*</span><span class="sxs-lookup"><span data-stu-id="b7922-131">*pel*</span></span> 
  
- <span data-ttu-id="b7922-132">实时如果已设置**UPS_THESE_FOLDERS** , 则这是要同步的文件夹的条目 id 列表。</span><span class="sxs-lookup"><span data-stu-id="b7922-132">[in] This is the list of entry IDs of the folders to synchronize if **UPS_THESE_FOLDERS** has been set.</span></span> <span data-ttu-id="b7922-133">有关**LPENTRYLIST**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="b7922-133">See mapidefs.h for the type definition of **LPENTRYLIST**.</span></span> 
    
 <span data-ttu-id="b7922-134">_pulFolderOptions_</span><span class="sxs-lookup"><span data-stu-id="b7922-134">_pulFolderOptions_</span></span>
  
- <span data-ttu-id="b7922-135">实时如果已设置**UPS_THESE_FOLDERS** , 则这是*pel*中对应文件夹的文件夹选项的数组。</span><span class="sxs-lookup"><span data-stu-id="b7922-135">[in] This is an array of folder options for corresponding folders in  *pel*  if **UPS_THESE_FOLDERS** has been set.</span></span> <span data-ttu-id="b7922-136">[上载文件夹状态](upload-folder-state.md)期间上载*pel*中列出的每个文件夹时, 将使用这些文件夹选项。</span><span class="sxs-lookup"><span data-stu-id="b7922-136">These folder options are used when uploading each of the folders listed in  *pel*  during the [upload folder state](upload-folder-state.md).</span></span> <span data-ttu-id="b7922-137">有关文件夹选项的详细信息, 请参阅**[UPFLD](upfld.md)**。</span><span class="sxs-lookup"><span data-stu-id="b7922-137">For more information about folder options, see **[UPFLD](upfld.md)**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="b7922-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7922-138">See also</span></span>



[<span data-ttu-id="b7922-139">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="b7922-139">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="b7922-140">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="b7922-140">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="b7922-141">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="b7922-141">MAPI Constants</span></span>](mapi-constants.md)

