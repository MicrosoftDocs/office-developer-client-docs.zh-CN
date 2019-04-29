---
title: IOlkAccountManagerFindAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31004aec-7bd2-6e12-83eb-1a32da121c54
description: 按属性值查找帐户。
ms.openlocfilehash: d09bce88413f85ee3ccc332c3cb88bb545a0ccaf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428800"
---
# <a name="iolkaccountmanagerfindaccount"></a><span data-ttu-id="eef1e-103">IOlkAccountManager::FindAccount</span><span class="sxs-lookup"><span data-stu-id="eef1e-103">IOlkAccountManager::FindAccount</span></span>

<span data-ttu-id="eef1e-104">按属性值查找帐户。</span><span class="sxs-lookup"><span data-stu-id="eef1e-104">Finds an account by property value.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="eef1e-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="eef1e-105">Quick info</span></span>

<span data-ttu-id="eef1e-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="eef1e-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::FindAccount (  
    DWORD dwProp, 
    ACCT_VARIANT *pVar, 
    IOlkAccount **ppAccount 
);
```

## <a name="parameters"></a><span data-ttu-id="eef1e-107">参数</span><span class="sxs-lookup"><span data-stu-id="eef1e-107">Parameters</span></span>

<span data-ttu-id="eef1e-108">_dwProp_</span><span class="sxs-lookup"><span data-stu-id="eef1e-108">_dwProp_</span></span>
  
> <span data-ttu-id="eef1e-109">实时要搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="eef1e-109">[in] The property to search on.</span></span> <span data-ttu-id="eef1e-110">必须为[PROP_ACCT_ID](prop_acct_id.md)或[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)。</span><span class="sxs-lookup"><span data-stu-id="eef1e-110">Must be [PROP_ACCT_ID](prop_acct_id.md) or [PROP_ACCT_IS_EXCH](prop_acct_is_exch.md).</span></span>
    
<span data-ttu-id="eef1e-111">_pVar_</span><span class="sxs-lookup"><span data-stu-id="eef1e-111">_pVar_</span></span>
  
> <span data-ttu-id="eef1e-112">实时要匹配的值。</span><span class="sxs-lookup"><span data-stu-id="eef1e-112">[in] The value to match.</span></span>
    
<span data-ttu-id="eef1e-113">_ppAccount_</span><span class="sxs-lookup"><span data-stu-id="eef1e-113">_ppAccount_</span></span>
  
> <span data-ttu-id="eef1e-114">排除找到的帐户。</span><span class="sxs-lookup"><span data-stu-id="eef1e-114">[out] The account found.</span></span> <span data-ttu-id="eef1e-115">此对象支持[IOlkAccount](iolkaccount.md)接口。</span><span class="sxs-lookup"><span data-stu-id="eef1e-115">This object supports an [IOlkAccount](iolkaccount.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="eef1e-116">返回值</span><span class="sxs-lookup"><span data-stu-id="eef1e-116">Return values</span></span>

|<span data-ttu-id="eef1e-117">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="eef1e-117">**HRESULT**</span></span>|<span data-ttu-id="eef1e-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="eef1e-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eef1e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="eef1e-119">S_OK</span></span>  <br/> |<span data-ttu-id="eef1e-120">调用成功。</span><span class="sxs-lookup"><span data-stu-id="eef1e-120">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="eef1e-121">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="eef1e-121">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="eef1e-122">找不到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="eef1e-122">The specified account cannot be found.</span></span>  <br/> |
|<span data-ttu-id="eef1e-123">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="eef1e-123">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="eef1e-124">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="eef1e-124">The account manager has not been initialized for use.</span></span>  <br/> |
|<span data-ttu-id="eef1e-125">E_OLK_PARAM_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="eef1e-125">E_OLK_PARAM_NOT_SUPPORTED</span></span>  <br/> |<span data-ttu-id="eef1e-126">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="eef1e-126">One or more parameters are invalid.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="eef1e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eef1e-127">See also</span></span>

- [<span data-ttu-id="eef1e-128">ACCT_VARIANT</span><span class="sxs-lookup"><span data-stu-id="eef1e-128">ACCT_VARIANT</span></span>](acct_variant.md)  
- [<span data-ttu-id="eef1e-129">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="eef1e-129">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="eef1e-130">IOlkAccountHelper</span><span class="sxs-lookup"><span data-stu-id="eef1e-130">IOlkAccountHelper</span></span>](iolkaccounthelper.md)

