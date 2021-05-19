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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414919"
---
# <a name="uphier"></a><span data-ttu-id="cdd00-103">UPHIER</span><span class="sxs-lookup"><span data-stu-id="cdd00-103">UPHIER</span></span>
 
<span data-ttu-id="cdd00-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cdd00-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cdd00-105">在上载层次结构状态期间同步 [文件夹层次结构的信息](upload-hierarchy-state.md)。</span><span class="sxs-lookup"><span data-stu-id="cdd00-105">Information for synchronizing a folder hierarchy during the [upload hierarchy state](upload-hierarchy-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="cdd00-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="cdd00-106">Quick info</span></span>

```cpp
struct UPHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    UINT iEnt; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="cdd00-107">成员</span><span class="sxs-lookup"><span data-stu-id="cdd00-107">Members</span></span>

<span data-ttu-id="cdd00-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cdd00-108">_ulFlags_</span></span>
  
> <span data-ttu-id="cdd00-109">[in]用于修改同步文件夹层次结构时的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="cdd00-109">[in] Flags to modify the behavior when synchronizing the folder hierarchy.</span></span>
    
  - <span data-ttu-id="cdd00-110">UPH_OK</span><span class="sxs-lookup"><span data-stu-id="cdd00-110">UPH_OK</span></span>
    
    - <span data-ttu-id="cdd00-111">[in]Upload已成功。</span><span class="sxs-lookup"><span data-stu-id="cdd00-111">[in] Upload was successful.</span></span> <span data-ttu-id="cdd00-112">客户端在将信息成功上载到服务器后进行设置。</span><span class="sxs-lookup"><span data-stu-id="cdd00-112">The client sets this after successfully uploading information to the server.</span></span> <span data-ttu-id="cdd00-113">看到此标志后，Outlook清除指示文件夹层次结构需要更新的任何内部记帐信息。</span><span class="sxs-lookup"><span data-stu-id="cdd00-113">Upon seeing this flag, Outlook clears any internal bookkeeping information that indicated the folder hierarchy needed updating.</span></span> 
    
    - <span data-ttu-id="cdd00-114">如果上传未成功，客户端将传递 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="cdd00-114">The client passes the HRESULT if the upload was not successful.</span></span>
    
<span data-ttu-id="cdd00-115">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="cdd00-115">_pstmReserved_</span></span>
  
> <span data-ttu-id="cdd00-116">[out]此成员仅供Outlook使用，不受支持。</span><span class="sxs-lookup"><span data-stu-id="cdd00-116">[out] This member is reserved for Outlook internal use and is not supported.</span></span>
    
<span data-ttu-id="cdd00-117">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="cdd00-117">_iEnt_</span></span>
  
> <span data-ttu-id="cdd00-118">[out]索引，跟踪同步  *cEnt 指定的文件夹数*  。</span><span class="sxs-lookup"><span data-stu-id="cdd00-118">[out] Index to track synchronizing the number of folders specified by  *cEnt*  .</span></span> 
    
<span data-ttu-id="cdd00-119">_cEnt_</span><span class="sxs-lookup"><span data-stu-id="cdd00-119">_cEnt_</span></span>
  
> <span data-ttu-id="cdd00-120">[out]不同步的文件夹数。</span><span class="sxs-lookup"><span data-stu-id="cdd00-120">[out] Number of folders that are out of sync.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cdd00-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdd00-121">See also</span></span>

- [<span data-ttu-id="cdd00-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="cdd00-122">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="cdd00-123">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="cdd00-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="cdd00-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="cdd00-124">MAPI Constants</span></span>](mapi-constants.md)

