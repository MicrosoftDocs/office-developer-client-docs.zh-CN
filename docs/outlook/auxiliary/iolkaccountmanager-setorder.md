---
title: IOlkAccountManagerSetOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e219adf6-e591-72e6-b9bd-2fc62eb5142d
description: 修改指定帐户类别的顺序。
ms.openlocfilehash: 29dfe4fd1bda9e323481297167361650c3b3a173
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322041"
---
# <a name="iolkaccountmanagersetorder"></a><span data-ttu-id="81307-103">IOlkAccountManager::SetOrder</span><span class="sxs-lookup"><span data-stu-id="81307-103">IOlkAccountManager::SetOrder</span></span>

<span data-ttu-id="81307-104">修改指定帐户类别的顺序。</span><span class="sxs-lookup"><span data-stu-id="81307-104">Modifies the ordering of the specified category of accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="81307-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="81307-105">Quick info</span></span>

<span data-ttu-id="81307-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="81307-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT SetOrder(
    const CLSID * pclsidCategory,
    DWORD cAccts,
    DWORD rgAccts[]
);

```

## <a name="parameters"></a><span data-ttu-id="81307-107">参数</span><span class="sxs-lookup"><span data-stu-id="81307-107">Parameters</span></span>

<span data-ttu-id="81307-108">_pclsidCategory_</span><span class="sxs-lookup"><span data-stu-id="81307-108">_pclsidCategory_</span></span>
  
> <span data-ttu-id="81307-109">实时要为其设置顺序的类别类 ID。</span><span class="sxs-lookup"><span data-stu-id="81307-109">[in] The category class ID for which to set the order.</span></span> <span data-ttu-id="81307-110">值必须为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="81307-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="81307-111">CLSID_OlkAddressBook</span><span class="sxs-lookup"><span data-stu-id="81307-111">CLSID_OlkAddressBook</span></span>
    
   - <span data-ttu-id="81307-112">CLSID_OlkStore</span><span class="sxs-lookup"><span data-stu-id="81307-112">CLSID_OlkStore</span></span>
    
<span data-ttu-id="81307-113">_cAccts_</span><span class="sxs-lookup"><span data-stu-id="81307-113">_cAccts_</span></span>
  
> <span data-ttu-id="81307-114">实时帐户数。</span><span class="sxs-lookup"><span data-stu-id="81307-114">[in] The number of accounts.</span></span>
    
<span data-ttu-id="81307-115">_rgAccts_</span><span class="sxs-lookup"><span data-stu-id="81307-115">_rgAccts_</span></span>
  
> <span data-ttu-id="81307-116">实时帐户 id 的数组。</span><span class="sxs-lookup"><span data-stu-id="81307-116">[in] An array of account IDs.</span></span> <span data-ttu-id="81307-117">数组的大小为_cAccts_。</span><span class="sxs-lookup"><span data-stu-id="81307-117">The size of the array is  _cAccts_.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="81307-118">返回值</span><span class="sxs-lookup"><span data-stu-id="81307-118">Return values</span></span>

|<span data-ttu-id="81307-119">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="81307-119">**HRESULT**</span></span>|<span data-ttu-id="81307-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="81307-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="81307-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="81307-121">S_OK</span></span>  <br/> |<span data-ttu-id="81307-122">调用成功。</span><span class="sxs-lookup"><span data-stu-id="81307-122">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="81307-123">E_ACCT_WRONG_SORT_ORDER</span><span class="sxs-lookup"><span data-stu-id="81307-123">E_ACCT_WRONG_SORT_ORDER</span></span>  <br/> |<span data-ttu-id="81307-124">新的排序顺序与旧的排序顺序具有不同的帐户数。</span><span class="sxs-lookup"><span data-stu-id="81307-124">The new sort order has a different number of accounts than the old sort order.</span></span>  <br/> |
|<span data-ttu-id="81307-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="81307-125">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="81307-126">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="81307-126">One or more arguments are invalid.</span></span>  <br/> |
|<span data-ttu-id="81307-127">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="81307-127">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="81307-128">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="81307-128">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="81307-129">注解</span><span class="sxs-lookup"><span data-stu-id="81307-129">Remarks</span></span>

<span data-ttu-id="81307-130">调用方为数组指针_prgAccts_分配内存, 并为_prgAccts_点分配数组。</span><span class="sxs-lookup"><span data-stu-id="81307-130">The caller allocates memory for the array pointer  _prgAccts_ as well as for the array at which  _prgAccts_ points.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="81307-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81307-131">See also</span></span>

- [<span data-ttu-id="81307-132">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="81307-132">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="81307-133">IOlkAccountManager::GetOrder</span><span class="sxs-lookup"><span data-stu-id="81307-133">IOlkAccountManager::GetOrder</span></span>](iolkaccountmanager-getorder.md)

