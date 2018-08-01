---
title: IOlkAccountSaveChanges
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8f1ab61e-7d1c-50d5-ae21-8cb4b08d729c
description: 将更改提交给 account 对象，通过写入注册表存储。
ms.openlocfilehash: ebff8af8af8a7512b577b36a2c31f76f3297a19d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774283"
---
# <a name="iolkaccountsavechanges"></a><span data-ttu-id="4ca2e-103">IOlkAccount::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="4ca2e-103">IOlkAccount::SaveChanges</span></span>

<span data-ttu-id="4ca2e-104">将更改提交给 account 对象，通过写入注册表存储。</span><span class="sxs-lookup"><span data-stu-id="4ca2e-104">Commits changes to the account object by writing to the registry store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="4ca2e-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="4ca2e-105">Quick info</span></span>

<span data-ttu-id="4ca2e-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="4ca2e-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::SaveChanges (  
    DWORD dwFlags 
); 
```

## <a name="parameters"></a><span data-ttu-id="4ca2e-107">参数</span><span class="sxs-lookup"><span data-stu-id="4ca2e-107">Parameters</span></span>

<span data-ttu-id="4ca2e-108">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="4ca2e-108">_dwFlags_</span></span>
  
> <span data-ttu-id="4ca2e-109">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="4ca2e-109">[in] Flags to modify behavior.</span></span> <span data-ttu-id="4ca2e-110">OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。</span><span class="sxs-lookup"><span data-stu-id="4ca2e-110">OLK_ACCOUNT_NO_FLAGS is the only supported value.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="4ca2e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4ca2e-111">Return values</span></span>

|<span data-ttu-id="4ca2e-112">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="4ca2e-112">**HRESULT**</span></span>|<span data-ttu-id="4ca2e-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ca2e-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ca2e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ca2e-114">S_OK</span></span>  <br/> |<span data-ttu-id="4ca2e-115">此方法已成功。</span><span class="sxs-lookup"><span data-stu-id="4ca2e-115">The method was successful.</span></span>  <br/> |
|<span data-ttu-id="4ca2e-116">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4ca2e-116">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="4ca2e-117">找不到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="4ca2e-117">Cannot find the specified account.</span></span>  <br/> |
|<span data-ttu-id="4ca2e-118">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="4ca2e-118">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="4ca2e-119">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="4ca2e-119">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4ca2e-120">注解</span><span class="sxs-lookup"><span data-stu-id="4ca2e-120">Remarks</span></span>

<span data-ttu-id="4ca2e-121">使用[IOlkAccount::SetProp](iolkaccount-setprop.md)更改帐户属性的值后, 使用**IOlkAccount::SaveChanges**保存此更改。</span><span class="sxs-lookup"><span data-stu-id="4ca2e-121">After changing the value of account properties by using [IOlkAccount::SetProp](iolkaccount-setprop.md), use **IOlkAccount::SaveChanges** to save such changes.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4ca2e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ca2e-122">See also</span></span>

- [<span data-ttu-id="4ca2e-123">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="4ca2e-123">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="4ca2e-124">IOlkAccountManager::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="4ca2e-124">IOlkAccountManager::SaveChanges</span></span>](iolkaccountmanager-savechanges.md)

