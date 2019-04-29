---
title: GetDefCachedModeDownloadPubFoldFavs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2dd95561-ed8f-8a3b-6532-b53556f16666
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e623c9d40ffd2dd276bd9601676244644bb3402
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417705"
---
# <a name="getdefcachedmodedownloadpubfoldfavs"></a><span data-ttu-id="aeb89-103">GetDefCachedModeDownloadPubFoldFavs</span><span class="sxs-lookup"><span data-stu-id="aeb89-103">GetDefCachedModeDownloadPubFoldFavs</span></span>

  
  
<span data-ttu-id="aeb89-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aeb89-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aeb89-105">指示是否已启用**公用文件夹收藏夹**文件夹的缓存 Exchange 模式, 以及是否由策略强制执行此功能。</span><span class="sxs-lookup"><span data-stu-id="aeb89-105">Indicates whether Cached Exchange Mode for the **Public Folder Favorites** folder is enabled, and whether this is enforced by policy.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="aeb89-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="aeb89-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="aeb89-107">导出者:</span><span class="sxs-lookup"><span data-stu-id="aeb89-107">Exported by:</span></span>  <br/> |<span data-ttu-id="aeb89-108">msmapi32</span><span class="sxs-lookup"><span data-stu-id="aeb89-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="aeb89-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="aeb89-109">Called by:</span></span>  <br/> |<span data-ttu-id="aeb89-110">Client</span><span class="sxs-lookup"><span data-stu-id="aeb89-110">Client</span></span>  <br/> |
|<span data-ttu-id="aeb89-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="aeb89-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="aeb89-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="aeb89-112">Outlook</span></span>  <br/> |
   
```cpp
BOOL GetDefCachedModeDownloadPubFoldFavs(BOOL *pfPolicy); 

```

## <a name="parameters"></a><span data-ttu-id="aeb89-113">参数</span><span class="sxs-lookup"><span data-stu-id="aeb89-113">Parameters</span></span>

 <span data-ttu-id="aeb89-114">_pfPolicy_</span><span class="sxs-lookup"><span data-stu-id="aeb89-114">_pfPolicy_</span></span>
  
> <span data-ttu-id="aeb89-115">排除如果返回值由策略强制, 则**为 true** ; 如果不是, 则为**false** 。</span><span class="sxs-lookup"><span data-stu-id="aeb89-115">[out] **true** if the return value is enforced by policy, **false** if it is not.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="aeb89-116">返回值</span><span class="sxs-lookup"><span data-stu-id="aeb89-116">Return values</span></span>

 <span data-ttu-id="aeb89-117">**true**</span><span class="sxs-lookup"><span data-stu-id="aeb89-117">**true**</span></span>
  
- <span data-ttu-id="aeb89-118">启用缓存。</span><span class="sxs-lookup"><span data-stu-id="aeb89-118">Caching is enabled.</span></span>
    
 <span data-ttu-id="aeb89-119">**该值**</span><span class="sxs-lookup"><span data-stu-id="aeb89-119">**false**</span></span>
  
- <span data-ttu-id="aeb89-120">缓存被禁用。</span><span class="sxs-lookup"><span data-stu-id="aeb89-120">Caching is disabled.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aeb89-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aeb89-121">See also</span></span>



[<span data-ttu-id="aeb89-122">GetDefCachedMode</span><span class="sxs-lookup"><span data-stu-id="aeb89-122">GetDefCachedMode</span></span>](getdefcachedmode.md)

