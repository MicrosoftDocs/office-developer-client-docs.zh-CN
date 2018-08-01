---
title: IOlkAccountManagerGetOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd22026c-e4f7-2f25-0ef2-5d9539fd7eee
description: 获取指定的类别的帐户的顺序。
ms.openlocfilehash: d05e354e25d49a51b3d3f8f053c2b39dc37b333f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774345"
---
# <a name="iolkaccountmanagergetorder"></a><span data-ttu-id="6b4ec-103">IOlkAccountManager::GetOrder</span><span class="sxs-lookup"><span data-stu-id="6b4ec-103">IOlkAccountManager::GetOrder</span></span>

<span data-ttu-id="6b4ec-104">获取指定的类别的帐户的顺序。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-104">Gets the ordering of the specified category of accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6b4ec-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="6b4ec-105">Quick info</span></span>

<span data-ttu-id="6b4ec-106">请参阅[IOlkAccountManager](iolkaccountmanager.md)</span><span class="sxs-lookup"><span data-stu-id="6b4ec-106">See [IOlkAccountManager](iolkaccountmanager.md)</span></span>
  
```cpp
HRESULT IOlkAccountManager::GetOrder (  
    const CLSID *pclsidCategory, 
    DWORD *pcAccts, 
    DWORD *prgAccts[] 
); 
```

## <a name="parameters"></a><span data-ttu-id="6b4ec-107">参数</span><span class="sxs-lookup"><span data-stu-id="6b4ec-107">Parameters</span></span>

<span data-ttu-id="6b4ec-108">_pclsidCategory_</span><span class="sxs-lookup"><span data-stu-id="6b4ec-108">_pclsidCategory_</span></span>
  
> <span data-ttu-id="6b4ec-109">[in]类别类 ID 为其获取顺序。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-109">[in] The category class ID for which to get the order.</span></span> <span data-ttu-id="6b4ec-110">该值必须为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="6b4ec-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="6b4ec-111">CLSID_OlkMail</span><span class="sxs-lookup"><span data-stu-id="6b4ec-111">CLSID_OlkMail</span></span>
    
   - <span data-ttu-id="6b4ec-112">CLSID_OlkAddressBook</span><span class="sxs-lookup"><span data-stu-id="6b4ec-112">CLSID_OlkAddressBook</span></span>
    
   - <span data-ttu-id="6b4ec-113">CLSID_OlkStore</span><span class="sxs-lookup"><span data-stu-id="6b4ec-113">CLSID_OlkStore</span></span>
    
<span data-ttu-id="6b4ec-114">_pcAccts_</span><span class="sxs-lookup"><span data-stu-id="6b4ec-114">_pcAccts_</span></span>
  
>  <span data-ttu-id="6b4ec-115">[输出]帐户数。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-115">[out] The number of accounts.</span></span> 
    
<span data-ttu-id="6b4ec-116">_prgAccts_</span><span class="sxs-lookup"><span data-stu-id="6b4ec-116">_prgAccts_</span></span>
  
> <span data-ttu-id="6b4ec-117">[输出]一个指向帐户的数组。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-117">[out] A pointer to an array of accounts.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="6b4ec-118">返回值</span><span class="sxs-lookup"><span data-stu-id="6b4ec-118">Return values</span></span>

|<span data-ttu-id="6b4ec-119">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="6b4ec-119">**HRESULT**</span></span>|<span data-ttu-id="6b4ec-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b4ec-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b4ec-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b4ec-121">S_OK</span></span>  <br/> |<span data-ttu-id="6b4ec-122">成功呼叫</span><span class="sxs-lookup"><span data-stu-id="6b4ec-122">The call succeeded</span></span>  <br/> |
|<span data-ttu-id="6b4ec-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6b4ec-123">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="6b4ec-124">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-124">One or more arguments are invalid.</span></span>  <br/> |
|<span data-ttu-id="6b4ec-125">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="6b4ec-125">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="6b4ec-126">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-126">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6b4ec-127">注解</span><span class="sxs-lookup"><span data-stu-id="6b4ec-127">Remarks</span></span>

<span data-ttu-id="6b4ec-128">调用此方法之前，呼叫者在哪些*prgAccts*点数组分配仅数组指针*prgAccts*但没有内存。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-128">Before calling this method, the caller allocates only an array pointer  *prgAccts*  but no memory for the array at which  *prgAccts*  points.</span></span> <span data-ttu-id="6b4ec-129">此方法返回后，呼叫者必须使用[IOlkAccountManager::FreeMemory](iolkaccountmanager-freememory.md)版本为*prgAccts*分配的内存。</span><span class="sxs-lookup"><span data-stu-id="6b4ec-129">After this method returns, the caller must use [IOlkAccountManager::FreeMemory](iolkaccountmanager-freememory.md) to release the memory allocated for  *prgAccts*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6b4ec-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b4ec-130">See also</span></span>

- [<span data-ttu-id="6b4ec-131">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="6b4ec-131">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="6b4ec-132">IOlkAccountManager::SetOrder</span><span class="sxs-lookup"><span data-stu-id="6b4ec-132">IOlkAccountManager::SetOrder</span></span>](iolkaccountmanager-setorder.md)

