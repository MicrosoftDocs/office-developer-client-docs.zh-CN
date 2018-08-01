---
title: IOlkAccountManagerFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: acb67186-ab38-e918-5402-2526307a5bd0
description: 释放内存分配 IOlkAccountManager 接口。
ms.openlocfilehash: 85ba4d0d47eb5c879fa562e3147860533ef59f23
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774333"
---
# <a name="iolkaccountmanagerfreememory"></a><span data-ttu-id="d712a-103">IOlkAccountManager::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="d712a-103">IOlkAccountManager::FreeMemory</span></span>

<span data-ttu-id="d712a-104">释放内存分配[IOlkAccountManager](iolkaccountmanager.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d712a-104">Frees memory allocated by the [IOlkAccountManager](iolkaccountmanager.md) interface.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="d712a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d712a-105">Quick info</span></span>

<span data-ttu-id="d712a-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="d712a-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::FreeMemory (  
    BYTE *pv, 
);
```

## <a name="parameters"></a><span data-ttu-id="d712a-107">参数</span><span class="sxs-lookup"><span data-stu-id="d712a-107">Parameters</span></span>

<span data-ttu-id="d712a-108">_pv_</span><span class="sxs-lookup"><span data-stu-id="d712a-108">_pv_</span></span>
  
> <span data-ttu-id="d712a-109">[in]指向以释放内存的指针。</span><span class="sxs-lookup"><span data-stu-id="d712a-109">[in] A pointer to the memory to free.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="d712a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d712a-110">Return values</span></span>

<span data-ttu-id="d712a-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="d712a-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d712a-112">注释</span><span class="sxs-lookup"><span data-stu-id="d712a-112">Remarks</span></span>

<span data-ttu-id="d712a-113">使用此方法释放由[IOlkAccountManager::GetOrder](iolkaccountmanager-getorder.md)分配内存。</span><span class="sxs-lookup"><span data-stu-id="d712a-113">Use this method to release memory allocated by [IOlkAccountManager::GetOrder](iolkaccountmanager-getorder.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d712a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d712a-114">See also</span></span>

- [<span data-ttu-id="d712a-115">IOlkAccountManager::GetOrder</span><span class="sxs-lookup"><span data-stu-id="d712a-115">IOlkAccountManager::GetOrder</span></span>](iolkaccountmanager-getorder.md)

