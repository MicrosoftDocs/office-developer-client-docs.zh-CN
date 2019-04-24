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
ms.openlocfilehash: 8e8a6ac07e14af52337b6e280fa58274df453c65
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299704"
---
# <a name="getdefcachedmode"></a><span data-ttu-id="17aeb-103">GetDefCachedMode</span><span class="sxs-lookup"><span data-stu-id="17aeb-103">GetDefCachedMode</span></span>

  
  
<span data-ttu-id="17aeb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17aeb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17aeb-105">指示是否启用专用 exchange 存储的缓存 Exchange 模式, 以及是否通过策略强制实施。</span><span class="sxs-lookup"><span data-stu-id="17aeb-105">Indicates whether Cached Exchange Mode for the private Exchange store is enabled, and whether this is enforced by policy.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="17aeb-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="17aeb-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="17aeb-107">导出者:</span><span class="sxs-lookup"><span data-stu-id="17aeb-107">Exported by:</span></span>  <br/> |<span data-ttu-id="17aeb-108">msmapi32</span><span class="sxs-lookup"><span data-stu-id="17aeb-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="17aeb-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="17aeb-109">Called by:</span></span>  <br/> |<span data-ttu-id="17aeb-110">客户端</span><span class="sxs-lookup"><span data-stu-id="17aeb-110">Client</span></span>  <br/> |
|<span data-ttu-id="17aeb-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="17aeb-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="17aeb-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="17aeb-112">Outlook</span></span>  <br/> |
   
```cpp
BOOL GetDefCachedMode(BOOL *pfPolicy); 

```

## <a name="parameters"></a><span data-ttu-id="17aeb-113">参数</span><span class="sxs-lookup"><span data-stu-id="17aeb-113">Parameters</span></span>

 <span data-ttu-id="17aeb-114">_pfPolicy_</span><span class="sxs-lookup"><span data-stu-id="17aeb-114">_pfPolicy_</span></span>
  
> <span data-ttu-id="17aeb-115">排除如果返回值由策略强制, 则**为 true** ; 如果不是, 则为**false** 。</span><span class="sxs-lookup"><span data-stu-id="17aeb-115">[out] **true** if the return value is enforced by policy, **false** if it is not.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="17aeb-116">返回值</span><span class="sxs-lookup"><span data-stu-id="17aeb-116">Return values</span></span>

 <span data-ttu-id="17aeb-117">**true**</span><span class="sxs-lookup"><span data-stu-id="17aeb-117">**true**</span></span>
  
- <span data-ttu-id="17aeb-118">启用缓存。</span><span class="sxs-lookup"><span data-stu-id="17aeb-118">Caching is enabled.</span></span>
    
 <span data-ttu-id="17aeb-119">**该值**</span><span class="sxs-lookup"><span data-stu-id="17aeb-119">**false**</span></span>
  
- <span data-ttu-id="17aeb-120">缓存被禁用。</span><span class="sxs-lookup"><span data-stu-id="17aeb-120">Caching is disabled.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="17aeb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17aeb-121">See also</span></span>



[<span data-ttu-id="17aeb-122">GetDefCachedModeDownloadPubFoldFavs</span><span class="sxs-lookup"><span data-stu-id="17aeb-122">GetDefCachedModeDownloadPubFoldFavs</span></span>](getdefcachedmodedownloadpubfoldfavs.md)

