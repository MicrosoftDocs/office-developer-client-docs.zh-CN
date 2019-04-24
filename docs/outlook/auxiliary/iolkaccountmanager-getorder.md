---
title: IOlkAccountManagerGetOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd22026c-e4f7-2f25-0ef2-5d9539fd7eee
description: 获取指定的帐户类别的排序。
ms.openlocfilehash: 3eb6dd96caa43f81eba86a389c938ef90c9533b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322027"
---
# <a name="iolkaccountmanagergetorder"></a><span data-ttu-id="eefc3-103">IOlkAccountManager::GetOrder</span><span class="sxs-lookup"><span data-stu-id="eefc3-103">IOlkAccountManager::GetOrder</span></span>

<span data-ttu-id="eefc3-104">获取指定的帐户类别的排序。</span><span class="sxs-lookup"><span data-stu-id="eefc3-104">Gets the ordering of the specified category of accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="eefc3-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="eefc3-105">Quick info</span></span>

<span data-ttu-id="eefc3-106">请参阅[IOlkAccountManager](iolkaccountmanager.md)</span><span class="sxs-lookup"><span data-stu-id="eefc3-106">See [IOlkAccountManager](iolkaccountmanager.md)</span></span>
  
```cpp
HRESULT IOlkAccountManager::GetOrder (  
    const CLSID *pclsidCategory, 
    DWORD *pcAccts, 
    DWORD *prgAccts[] 
); 
```

## <a name="parameters"></a><span data-ttu-id="eefc3-107">参数</span><span class="sxs-lookup"><span data-stu-id="eefc3-107">Parameters</span></span>

<span data-ttu-id="eefc3-108">_pclsidCategory_</span><span class="sxs-lookup"><span data-stu-id="eefc3-108">_pclsidCategory_</span></span>
  
> <span data-ttu-id="eefc3-109">实时要为其获取订单的类别类 ID。</span><span class="sxs-lookup"><span data-stu-id="eefc3-109">[in] The category class ID for which to get the order.</span></span> <span data-ttu-id="eefc3-110">该值必须为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="eefc3-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="eefc3-111">CLSID_OlkMail</span><span class="sxs-lookup"><span data-stu-id="eefc3-111">CLSID_OlkMail</span></span>
    
   - <span data-ttu-id="eefc3-112">CLSID_OlkAddressBook</span><span class="sxs-lookup"><span data-stu-id="eefc3-112">CLSID_OlkAddressBook</span></span>
    
   - <span data-ttu-id="eefc3-113">CLSID_OlkStore</span><span class="sxs-lookup"><span data-stu-id="eefc3-113">CLSID_OlkStore</span></span>
    
<span data-ttu-id="eefc3-114">_pcAccts_</span><span class="sxs-lookup"><span data-stu-id="eefc3-114">_pcAccts_</span></span>
  
>  <span data-ttu-id="eefc3-115">排除帐户数。</span><span class="sxs-lookup"><span data-stu-id="eefc3-115">[out] The number of accounts.</span></span> 
    
<span data-ttu-id="eefc3-116">_prgAccts_</span><span class="sxs-lookup"><span data-stu-id="eefc3-116">_prgAccts_</span></span>
  
> <span data-ttu-id="eefc3-117">排除指向帐户数组的指针。</span><span class="sxs-lookup"><span data-stu-id="eefc3-117">[out] A pointer to an array of accounts.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="eefc3-118">返回值</span><span class="sxs-lookup"><span data-stu-id="eefc3-118">Return values</span></span>

|<span data-ttu-id="eefc3-119">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="eefc3-119">**HRESULT**</span></span>|<span data-ttu-id="eefc3-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="eefc3-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eefc3-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="eefc3-121">S_OK</span></span>  <br/> |<span data-ttu-id="eefc3-122">呼叫成功</span><span class="sxs-lookup"><span data-stu-id="eefc3-122">The call succeeded</span></span>  <br/> |
|<span data-ttu-id="eefc3-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="eefc3-123">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="eefc3-124">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="eefc3-124">One or more arguments are invalid.</span></span>  <br/> |
|<span data-ttu-id="eefc3-125">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="eefc3-125">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="eefc3-126">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="eefc3-126">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eefc3-127">注解</span><span class="sxs-lookup"><span data-stu-id="eefc3-127">Remarks</span></span>

<span data-ttu-id="eefc3-128">调用此方法之前, 调用方仅分配一个数组指针*prgAccts* , 但在该数组处没有*prgAccts*点的内存。</span><span class="sxs-lookup"><span data-stu-id="eefc3-128">Before calling this method, the caller allocates only an array pointer  *prgAccts*  but no memory for the array at which  *prgAccts*  points.</span></span> <span data-ttu-id="eefc3-129">此方法返回后, 调用方必须使用[IOlkAccountManager:: FreeMemory](iolkaccountmanager-freememory.md)来释放为*prgAccts*分配的内存。</span><span class="sxs-lookup"><span data-stu-id="eefc3-129">After this method returns, the caller must use [IOlkAccountManager::FreeMemory](iolkaccountmanager-freememory.md) to release the memory allocated for  *prgAccts*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="eefc3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eefc3-130">See also</span></span>

- [<span data-ttu-id="eefc3-131">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="eefc3-131">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="eefc3-132">IOlkAccountManager::SetOrder</span><span class="sxs-lookup"><span data-stu-id="eefc3-132">IOlkAccountManager::SetOrder</span></span>](iolkaccountmanager-setorder.md)

