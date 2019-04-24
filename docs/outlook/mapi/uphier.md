---
title: UPHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a75ca0dd-9c50-2a9f-6c59-1f8020833a01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 45ef7ce9291376ac020035f0bde6172caf6cc01b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359421"
---
# <a name="uphier"></a><span data-ttu-id="6c442-103">UPHIER</span><span class="sxs-lookup"><span data-stu-id="6c442-103">UPHIER</span></span>
 
<span data-ttu-id="6c442-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c442-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c442-105">用于在[上载层次结构状态](upload-hierarchy-state.md)期间同步文件夹层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="6c442-105">Information for synchronizing a folder hierarchy during the [upload hierarchy state](upload-hierarchy-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6c442-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="6c442-106">Quick info</span></span>

```cpp
struct UPHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    UINT iEnt; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="6c442-107">成员</span><span class="sxs-lookup"><span data-stu-id="6c442-107">Members</span></span>

<span data-ttu-id="6c442-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6c442-108">_ulFlags_</span></span>
  
> <span data-ttu-id="6c442-109">实时用于在同步文件夹层次结构时修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="6c442-109">[in] Flags to modify the behavior when synchronizing the folder hierarchy.</span></span>
    
  - <span data-ttu-id="6c442-110">UPH_OK</span><span class="sxs-lookup"><span data-stu-id="6c442-110">UPH_OK</span></span>
    
    - <span data-ttu-id="6c442-111">实时上载成功。</span><span class="sxs-lookup"><span data-stu-id="6c442-111">[in] Upload was successful.</span></span> <span data-ttu-id="6c442-112">在成功将信息上载到服务器后, 客户端会对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="6c442-112">The client sets this after successfully uploading information to the server.</span></span> <span data-ttu-id="6c442-113">在看到此标志之后, Outlook 将清除所有指示文件夹层次结构需要更新的内部簿记信息。</span><span class="sxs-lookup"><span data-stu-id="6c442-113">Upon seeing this flag, Outlook clears any internal bookkeeping information that indicated the folder hierarchy needed updating.</span></span> 
    
    - <span data-ttu-id="6c442-114">如果上载未成功, 客户端将传递 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="6c442-114">The client passes the HRESULT if the upload was not successful.</span></span>
    
<span data-ttu-id="6c442-115">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="6c442-115">_pstmReserved_</span></span>
  
> <span data-ttu-id="6c442-116">排除此成员保留供 Outlook 内部使用, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="6c442-116">[out] This member is reserved for Outlook internal use and is not supported.</span></span>
    
<span data-ttu-id="6c442-117">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="6c442-117">_iEnt_</span></span>
  
> <span data-ttu-id="6c442-118">排除用于跟踪对由*分币*指定的文件夹数进行同步的索引。</span><span class="sxs-lookup"><span data-stu-id="6c442-118">[out] Index to track synchronizing the number of folders specified by  *cEnt*  .</span></span> 
    
<span data-ttu-id="6c442-119">_分币_</span><span class="sxs-lookup"><span data-stu-id="6c442-119">_cEnt_</span></span>
  
> <span data-ttu-id="6c442-120">排除不同步的文件夹数。</span><span class="sxs-lookup"><span data-stu-id="6c442-120">[out] Number of folders that are out of sync.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6c442-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c442-121">See also</span></span>

- [<span data-ttu-id="6c442-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="6c442-122">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="6c442-123">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="6c442-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="6c442-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6c442-124">MAPI Constants</span></span>](mapi-constants.md)

