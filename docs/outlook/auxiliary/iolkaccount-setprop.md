---
title: IOlkAccountSetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 883b1c5d-47dd-a006-b5f1-130691bdd019
description: 设置指定的帐户属性的值。
ms.openlocfilehash: 2bb8a323f5f3399b9eac1cfdf9ac18faddfdb259
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774302"
---
# <a name="iolkaccountsetprop"></a><span data-ttu-id="915e7-103">IOlkAccount::SetProp</span><span class="sxs-lookup"><span data-stu-id="915e7-103">IOlkAccount::SetProp</span></span>

<span data-ttu-id="915e7-104">设置指定的帐户属性的值。</span><span class="sxs-lookup"><span data-stu-id="915e7-104">Sets the value of the specified account property.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="915e7-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="915e7-105">Quick info</span></span>

<span data-ttu-id="915e7-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="915e7-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::SetProp(  
    DWORD dwProp, 
    ACCT_VARIANT *pVar 
);
```

## <a name="parameters"></a><span data-ttu-id="915e7-107">参数</span><span class="sxs-lookup"><span data-stu-id="915e7-107">Parameters</span></span>

<span data-ttu-id="915e7-108">_dwProp_</span><span class="sxs-lookup"><span data-stu-id="915e7-108">_dwProp_</span></span>
  
> <span data-ttu-id="915e7-109">[in]要设置的帐户属性属性标记。</span><span class="sxs-lookup"><span data-stu-id="915e7-109">[in] The property tag of the account property to set.</span></span>
    
<span data-ttu-id="915e7-110">_pVar_</span><span class="sxs-lookup"><span data-stu-id="915e7-110">_pVar_</span></span>
  
> <span data-ttu-id="915e7-111">[in]指定的属性的值。</span><span class="sxs-lookup"><span data-stu-id="915e7-111">[in] The value of the specified property.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="915e7-112">返回值</span><span class="sxs-lookup"><span data-stu-id="915e7-112">Return values</span></span>

|<span data-ttu-id="915e7-113">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="915e7-113">**HRESULT**</span></span>|<span data-ttu-id="915e7-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="915e7-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="915e7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="915e7-115">S_OK</span></span>  <br/> |<span data-ttu-id="915e7-116">方法调用成功。</span><span class="sxs-lookup"><span data-stu-id="915e7-116">The method call was successful.</span></span>  <br/> |
|<span data-ttu-id="915e7-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="915e7-117">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="915e7-118">指定无效的属性标记。</span><span class="sxs-lookup"><span data-stu-id="915e7-118">An invalid property tag was specified.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="915e7-119">说明</span><span class="sxs-lookup"><span data-stu-id="915e7-119">Remarks</span></span>

<span data-ttu-id="915e7-120">使用[IOlkAccount::SaveChanges](iolkaccount-savechanges.md)将更改保存到帐户属性的值。</span><span class="sxs-lookup"><span data-stu-id="915e7-120">Use [IOlkAccount::SaveChanges](iolkaccount-savechanges.md) to save changes to the value of account properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="915e7-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="915e7-121">See also</span></span>

- [<span data-ttu-id="915e7-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="915e7-122">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="915e7-123">IOlkAccount::GetProp</span><span class="sxs-lookup"><span data-stu-id="915e7-123">IOlkAccount::GetProp</span></span>](iolkaccount-getprop.md)

