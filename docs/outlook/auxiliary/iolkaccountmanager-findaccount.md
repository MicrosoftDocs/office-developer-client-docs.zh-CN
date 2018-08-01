---
title: IOlkAccountManagerFindAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31004aec-7bd2-6e12-83eb-1a32da121c54
description: 属性值来查找帐户。
ms.openlocfilehash: a7d016ab7e265e547b33940c16f96979bd5fa87a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774338"
---
# <a name="iolkaccountmanagerfindaccount"></a><span data-ttu-id="9a5f4-103">IOlkAccountManager::FindAccount</span><span class="sxs-lookup"><span data-stu-id="9a5f4-103">IOlkAccountManager::FindAccount</span></span>

<span data-ttu-id="9a5f4-104">属性值来查找帐户。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-104">Finds an account by property value.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="9a5f4-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="9a5f4-105">Quick info</span></span>

<span data-ttu-id="9a5f4-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="9a5f4-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::FindAccount (  
    DWORD dwProp, 
    ACCT_VARIANT *pVar, 
    IOlkAccount **ppAccount 
);
```

## <a name="parameters"></a><span data-ttu-id="9a5f4-107">参数</span><span class="sxs-lookup"><span data-stu-id="9a5f4-107">Parameters</span></span>

<span data-ttu-id="9a5f4-108">_dwProp_</span><span class="sxs-lookup"><span data-stu-id="9a5f4-108">_dwProp_</span></span>
  
> <span data-ttu-id="9a5f4-109">[in]要搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-109">[in] The property to search on.</span></span> <span data-ttu-id="9a5f4-110">必须[PROP_ACCT_ID](prop_acct_id.md)或[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-110">Must be [PROP_ACCT_ID](prop_acct_id.md) or [PROP_ACCT_IS_EXCH](prop_acct_is_exch.md).</span></span>
    
<span data-ttu-id="9a5f4-111">_pVar_</span><span class="sxs-lookup"><span data-stu-id="9a5f4-111">_pVar_</span></span>
  
> <span data-ttu-id="9a5f4-112">[in]要匹配的值。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-112">[in] The value to match.</span></span>
    
<span data-ttu-id="9a5f4-113">_ppAccount_</span><span class="sxs-lookup"><span data-stu-id="9a5f4-113">_ppAccount_</span></span>
  
> <span data-ttu-id="9a5f4-114">[输出]找到该帐户。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-114">[out] The account found.</span></span> <span data-ttu-id="9a5f4-115">此对象支持[IOlkAccount](iolkaccount.md)接口。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-115">This object supports an [IOlkAccount](iolkaccount.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="9a5f4-116">返回值</span><span class="sxs-lookup"><span data-stu-id="9a5f4-116">Return values</span></span>

|<span data-ttu-id="9a5f4-117">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-117">**HRESULT**</span></span>|<span data-ttu-id="9a5f4-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a5f4-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a5f4-119">S_OK</span></span>  <br/> |<span data-ttu-id="9a5f4-120">调用成功。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-120">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="9a5f4-121">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="9a5f4-121">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="9a5f4-122">找不到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-122">The specified account cannot be found.</span></span>  <br/> |
|<span data-ttu-id="9a5f4-123">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="9a5f4-123">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="9a5f4-124">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-124">The account manager has not been initialized for use.</span></span>  <br/> |
|<span data-ttu-id="9a5f4-125">E_OLK_PARAM_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="9a5f4-125">E_OLK_PARAM_NOT_SUPPORTED</span></span>  <br/> |<span data-ttu-id="9a5f4-126">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="9a5f4-126">One or more parameters are invalid.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9a5f4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a5f4-127">See also</span></span>

- [<span data-ttu-id="9a5f4-128">ACCT_VARIANT</span><span class="sxs-lookup"><span data-stu-id="9a5f4-128">ACCT_VARIANT</span></span>](acct_variant.md)  
- [<span data-ttu-id="9a5f4-129">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="9a5f4-129">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="9a5f4-130">IOlkAccountHelper</span><span class="sxs-lookup"><span data-stu-id="9a5f4-130">IOlkAccountHelper</span></span>](iolkaccounthelper.md)

