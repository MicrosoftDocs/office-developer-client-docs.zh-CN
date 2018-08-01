---
title: IOlkAccountManagerSetOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e219adf6-e591-72e6-b9bd-2fc62eb5142d
description: 修改的帐户指定类别排序。
ms.openlocfilehash: fcb27404471c9b551320027b0ed6979926ad3d58
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774341"
---
# <a name="iolkaccountmanagersetorder"></a><span data-ttu-id="103dd-103">IOlkAccountManager::SetOrder</span><span class="sxs-lookup"><span data-stu-id="103dd-103">IOlkAccountManager::SetOrder</span></span>

<span data-ttu-id="103dd-104">修改的帐户指定类别排序。</span><span class="sxs-lookup"><span data-stu-id="103dd-104">Modifies the ordering of the specified category of accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="103dd-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="103dd-105">Quick info</span></span>

<span data-ttu-id="103dd-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="103dd-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT SetOrder(
    const CLSID * pclsidCategory,
    DWORD cAccts,
    DWORD rgAccts[]
);

```

## <a name="parameters"></a><span data-ttu-id="103dd-107">参数</span><span class="sxs-lookup"><span data-stu-id="103dd-107">Parameters</span></span>

<span data-ttu-id="103dd-108">_pclsidCategory_</span><span class="sxs-lookup"><span data-stu-id="103dd-108">_pclsidCategory_</span></span>
  
> <span data-ttu-id="103dd-109">[in]类别类 ID 为其设置的顺序。</span><span class="sxs-lookup"><span data-stu-id="103dd-109">[in] The category class ID for which to set the order.</span></span> <span data-ttu-id="103dd-110">该值必须为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="103dd-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="103dd-111">CLSID_OlkAddressBook</span><span class="sxs-lookup"><span data-stu-id="103dd-111">CLSID_OlkAddressBook</span></span>
    
   - <span data-ttu-id="103dd-112">CLSID_OlkStore</span><span class="sxs-lookup"><span data-stu-id="103dd-112">CLSID_OlkStore</span></span>
    
<span data-ttu-id="103dd-113">_cAccts_</span><span class="sxs-lookup"><span data-stu-id="103dd-113">_cAccts_</span></span>
  
> <span data-ttu-id="103dd-114">[in]帐户数。</span><span class="sxs-lookup"><span data-stu-id="103dd-114">[in] The number of accounts.</span></span>
    
<span data-ttu-id="103dd-115">_rgAccts_</span><span class="sxs-lookup"><span data-stu-id="103dd-115">_rgAccts_</span></span>
  
> <span data-ttu-id="103dd-116">[in]帐户 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="103dd-116">[in] An array of account IDs.</span></span> <span data-ttu-id="103dd-117">数组的大小是_cAccts_。</span><span class="sxs-lookup"><span data-stu-id="103dd-117">The size of the array is  _cAccts_.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="103dd-118">返回值</span><span class="sxs-lookup"><span data-stu-id="103dd-118">Return values</span></span>

|<span data-ttu-id="103dd-119">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="103dd-119">**HRESULT**</span></span>|<span data-ttu-id="103dd-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="103dd-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="103dd-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="103dd-121">S_OK</span></span>  <br/> |<span data-ttu-id="103dd-122">调用成功。</span><span class="sxs-lookup"><span data-stu-id="103dd-122">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="103dd-123">E_ACCT_WRONG_SORT_ORDER</span><span class="sxs-lookup"><span data-stu-id="103dd-123">E_ACCT_WRONG_SORT_ORDER</span></span>  <br/> |<span data-ttu-id="103dd-124">新的排序顺序具有不同于旧的排序顺序的帐户数。</span><span class="sxs-lookup"><span data-stu-id="103dd-124">The new sort order has a different number of accounts than the old sort order.</span></span>  <br/> |
|<span data-ttu-id="103dd-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="103dd-125">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="103dd-126">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="103dd-126">One or more arguments are invalid.</span></span>  <br/> |
|<span data-ttu-id="103dd-127">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="103dd-127">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="103dd-128">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="103dd-128">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="103dd-129">注解</span><span class="sxs-lookup"><span data-stu-id="103dd-129">Remarks</span></span>

<span data-ttu-id="103dd-130">呼叫者的数组指针_prgAccts_以及哪些_prgAccts_点处的数组分配内存。</span><span class="sxs-lookup"><span data-stu-id="103dd-130">The caller allocates memory for the array pointer  _prgAccts_ as well as for the array at which  _prgAccts_ points.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="103dd-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="103dd-131">See also</span></span>

- [<span data-ttu-id="103dd-132">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="103dd-132">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="103dd-133">IOlkAccountManager::GetOrder</span><span class="sxs-lookup"><span data-stu-id="103dd-133">IOlkAccountManager::GetOrder</span></span>](iolkaccountmanager-getorder.md)

