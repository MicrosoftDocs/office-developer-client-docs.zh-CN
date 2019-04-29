---
title: IOlkAccountSaveChanges
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8f1ab61e-7d1c-50d5-ae21-8cb4b08d729c
description: 通过写入注册表存储提交对 account 对象所做的更改。
ms.openlocfilehash: c23cefbbda62de9b7e159e500d95b8db5ff34ef4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425832"
---
# <a name="iolkaccountsavechanges"></a><span data-ttu-id="5fa7d-103">IOlkAccount::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="5fa7d-103">IOlkAccount::SaveChanges</span></span>

<span data-ttu-id="5fa7d-104">通过写入注册表存储提交对 account 对象所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5fa7d-104">Commits changes to the account object by writing to the registry store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5fa7d-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5fa7d-105">Quick info</span></span>

<span data-ttu-id="5fa7d-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="5fa7d-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::SaveChanges (  
    DWORD dwFlags 
); 
```

## <a name="parameters"></a><span data-ttu-id="5fa7d-107">参数</span><span class="sxs-lookup"><span data-stu-id="5fa7d-107">Parameters</span></span>

<span data-ttu-id="5fa7d-108">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="5fa7d-108">_dwFlags_</span></span>
  
> <span data-ttu-id="5fa7d-109">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="5fa7d-109">[in] Flags to modify behavior.</span></span> <span data-ttu-id="5fa7d-110">OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。</span><span class="sxs-lookup"><span data-stu-id="5fa7d-110">OLK_ACCOUNT_NO_FLAGS is the only supported value.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="5fa7d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5fa7d-111">Return values</span></span>

|<span data-ttu-id="5fa7d-112">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="5fa7d-112">**HRESULT**</span></span>|<span data-ttu-id="5fa7d-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="5fa7d-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5fa7d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5fa7d-114">S_OK</span></span>  <br/> |<span data-ttu-id="5fa7d-115">方法已成功。</span><span class="sxs-lookup"><span data-stu-id="5fa7d-115">The method was successful.</span></span>  <br/> |
|<span data-ttu-id="5fa7d-116">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5fa7d-116">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="5fa7d-117">找不到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="5fa7d-117">Cannot find the specified account.</span></span>  <br/> |
|<span data-ttu-id="5fa7d-118">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="5fa7d-118">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="5fa7d-119">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="5fa7d-119">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5fa7d-120">说明</span><span class="sxs-lookup"><span data-stu-id="5fa7d-120">Remarks</span></span>

<span data-ttu-id="5fa7d-121">使用[IOlkAccount:: SetProp](iolkaccount-setprop.md)更改 account 属性的值后, 请使用**IOlkAccount:: SaveChanges**保存此类更改。</span><span class="sxs-lookup"><span data-stu-id="5fa7d-121">After changing the value of account properties by using [IOlkAccount::SetProp](iolkaccount-setprop.md), use **IOlkAccount::SaveChanges** to save such changes.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5fa7d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa7d-122">See also</span></span>

- [<span data-ttu-id="5fa7d-123">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="5fa7d-123">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="5fa7d-124">IOlkAccountManager::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="5fa7d-124">IOlkAccountManager::SaveChanges</span></span>](iolkaccountmanager-savechanges.md)

