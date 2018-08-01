---
title: IOlkAccountFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3b2ee5aa-7639-d86d-447e-50bda54aa3ec
description: 释放内存分配 IOlkAccount 接口。
ms.openlocfilehash: ce3046db29cb2cac7d7ee72a3e4e9125346a4ac4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774277"
---
# <a name="iolkaccountfreememory"></a><span data-ttu-id="7276a-103">IOlkAccount::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="7276a-103">IOlkAccount::FreeMemory</span></span>

<span data-ttu-id="7276a-104">释放内存分配[IOlkAccount](iolkaccount.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7276a-104">Frees memory allocated by the [IOlkAccount](iolkaccount.md) interface.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="7276a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="7276a-105">Quick info</span></span>

<span data-ttu-id="7276a-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="7276a-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::FreeMemory (  
    BYTE *pv, 
); 

```

## <a name="parameters"></a><span data-ttu-id="7276a-107">参数</span><span class="sxs-lookup"><span data-stu-id="7276a-107">Parameters</span></span>

<span data-ttu-id="7276a-108">_pv_</span><span class="sxs-lookup"><span data-stu-id="7276a-108">_pv_</span></span>
  
> <span data-ttu-id="7276a-109">[in]指向要释放内存的指针。</span><span class="sxs-lookup"><span data-stu-id="7276a-109">[in] A pointer to memory to be freed.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="7276a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="7276a-110">Return values</span></span>

<span data-ttu-id="7276a-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="7276a-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7276a-112">注释</span><span class="sxs-lookup"><span data-stu-id="7276a-112">Remarks</span></span>

<span data-ttu-id="7276a-113">使用此方法以释放内存分配[IOlkAccount::GetProp](iolkaccount-getprop.md) （如果指定的帐户属性的值为二进制或字符串类型） 和[IOlkAccount::GetAccountInfo](iolkaccount-getaccountinfo.md)。</span><span class="sxs-lookup"><span data-stu-id="7276a-113">Use this method to free memory allocated by [IOlkAccount::GetProp](iolkaccount-getprop.md) (if the value of the specified account property is a binary or string type) and [IOlkAccount::GetAccountInfo](iolkaccount-getaccountinfo.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7276a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7276a-114">See also</span></span>

- [<span data-ttu-id="7276a-115">IOlkAccount::GetAccountInfo</span><span class="sxs-lookup"><span data-stu-id="7276a-115">IOlkAccount::GetAccountInfo</span></span>](iolkaccount-getaccountinfo.md)  
- [<span data-ttu-id="7276a-116">IOlkAccount::GetProp</span><span class="sxs-lookup"><span data-stu-id="7276a-116">IOlkAccount::GetProp</span></span>](iolkaccount-getprop.md)

