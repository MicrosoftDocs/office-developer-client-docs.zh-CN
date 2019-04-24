---
title: IOlkAccountFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3b2ee5aa-7639-d86d-447e-50bda54aa3ec
description: 释放由 IOlkAccount 接口分配的内存。
ms.openlocfilehash: a7f763ba4fc260a517f8b7df4d3791f4a8fd23b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321334"
---
# <a name="iolkaccountfreememory"></a><span data-ttu-id="d34da-103">IOlkAccount::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="d34da-103">IOlkAccount::FreeMemory</span></span>

<span data-ttu-id="d34da-104">释放由[IOlkAccount](iolkaccount.md)接口分配的内存。</span><span class="sxs-lookup"><span data-stu-id="d34da-104">Frees memory allocated by the [IOlkAccount](iolkaccount.md) interface.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="d34da-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d34da-105">Quick info</span></span>

<span data-ttu-id="d34da-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="d34da-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::FreeMemory (  
    BYTE *pv, 
); 

```

## <a name="parameters"></a><span data-ttu-id="d34da-107">参数</span><span class="sxs-lookup"><span data-stu-id="d34da-107">Parameters</span></span>

<span data-ttu-id="d34da-108">_pv_</span><span class="sxs-lookup"><span data-stu-id="d34da-108">_pv_</span></span>
  
> <span data-ttu-id="d34da-109">实时指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="d34da-109">[in] A pointer to memory to be freed.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="d34da-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d34da-110">Return values</span></span>

<span data-ttu-id="d34da-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="d34da-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d34da-112">注解</span><span class="sxs-lookup"><span data-stu-id="d34da-112">Remarks</span></span>

<span data-ttu-id="d34da-113">使用此方法释放由[IOlkAccount:: GetProp](iolkaccount-getprop.md) (如果指定的帐户属性的值是二进制或字符串类型) 和[IOlkAccount:: GetAccountInfo](iolkaccount-getaccountinfo.md)分配的内存。</span><span class="sxs-lookup"><span data-stu-id="d34da-113">Use this method to free memory allocated by [IOlkAccount::GetProp](iolkaccount-getprop.md) (if the value of the specified account property is a binary or string type) and [IOlkAccount::GetAccountInfo](iolkaccount-getaccountinfo.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d34da-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d34da-114">See also</span></span>

- [<span data-ttu-id="d34da-115">IOlkAccount::GetAccountInfo</span><span class="sxs-lookup"><span data-stu-id="d34da-115">IOlkAccount::GetAccountInfo</span></span>](iolkaccount-getaccountinfo.md)  
- [<span data-ttu-id="d34da-116">IOlkAccount::GetProp</span><span class="sxs-lookup"><span data-stu-id="d34da-116">IOlkAccount::GetProp</span></span>](iolkaccount-getprop.md)

