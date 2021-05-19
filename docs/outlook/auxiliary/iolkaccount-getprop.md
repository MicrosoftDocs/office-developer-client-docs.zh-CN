---
title: IOlkAccountGetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5725eb52-3a78-897d-f9e3-c5a494fb78c0
description: 获取指定帐户属性的值。
ms.openlocfilehash: d24df8cfa9d54bee4614c1f31e12268748b8c986
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433736"
---
# <a name="iolkaccountgetprop"></a><span data-ttu-id="7a201-103">IOlkAccount::GetProp</span><span class="sxs-lookup"><span data-stu-id="7a201-103">IOlkAccount::GetProp</span></span>

<span data-ttu-id="7a201-104">获取指定帐户属性的值。</span><span class="sxs-lookup"><span data-stu-id="7a201-104">Gets the value of the specified account property.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7a201-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="7a201-105">Quick info</span></span>

<span data-ttu-id="7a201-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="7a201-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::GetProp(  
DWORD dwProp, 
ACCT_VARIANT *pVar 
);
```

## <a name="parameters"></a><span data-ttu-id="7a201-107">参数</span><span class="sxs-lookup"><span data-stu-id="7a201-107">Parameters</span></span>

<span data-ttu-id="7a201-108">_dwProp_</span><span class="sxs-lookup"><span data-stu-id="7a201-108">_dwProp_</span></span>
  
> <span data-ttu-id="7a201-109">[in]要获取的帐户属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="7a201-109">[in] The property tag of the account property to get.</span></span>
    
<span data-ttu-id="7a201-110">_pVar_</span><span class="sxs-lookup"><span data-stu-id="7a201-110">_pVar_</span></span>
  
> <span data-ttu-id="7a201-111">[out]指定属性的值。</span><span class="sxs-lookup"><span data-stu-id="7a201-111">[out] The value of the specified property.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="7a201-112">返回值</span><span class="sxs-lookup"><span data-stu-id="7a201-112">Return values</span></span>

|<span data-ttu-id="7a201-113">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="7a201-113">**HRESULT**</span></span>|<span data-ttu-id="7a201-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a201-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a201-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a201-115">S_OK</span></span>  <br/> |<span data-ttu-id="7a201-116">调用成功。</span><span class="sxs-lookup"><span data-stu-id="7a201-116">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="7a201-117">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="7a201-117">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="7a201-118">找不到给定帐户的属性。</span><span class="sxs-lookup"><span data-stu-id="7a201-118">The property is not found for the given account.</span></span>  <br/> |
|<span data-ttu-id="7a201-119">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7a201-119">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="7a201-120">指定了无效的属性标记。</span><span class="sxs-lookup"><span data-stu-id="7a201-120">An invalid property tag has been specified.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7a201-121">备注</span><span class="sxs-lookup"><span data-stu-id="7a201-121">Remarks</span></span>

<span data-ttu-id="7a201-122">此方法返回后，如果帐户属性的值是二进制或字符串类型，则必须使用 [IOlkAccount：：FreeMemory](iolkaccount-freememory.md)释放 *pVar。*</span><span class="sxs-lookup"><span data-stu-id="7a201-122">After this method returns, if the value of the account property is a binary or string type, you must free  *pVar*  by using [IOlkAccount::FreeMemory](iolkaccount-freememory.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a201-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a201-123">See also</span></span>

- [<span data-ttu-id="7a201-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="7a201-124">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="7a201-125">IOlkAccount::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="7a201-125">IOlkAccount::FreeMemory</span></span>](iolkaccount-freememory.md)  
- [<span data-ttu-id="7a201-126">IOlkAccount::SetProp</span><span class="sxs-lookup"><span data-stu-id="7a201-126">IOlkAccount::SetProp</span></span>](iolkaccount-setprop.md)

