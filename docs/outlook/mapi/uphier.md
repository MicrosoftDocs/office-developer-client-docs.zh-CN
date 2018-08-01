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
ms.openlocfilehash: 041ae867ff3a9cc9636ff1d93f9360576e455420
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779047"
---
# <a name="uphier"></a><span data-ttu-id="3d1e2-103">UPHIER</span><span class="sxs-lookup"><span data-stu-id="3d1e2-103">UPHIER</span></span>
 
<span data-ttu-id="3d1e2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3d1e2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3d1e2-105">[上载层次结构状态](upload-hierarchy-state.md)期间同步文件夹层次结构的信息。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-105">Information for synchronizing a folder hierarchy during the [upload hierarchy state](upload-hierarchy-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="3d1e2-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="3d1e2-106">Quick info</span></span>

```cpp
struct UPHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    UINT iEnt; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="3d1e2-107">Members</span><span class="sxs-lookup"><span data-stu-id="3d1e2-107">Members</span></span>

<span data-ttu-id="3d1e2-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3d1e2-108">_ulFlags_</span></span>
  
> <span data-ttu-id="3d1e2-109">[in]要同步的文件夹层次结构时修改的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-109">[in] Flags to modify the behavior when synchronizing the folder hierarchy.</span></span>
    
  - <span data-ttu-id="3d1e2-110">UPH_OK</span><span class="sxs-lookup"><span data-stu-id="3d1e2-110">UPH_OK</span></span>
    
    - <span data-ttu-id="3d1e2-111">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-111">[in] Upload was successful.</span></span> <span data-ttu-id="3d1e2-112">客户端设置此后成功上载到服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-112">The client sets this after successfully uploading information to the server.</span></span> <span data-ttu-id="3d1e2-113">时看到此标志，Outlook 清除指定的文件夹层次结构需要更新任何内部记帐信息。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-113">Upon seeing this flag, Outlook clears any internal bookkeeping information that indicated the folder hierarchy needed updating.</span></span> 
    
    - <span data-ttu-id="3d1e2-114">如果上载未成功，则客户端通过 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-114">The client passes the HRESULT if the upload was not successful.</span></span>
    
<span data-ttu-id="3d1e2-115">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="3d1e2-115">_pstmReserved_</span></span>
  
> <span data-ttu-id="3d1e2-116">[输出]此成员仅供 Outlook 内部使用，不支持。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-116">[out] This member is reserved for Outlook internal use and is not supported.</span></span>
    
<span data-ttu-id="3d1e2-117">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="3d1e2-117">_iEnt_</span></span>
  
> <span data-ttu-id="3d1e2-118">[输出]索引来跟踪同步 *%* 由指定的文件夹的数目。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-118">[out] Index to track synchronizing the number of folders specified by  *cEnt*  .</span></span> 
    
<span data-ttu-id="3d1e2-119">_%_</span><span class="sxs-lookup"><span data-stu-id="3d1e2-119">_cEnt_</span></span>
  
> <span data-ttu-id="3d1e2-120">[输出]文件夹的同步的数。</span><span class="sxs-lookup"><span data-stu-id="3d1e2-120">[out] Number of folders that are out of sync.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d1e2-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d1e2-121">See also</span></span>

- [<span data-ttu-id="3d1e2-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="3d1e2-122">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="3d1e2-123">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="3d1e2-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="3d1e2-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3d1e2-124">MAPI Constants</span></span>](mapi-constants.md)

