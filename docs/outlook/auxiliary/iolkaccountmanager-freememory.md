---
title: IOlkAccountManagerFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: acb67186-ab38-e918-5402-2526307a5bd0
description: 释放由 IOlkAccountManager 接口分配的内存。
ms.openlocfilehash: 3e680e1e26d6c9b12c2dd4a7d48df4dbeae14154
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408486"
---
# <a name="iolkaccountmanagerfreememory"></a><span data-ttu-id="9c710-103">IOlkAccountManager::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="9c710-103">IOlkAccountManager::FreeMemory</span></span>

<span data-ttu-id="9c710-104">释放由[IOlkAccountManager](iolkaccountmanager.md)接口分配的内存。</span><span class="sxs-lookup"><span data-stu-id="9c710-104">Frees memory allocated by the [IOlkAccountManager](iolkaccountmanager.md) interface.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="9c710-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="9c710-105">Quick info</span></span>

<span data-ttu-id="9c710-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="9c710-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::FreeMemory (  
    BYTE *pv, 
);
```

## <a name="parameters"></a><span data-ttu-id="9c710-107">参数</span><span class="sxs-lookup"><span data-stu-id="9c710-107">Parameters</span></span>

<span data-ttu-id="9c710-108">_pv_</span><span class="sxs-lookup"><span data-stu-id="9c710-108">_pv_</span></span>
  
> <span data-ttu-id="9c710-109">实时指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="9c710-109">[in] A pointer to the memory to free.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="9c710-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9c710-110">Return values</span></span>

<span data-ttu-id="9c710-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="9c710-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9c710-112">说明</span><span class="sxs-lookup"><span data-stu-id="9c710-112">Remarks</span></span>

<span data-ttu-id="9c710-113">使用此方法可释放由[IOlkAccountManager:: GetOrder](iolkaccountmanager-getorder.md)分配的内存。</span><span class="sxs-lookup"><span data-stu-id="9c710-113">Use this method to release memory allocated by [IOlkAccountManager::GetOrder](iolkaccountmanager-getorder.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c710-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c710-114">See also</span></span>

- [<span data-ttu-id="9c710-115">IOlkAccountManager::GetOrder</span><span class="sxs-lookup"><span data-stu-id="9c710-115">IOlkAccountManager::GetOrder</span></span>](iolkaccountmanager-getorder.md)

