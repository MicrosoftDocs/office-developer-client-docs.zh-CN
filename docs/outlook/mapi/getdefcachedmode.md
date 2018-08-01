---
title: GetDefCachedMode
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 325b6b47-b6a6-503e-e9bb-65ef7b73d659
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7595fac4346a537eed86550432f56a761c27c0ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775059"
---
# <a name="getdefcachedmode"></a><span data-ttu-id="9a45d-103">GetDefCachedMode</span><span class="sxs-lookup"><span data-stu-id="9a45d-103">GetDefCachedMode</span></span>

  
  
<span data-ttu-id="9a45d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9a45d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9a45d-105">指示是否启用了专用的 Exchange 存储的缓存 Exchange 模式，并且这是否按策略强制实施。</span><span class="sxs-lookup"><span data-stu-id="9a45d-105">Indicates whether Cached Exchange Mode for the private Exchange store is enabled, and whether this is enforced by policy.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="9a45d-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="9a45d-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9a45d-107">导出：</span><span class="sxs-lookup"><span data-stu-id="9a45d-107">Exported by:</span></span>  <br/> |<span data-ttu-id="9a45d-108">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="9a45d-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="9a45d-109">调用：</span><span class="sxs-lookup"><span data-stu-id="9a45d-109">Called by:</span></span>  <br/> |<span data-ttu-id="9a45d-110">客户端</span><span class="sxs-lookup"><span data-stu-id="9a45d-110">Client</span></span>  <br/> |
|<span data-ttu-id="9a45d-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="9a45d-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="9a45d-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="9a45d-112">Outlook</span></span>  <br/> |
   
```cpp
BOOL GetDefCachedMode(BOOL *pfPolicy); 

```

## <a name="parameters"></a><span data-ttu-id="9a45d-113">参数</span><span class="sxs-lookup"><span data-stu-id="9a45d-113">Parameters</span></span>

 <span data-ttu-id="9a45d-114">_pfPolicy_</span><span class="sxs-lookup"><span data-stu-id="9a45d-114">_pfPolicy_</span></span>
  
> <span data-ttu-id="9a45d-115">[输出]如果为**true**如果它不返回值强制实施策略， **false** 。</span><span class="sxs-lookup"><span data-stu-id="9a45d-115">[out] **true** if the return value is enforced by policy, **false** if it is not.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="9a45d-116">返回值</span><span class="sxs-lookup"><span data-stu-id="9a45d-116">Return values</span></span>

 <span data-ttu-id="9a45d-117">**true**</span><span class="sxs-lookup"><span data-stu-id="9a45d-117">**true**</span></span>
  
- <span data-ttu-id="9a45d-118">启用缓存。</span><span class="sxs-lookup"><span data-stu-id="9a45d-118">Caching is enabled.</span></span>
    
 <span data-ttu-id="9a45d-119">**false**</span><span class="sxs-lookup"><span data-stu-id="9a45d-119">**false**</span></span>
  
- <span data-ttu-id="9a45d-120">禁用缓存。</span><span class="sxs-lookup"><span data-stu-id="9a45d-120">Caching is disabled.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9a45d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a45d-121">See also</span></span>



[<span data-ttu-id="9a45d-122">GetDefCachedModeDownloadPubFoldFavs</span><span class="sxs-lookup"><span data-stu-id="9a45d-122">GetDefCachedModeDownloadPubFoldFavs</span></span>](getdefcachedmodedownloadpubfoldfavs.md)

