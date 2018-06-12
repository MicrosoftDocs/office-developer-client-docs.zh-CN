---
title: GetDefCachedModeDownloadPubFoldFavs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2dd95561-ed8f-8a3b-6532-b53556f16666
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cb93d9ae4e6660c208d74e43bb26be4dbd55f4e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775058"
---
# <a name="getdefcachedmodedownloadpubfoldfavs"></a><span data-ttu-id="33cad-103">GetDefCachedModeDownloadPubFoldFavs</span><span class="sxs-lookup"><span data-stu-id="33cad-103">GetDefCachedModeDownloadPubFoldFavs</span></span>

  
  
<span data-ttu-id="33cad-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="33cad-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="33cad-105">指示是否启用缓存 Exchange 模式下的**公用文件夹收藏夹**文件夹，并且这是否按策略强制实施。</span><span class="sxs-lookup"><span data-stu-id="33cad-105">Indicates whether Cached Exchange Mode for the **Public Folder Favorites** folder is enabled, and whether this is enforced by policy.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="33cad-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="33cad-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="33cad-107">导出：</span><span class="sxs-lookup"><span data-stu-id="33cad-107">Exported by:</span></span>  <br/> |<span data-ttu-id="33cad-108">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="33cad-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="33cad-109">调用：</span><span class="sxs-lookup"><span data-stu-id="33cad-109">Called by:</span></span>  <br/> |<span data-ttu-id="33cad-110">客户端</span><span class="sxs-lookup"><span data-stu-id="33cad-110">Client</span></span>  <br/> |
|<span data-ttu-id="33cad-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="33cad-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="33cad-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="33cad-112">Outlook</span></span>  <br/> |
   
```cpp
BOOL GetDefCachedModeDownloadPubFoldFavs(BOOL *pfPolicy); 

```

## <a name="parameters"></a><span data-ttu-id="33cad-113">参数</span><span class="sxs-lookup"><span data-stu-id="33cad-113">Parameters</span></span>

 <span data-ttu-id="33cad-114">_pfPolicy_</span><span class="sxs-lookup"><span data-stu-id="33cad-114">_pfPolicy_</span></span>
  
> <span data-ttu-id="33cad-115">[输出]如果为**true**如果它不返回值强制实施策略， **false** 。</span><span class="sxs-lookup"><span data-stu-id="33cad-115">[out] **true** if the return value is enforced by policy, **false** if it is not.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="33cad-116">返回值</span><span class="sxs-lookup"><span data-stu-id="33cad-116">Return values</span></span>

 <span data-ttu-id="33cad-117">**true**</span><span class="sxs-lookup"><span data-stu-id="33cad-117">**true**</span></span>
  
- <span data-ttu-id="33cad-118">启用缓存。</span><span class="sxs-lookup"><span data-stu-id="33cad-118">Caching is enabled.</span></span>
    
 <span data-ttu-id="33cad-119">**false**</span><span class="sxs-lookup"><span data-stu-id="33cad-119">**false**</span></span>
  
- <span data-ttu-id="33cad-120">禁用缓存。</span><span class="sxs-lookup"><span data-stu-id="33cad-120">Caching is disabled.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="33cad-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33cad-121">See also</span></span>



[<span data-ttu-id="33cad-122">GetDefCachedMode</span><span class="sxs-lookup"><span data-stu-id="33cad-122">GetDefCachedMode</span></span>](getdefcachedmode.md)

