---
title: UPFLD
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6da9d6b6-a016-ccef-77da-3e037c30450d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c8f7bdc5864c049d8db6f38e92a69c97b6f9dc73
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431356"
---
# <a name="upfld"></a><span data-ttu-id="f1b41-103">UPFLD</span><span class="sxs-lookup"><span data-stu-id="f1b41-103">UPFLD</span></span>

<span data-ttu-id="f1b41-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1b41-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1b41-105">上传文件夹状态期间 [上传文件夹的信息](upload-folder-state.md)。</span><span class="sxs-lookup"><span data-stu-id="f1b41-105">Information for uploading a folder during the [upload folder state](upload-folder-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="f1b41-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="f1b41-106">Quick info</span></span>

```cpp
struct UPFLD 
{ 
    ULONG ulFlags; 
    LPMAPIFOLDER pfld; 
    FEID feid; 
}; 

```

## <a name="members"></a><span data-ttu-id="f1b41-107">成员</span><span class="sxs-lookup"><span data-stu-id="f1b41-107">Members</span></span>

<span data-ttu-id="f1b41-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f1b41-108">_ulFlags_</span></span>
  
>  <span data-ttu-id="f1b41-109">[out]/[in] 用于确定启动的适当操作的标志。</span><span class="sxs-lookup"><span data-stu-id="f1b41-109">[out]/[in] Flags to determine appropriate actions for the uplaod.</span></span> 
    
  - <span data-ttu-id="f1b41-110">UPF_NEW</span><span class="sxs-lookup"><span data-stu-id="f1b41-110">UPF_NEW</span></span>
    
    - <span data-ttu-id="f1b41-111">[out]文件夹是新文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1b41-111">[out] Folder is new.</span></span>
    
  - <span data-ttu-id="f1b41-112">UPF_MOD_PARENT</span><span class="sxs-lookup"><span data-stu-id="f1b41-112">UPF_MOD_PARENT</span></span>
    
    - <span data-ttu-id="f1b41-113">[out]文件夹已移动。</span><span class="sxs-lookup"><span data-stu-id="f1b41-113">[out] Folder has been moved.</span></span>
    
  - <span data-ttu-id="f1b41-114">UPF_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="f1b41-114">UPF_MOD_PROPS</span></span>
    
    - <span data-ttu-id="f1b41-115">[out]已修改文件夹属性。</span><span class="sxs-lookup"><span data-stu-id="f1b41-115">[out] Folder properties have been modified.</span></span>
    
  - <span data-ttu-id="f1b41-116">UPF_DEL</span><span class="sxs-lookup"><span data-stu-id="f1b41-116">UPF_DEL</span></span>
    
    - <span data-ttu-id="f1b41-117">[out]已删除文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1b41-117">[out] Folder was deleted.</span></span>
    
  - <span data-ttu-id="f1b41-118">UPF_OK</span><span class="sxs-lookup"><span data-stu-id="f1b41-118">UPF_OK</span></span>
    
    - <span data-ttu-id="f1b41-119">[in]Upload已成功。</span><span class="sxs-lookup"><span data-stu-id="f1b41-119">[in] Upload was successful.</span></span> <span data-ttu-id="f1b41-120">客户端在将文件夹信息上载到服务器后进行设置。</span><span class="sxs-lookup"><span data-stu-id="f1b41-120">The client sets this after uploading folder information to the server.</span></span>
    
<span data-ttu-id="f1b41-121">_pfld_</span><span class="sxs-lookup"><span data-stu-id="f1b41-121">_pfld_</span></span>
  
> <span data-ttu-id="f1b41-122">[out]要上载的打开的文件夹对象。</span><span class="sxs-lookup"><span data-stu-id="f1b41-122">[out] The open folder object to upload.</span></span>
    
<span data-ttu-id="f1b41-123">_feid_</span><span class="sxs-lookup"><span data-stu-id="f1b41-123">_feid_</span></span>
  
> <span data-ttu-id="f1b41-124">[传出] 文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="f1b41-124">[out] Entry ID of the folder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f1b41-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1b41-125">See also</span></span>

- [<span data-ttu-id="f1b41-126">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="f1b41-126">About the Replication API</span></span>](about-the-replication-api.md) 
- [<span data-ttu-id="f1b41-127">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="f1b41-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="f1b41-128">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f1b41-128">MAPI Constants</span></span>](mapi-constants.md)

