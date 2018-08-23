---
title: UPHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a75ca0dd-9c50-2a9f-6c59-1f8020833a01
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a1ec71d7120eab220ee3b11d2a751fba51cee48e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592092"
---
# <a name="uphier"></a><span data-ttu-id="6a98f-103">UPHIER</span><span class="sxs-lookup"><span data-stu-id="6a98f-103">UPHIER</span></span>
 
<span data-ttu-id="6a98f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a98f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a98f-105">[上载层次结构状态](upload-hierarchy-state.md)期间同步文件夹层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="6a98f-105">Information for synchronizing a folder hierarchy during the [upload hierarchy state](upload-hierarchy-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6a98f-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="6a98f-106">Quick info</span></span>

```cpp
struct UPHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    UINT iEnt; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="6a98f-107">Members</span><span class="sxs-lookup"><span data-stu-id="6a98f-107">Members</span></span>

<span data-ttu-id="6a98f-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6a98f-108">_ulFlags_</span></span>
  
> <span data-ttu-id="6a98f-109">[in]要同步的文件夹层次结构时修改的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="6a98f-109">[in] Flags to modify the behavior when synchronizing the folder hierarchy.</span></span>
    
  - <span data-ttu-id="6a98f-110">UPH_OK</span><span class="sxs-lookup"><span data-stu-id="6a98f-110">UPH_OK</span></span>
    
    - <span data-ttu-id="6a98f-111">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="6a98f-111">[in] Upload was successful.</span></span> <span data-ttu-id="6a98f-112">客户端设置此后成功上载到服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="6a98f-112">The client sets this after successfully uploading information to the server.</span></span> <span data-ttu-id="6a98f-113">时看到此标志，Outlook 清除指定的文件夹层次结构需要更新任何内部记帐信息。</span><span class="sxs-lookup"><span data-stu-id="6a98f-113">Upon seeing this flag, Outlook clears any internal bookkeeping information that indicated the folder hierarchy needed updating.</span></span> 
    
    - <span data-ttu-id="6a98f-114">如果上载未成功，则客户端通过 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="6a98f-114">The client passes the HRESULT if the upload was not successful.</span></span>
    
<span data-ttu-id="6a98f-115">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="6a98f-115">_pstmReserved_</span></span>
  
> <span data-ttu-id="6a98f-116">[输出]此成员仅供 Outlook 内部使用，不支持。</span><span class="sxs-lookup"><span data-stu-id="6a98f-116">[out] This member is reserved for Outlook internal use and is not supported.</span></span>
    
<span data-ttu-id="6a98f-117">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="6a98f-117">_iEnt_</span></span>
  
> <span data-ttu-id="6a98f-118">[输出]索引来跟踪同步 *%* 由指定的文件夹的数目。</span><span class="sxs-lookup"><span data-stu-id="6a98f-118">[out] Index to track synchronizing the number of folders specified by  *cEnt*  .</span></span> 
    
<span data-ttu-id="6a98f-119">_%_</span><span class="sxs-lookup"><span data-stu-id="6a98f-119">_cEnt_</span></span>
  
> <span data-ttu-id="6a98f-120">[输出]文件夹的同步的数。</span><span class="sxs-lookup"><span data-stu-id="6a98f-120">[out] Number of folders that are out of sync.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a98f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a98f-121">See also</span></span>

- [<span data-ttu-id="6a98f-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="6a98f-122">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="6a98f-123">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="6a98f-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="6a98f-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6a98f-124">MAPI Constants</span></span>](mapi-constants.md)

