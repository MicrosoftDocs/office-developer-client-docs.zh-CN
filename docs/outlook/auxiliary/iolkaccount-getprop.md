---
title: IOlkAccountGetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5725eb52-3a78-897d-f9e3-c5a494fb78c0
description: 获取指定的帐户属性的值。
ms.openlocfilehash: 2c0756f416a209d37eff2209a82c298837f85f3d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774285"
---
# <a name="iolkaccountgetprop"></a><span data-ttu-id="dde59-103">IOlkAccount::GetProp</span><span class="sxs-lookup"><span data-stu-id="dde59-103">IOlkAccount::GetProp</span></span>

<span data-ttu-id="dde59-104">获取指定的帐户属性的值。</span><span class="sxs-lookup"><span data-stu-id="dde59-104">Gets the value of the specified account property.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="dde59-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="dde59-105">Quick info</span></span>

<span data-ttu-id="dde59-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="dde59-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::GetProp(  
DWORD dwProp, 
ACCT_VARIANT *pVar 
);
```

## <a name="parameters"></a><span data-ttu-id="dde59-107">参数</span><span class="sxs-lookup"><span data-stu-id="dde59-107">Parameters</span></span>

<span data-ttu-id="dde59-108">_dwProp_</span><span class="sxs-lookup"><span data-stu-id="dde59-108">_dwProp_</span></span>
  
> <span data-ttu-id="dde59-109">[in]要获取的帐户属性属性标记。</span><span class="sxs-lookup"><span data-stu-id="dde59-109">[in] The property tag of the account property to get.</span></span>
    
<span data-ttu-id="dde59-110">_pVar_</span><span class="sxs-lookup"><span data-stu-id="dde59-110">_pVar_</span></span>
  
> <span data-ttu-id="dde59-111">[输出]指定的属性的值。</span><span class="sxs-lookup"><span data-stu-id="dde59-111">[out] The value of the specified property.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="dde59-112">返回值</span><span class="sxs-lookup"><span data-stu-id="dde59-112">Return values</span></span>

|<span data-ttu-id="dde59-113">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="dde59-113">**HRESULT**</span></span>|<span data-ttu-id="dde59-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="dde59-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dde59-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="dde59-115">S_OK</span></span>  <br/> |<span data-ttu-id="dde59-116">调用成功。</span><span class="sxs-lookup"><span data-stu-id="dde59-116">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="dde59-117">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="dde59-117">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="dde59-118">为给定的帐户未找到属性。</span><span class="sxs-lookup"><span data-stu-id="dde59-118">The property is not found for the given account.</span></span>  <br/> |
|<span data-ttu-id="dde59-119">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dde59-119">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="dde59-120">指定了无效的属性标记。</span><span class="sxs-lookup"><span data-stu-id="dde59-120">An invalid property tag has been specified.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dde59-121">说明</span><span class="sxs-lookup"><span data-stu-id="dde59-121">Remarks</span></span>

<span data-ttu-id="dde59-122">此方法返回，如果帐户属性的值为二进制或字符串类型后，您必须使用[IOlkAccount::FreeMemory](iolkaccount-freememory.md)释放*pVar* 。</span><span class="sxs-lookup"><span data-stu-id="dde59-122">After this method returns, if the value of the account property is a binary or string type, you must free  *pVar*  by using [IOlkAccount::FreeMemory](iolkaccount-freememory.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dde59-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dde59-123">See also</span></span>

- [<span data-ttu-id="dde59-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="dde59-124">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="dde59-125">IOlkAccount::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="dde59-125">IOlkAccount::FreeMemory</span></span>](iolkaccount-freememory.md)  
- [<span data-ttu-id="dde59-126">IOlkAccount::SetProp</span><span class="sxs-lookup"><span data-stu-id="dde59-126">IOlkAccount::SetProp</span></span>](iolkaccount-setprop.md)

