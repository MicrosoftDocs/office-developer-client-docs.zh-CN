---
title: IOlkAccountManagerSaveChanges
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 32a5d4b7-ead7-24e7-58f2-750232263a0d
description: 将更改保存到指定的帐户。
ms.openlocfilehash: 87b513659b632e88697fb63d1aeccccb77ed9fd1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774353"
---
# <a name="iolkaccountmanagersavechanges"></a><span data-ttu-id="b387f-103">IOlkAccountManager::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="b387f-103">IOlkAccountManager::SaveChanges</span></span>

<span data-ttu-id="b387f-104">将更改保存到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="b387f-104">Saves changes to the specified account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b387f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="b387f-105">Quick info</span></span>

<span data-ttu-id="b387f-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="b387f-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::SaveChanges (  
    DWORD dwAcctID, 
    DWORD dwFlags 
); 
```

## <a name="parameters"></a><span data-ttu-id="b387f-107">参数</span><span class="sxs-lookup"><span data-stu-id="b387f-107">Parameters</span></span>

<span data-ttu-id="b387f-108">_dwAcctID_</span><span class="sxs-lookup"><span data-stu-id="b387f-108">_dwAcctID_</span></span>
  
> <span data-ttu-id="b387f-109">[in]要保存的帐户 ID。</span><span class="sxs-lookup"><span data-stu-id="b387f-109">[in] The account ID to save.</span></span> 
    
<span data-ttu-id="b387f-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="b387f-110">_dwFlags_</span></span>
  
> <span data-ttu-id="b387f-111">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="b387f-111">[in] Flags to modify behavior.</span></span> <span data-ttu-id="b387f-112">OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。</span><span class="sxs-lookup"><span data-stu-id="b387f-112">OLK_ACCOUNT_NO_FLAGS is the only supported value.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="b387f-113">返回值</span><span class="sxs-lookup"><span data-stu-id="b387f-113">Return values</span></span>

|<span data-ttu-id="b387f-114">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="b387f-114">**HRESULT**</span></span>|<span data-ttu-id="b387f-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b387f-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b387f-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b387f-116">S_OK</span></span>  <br/> |<span data-ttu-id="b387f-117">成功呼叫</span><span class="sxs-lookup"><span data-stu-id="b387f-117">The call succeeded</span></span>  <br/> |
|<span data-ttu-id="b387f-118">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="b387f-118">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="b387f-119">找不到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="b387f-119">The specified account cannot be found.</span></span>  <br/> |
|<span data-ttu-id="b387f-120">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b387f-120">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="b387f-121">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="b387f-121">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b387f-122">注解</span><span class="sxs-lookup"><span data-stu-id="b387f-122">Remarks</span></span>

<span data-ttu-id="b387f-123">使用[IOlkAccount::SetProp](iolkaccount-setprop.md)更改帐户属性的值后, 使用**IOlkAccountManager::SaveChanges**或[IOlkAccount::SaveChanges](iolkaccount-savechanges.md)保存此更改。</span><span class="sxs-lookup"><span data-stu-id="b387f-123">After changing the value of account properties by using [IOlkAccount::SetProp](iolkaccount-setprop.md), use **IOlkAccountManager::SaveChanges** or [IOlkAccount::SaveChanges](iolkaccount-savechanges.md) to save such changes.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b387f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b387f-124">See also</span></span>

- [<span data-ttu-id="b387f-125">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="b387f-125">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="b387f-126">IOlkAccount::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="b387f-126">IOlkAccount::SaveChanges</span></span>](iolkaccount-savechanges.md)

