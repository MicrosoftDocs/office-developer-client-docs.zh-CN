---
title: UPFLD
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6da9d6b6-a016-ccef-77da-3e037c30450d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f25b3fb967f4ed93ac38487f21145f35413764da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779045"
---
# <a name="upfld"></a><span data-ttu-id="2f978-103">UPFLD</span><span class="sxs-lookup"><span data-stu-id="2f978-103">UPFLD</span></span>

<span data-ttu-id="2f978-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2f978-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2f978-105">用于[上载文件夹状态](upload-folder-state.md)期间上载文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="2f978-105">Information for uploading a folder during the [upload folder state](upload-folder-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2f978-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="2f978-106">Quick info</span></span>

```cpp
struct UPFLD 
{ 
    ULONG ulFlags; 
    LPMAPIFOLDER pfld; 
    FEID feid; 
}; 

```

## <a name="members"></a><span data-ttu-id="2f978-107">Members</span><span class="sxs-lookup"><span data-stu-id="2f978-107">Members</span></span>

<span data-ttu-id="2f978-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2f978-108">_ulFlags_</span></span>
  
>  <span data-ttu-id="2f978-109">[out] / [输入] 要确定相应操作 uplaod 标志。</span><span class="sxs-lookup"><span data-stu-id="2f978-109">[out]/[in] Flags to determine appropriate actions for the uplaod.</span></span> 
    
  - <span data-ttu-id="2f978-110">UPF_NEW</span><span class="sxs-lookup"><span data-stu-id="2f978-110">UPF_NEW</span></span>
    
    - <span data-ttu-id="2f978-111">[输出]新文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f978-111">[out] Folder is new.</span></span>
    
  - <span data-ttu-id="2f978-112">UPF_MOD_PARENT</span><span class="sxs-lookup"><span data-stu-id="2f978-112">UPF_MOD_PARENT</span></span>
    
    - <span data-ttu-id="2f978-113">[输出]已移动文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f978-113">[out] Folder has been moved.</span></span>
    
  - <span data-ttu-id="2f978-114">UPF_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="2f978-114">UPF_MOD_PROPS</span></span>
    
    - <span data-ttu-id="2f978-115">[输出]文件夹属性已被修改。</span><span class="sxs-lookup"><span data-stu-id="2f978-115">[out] Folder properties have been modified.</span></span>
    
  - <span data-ttu-id="2f978-116">UPF_DEL</span><span class="sxs-lookup"><span data-stu-id="2f978-116">UPF_DEL</span></span>
    
    - <span data-ttu-id="2f978-117">[输出]已删除文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f978-117">[out] Folder was deleted.</span></span>
    
  - <span data-ttu-id="2f978-118">UPF_OK</span><span class="sxs-lookup"><span data-stu-id="2f978-118">UPF_OK</span></span>
    
    - <span data-ttu-id="2f978-119">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="2f978-119">[in] Upload was successful.</span></span> <span data-ttu-id="2f978-120">客户端设置后将文件夹信息上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="2f978-120">The client sets this after uploading folder information to the server.</span></span>
    
<span data-ttu-id="2f978-121">_pfld_</span><span class="sxs-lookup"><span data-stu-id="2f978-121">_pfld_</span></span>
  
> <span data-ttu-id="2f978-122">[输出]要上载的打开的文件夹对象。</span><span class="sxs-lookup"><span data-stu-id="2f978-122">[out] The open folder object to upload.</span></span>
    
<span data-ttu-id="2f978-123">_feid_</span><span class="sxs-lookup"><span data-stu-id="2f978-123">_feid_</span></span>
  
> <span data-ttu-id="2f978-124">[输出]文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="2f978-124">[out] Entry ID of the folder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2f978-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f978-125">See also</span></span>

- [<span data-ttu-id="2f978-126">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="2f978-126">About the Replication API</span></span>](about-the-replication-api.md) 
- [<span data-ttu-id="2f978-127">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="2f978-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="2f978-128">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2f978-128">MAPI Constants</span></span>](mapi-constants.md)

