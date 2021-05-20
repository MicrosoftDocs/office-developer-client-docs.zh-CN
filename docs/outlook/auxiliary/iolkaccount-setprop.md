---
title: IOlkAccountSetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 883b1c5d-47dd-a006-b5f1-130691bdd019
description: 设置指定帐户属性的值。
ms.openlocfilehash: 94134cee7886177ab840a6caff7d70d65bf9d4cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431986"
---
# <a name="iolkaccountsetprop"></a><span data-ttu-id="8eafe-103">IOlkAccount::SetProp</span><span class="sxs-lookup"><span data-stu-id="8eafe-103">IOlkAccount::SetProp</span></span>

<span data-ttu-id="8eafe-104">设置指定帐户属性的值。</span><span class="sxs-lookup"><span data-stu-id="8eafe-104">Sets the value of the specified account property.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="8eafe-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="8eafe-105">Quick info</span></span>

<span data-ttu-id="8eafe-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="8eafe-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::SetProp(  
    DWORD dwProp, 
    ACCT_VARIANT *pVar 
);
```

## <a name="parameters"></a><span data-ttu-id="8eafe-107">参数</span><span class="sxs-lookup"><span data-stu-id="8eafe-107">Parameters</span></span>

<span data-ttu-id="8eafe-108">_dwProp_</span><span class="sxs-lookup"><span data-stu-id="8eafe-108">_dwProp_</span></span>
  
> <span data-ttu-id="8eafe-109">[in]要设置的帐户属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="8eafe-109">[in] The property tag of the account property to set.</span></span>
    
<span data-ttu-id="8eafe-110">_pVar_</span><span class="sxs-lookup"><span data-stu-id="8eafe-110">_pVar_</span></span>
  
> <span data-ttu-id="8eafe-111">[in]指定属性的值。</span><span class="sxs-lookup"><span data-stu-id="8eafe-111">[in] The value of the specified property.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="8eafe-112">返回值</span><span class="sxs-lookup"><span data-stu-id="8eafe-112">Return values</span></span>

|<span data-ttu-id="8eafe-113">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="8eafe-113">**HRESULT**</span></span>|<span data-ttu-id="8eafe-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="8eafe-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8eafe-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8eafe-115">S_OK</span></span>  <br/> |<span data-ttu-id="8eafe-116">方法调用成功。</span><span class="sxs-lookup"><span data-stu-id="8eafe-116">The method call was successful.</span></span>  <br/> |
|<span data-ttu-id="8eafe-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8eafe-117">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="8eafe-118">指定了无效的属性标记。</span><span class="sxs-lookup"><span data-stu-id="8eafe-118">An invalid property tag was specified.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8eafe-119">备注</span><span class="sxs-lookup"><span data-stu-id="8eafe-119">Remarks</span></span>

<span data-ttu-id="8eafe-120">使用 [IOlkAccount：：SaveChanges](iolkaccount-savechanges.md) 保存对帐户属性值的更改。</span><span class="sxs-lookup"><span data-stu-id="8eafe-120">Use [IOlkAccount::SaveChanges](iolkaccount-savechanges.md) to save changes to the value of account properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8eafe-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8eafe-121">See also</span></span>

- [<span data-ttu-id="8eafe-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="8eafe-122">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="8eafe-123">IOlkAccount::GetProp</span><span class="sxs-lookup"><span data-stu-id="8eafe-123">IOlkAccount::GetProp</span></span>](iolkaccount-getprop.md)

