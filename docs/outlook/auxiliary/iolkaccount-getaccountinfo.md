---
title: IOlkAccountGetAccountInfo
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 97f08cde-d6e4-8935-1758-4018a3baf682
description: 获取指定帐户的类型和类别信息。
ms.openlocfilehash: 88021537cc7ff4c55759081e6f3619c2a9f10ea3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437901"
---
# <a name="iolkaccountgetaccountinfo"></a><span data-ttu-id="a9868-103">IOlkAccount::GetAccountInfo</span><span class="sxs-lookup"><span data-stu-id="a9868-103">IOlkAccount::GetAccountInfo</span></span>

<span data-ttu-id="a9868-104">获取指定帐户的类型和类别信息。</span><span class="sxs-lookup"><span data-stu-id="a9868-104">Gets the type and categories information for the specified account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a9868-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="a9868-105">Quick info</span></span>

<span data-ttu-id="a9868-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="a9868-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
```cpp
HRESULT IOlkAccount::GetAccountInfo(  
    CLSID *pclsidType, 
    DWORD *pcCategories, 
    CLSID **prgclsidCategory 
);

```

## <a name="parameters"></a><span data-ttu-id="a9868-107">参数</span><span class="sxs-lookup"><span data-stu-id="a9868-107">Parameters</span></span>

<span data-ttu-id="a9868-108">_pclsidType_</span><span class="sxs-lookup"><span data-stu-id="a9868-108">_pclsidType_</span></span>
  
> <span data-ttu-id="a9868-109">排除帐户类型的类标识符。</span><span class="sxs-lookup"><span data-stu-id="a9868-109">[out] The class identifier for the account type.</span></span> <span data-ttu-id="a9868-110">该值必须为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="a9868-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="a9868-111">CLSID_OlkPOP3Account</span><span class="sxs-lookup"><span data-stu-id="a9868-111">CLSID_OlkPOP3Account</span></span> 
    
   - <span data-ttu-id="a9868-112">CLSID_OlkIMAP4Account</span><span class="sxs-lookup"><span data-stu-id="a9868-112">CLSID_OlkIMAP4Account</span></span> 
    
   - <span data-ttu-id="a9868-113">CLSID_OlkMAPIAccount</span><span class="sxs-lookup"><span data-stu-id="a9868-113">CLSID_OlkMAPIAccount</span></span> 
    
   - <span data-ttu-id="a9868-114">CLSID_OlkHotmailAccount</span><span class="sxs-lookup"><span data-stu-id="a9868-114">CLSID_OlkHotmailAccount</span></span> 
    
   - <span data-ttu-id="a9868-115">CLSID_OlkLDAPAccount</span><span class="sxs-lookup"><span data-stu-id="a9868-115">CLSID_OlkLDAPAccount</span></span>
    
<span data-ttu-id="a9868-116">_pcCategories_</span><span class="sxs-lookup"><span data-stu-id="a9868-116">_pcCategories_</span></span>
  
> <span data-ttu-id="a9868-117">排除_prgclsidCategory_中的类别数。</span><span class="sxs-lookup"><span data-stu-id="a9868-117">[out] The number of categories in  _prgclsidCategory_.</span></span>
    
<span data-ttu-id="a9868-118">_prgclsidCategory_</span><span class="sxs-lookup"><span data-stu-id="a9868-118">_prgclsidCategory_</span></span>
  
> <span data-ttu-id="a9868-119">排除与此帐户关联的类别的数组。</span><span class="sxs-lookup"><span data-stu-id="a9868-119">[out] An array of categories that this account is associated with.</span></span> <span data-ttu-id="a9868-120">数组的大小为 \* _pcCategories_。</span><span class="sxs-lookup"><span data-stu-id="a9868-120">The array is of size \* _pcCategories_.</span></span> <span data-ttu-id="a9868-121">数组中每个类别的值必须是下列值之一:</span><span class="sxs-lookup"><span data-stu-id="a9868-121">The value of each category in the array must be one of the following:</span></span>
    
   - <span data-ttu-id="a9868-122">CLSID_OlkMail</span><span class="sxs-lookup"><span data-stu-id="a9868-122">CLSID_OlkMail</span></span>
    
   - <span data-ttu-id="a9868-123">CLSID_OlkAddressBook</span><span class="sxs-lookup"><span data-stu-id="a9868-123">CLSID_OlkAddressBook</span></span>
    
   - <span data-ttu-id="a9868-124">CLSID_OlkStore</span><span class="sxs-lookup"><span data-stu-id="a9868-124">CLSID_OlkStore</span></span>
    
## <a name="return-values"></a><span data-ttu-id="a9868-125">返回值</span><span class="sxs-lookup"><span data-stu-id="a9868-125">Return values</span></span>

<span data-ttu-id="a9868-126">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="a9868-126">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a9868-127">说明</span><span class="sxs-lookup"><span data-stu-id="a9868-127">Remarks</span></span>

<span data-ttu-id="a9868-128">此方法返回后, 必须使用[IOlkAccount:: FreeMemory](iolkaccount-freememory.md)释放*prgclsidCategory* 。</span><span class="sxs-lookup"><span data-stu-id="a9868-128">After this method returns, you must free  *prgclsidCategory*  by using [IOlkAccount::FreeMemory](iolkaccount-freememory.md).</span></span>
  
<span data-ttu-id="a9868-129">**IOlkAccount:: GetAccountInfo**不支持 Exchange 帐户的通讯簿类别。</span><span class="sxs-lookup"><span data-stu-id="a9868-129">**IOlkAccount::GetAccountInfo** does not support the address book category for an Exchange account.</span></span> <span data-ttu-id="a9868-130">如果帐户是 Exchange 帐户 (*pclsidType*为**CLSID_OlkMAPIAccount** ), 并且帐户实现了通讯簿, 则调用**IOlkAccount:: GetAccountInfo**不会将**CLSID_OlkAddressBook**作为中*的类别返回prgclsidCategory* 。</span><span class="sxs-lookup"><span data-stu-id="a9868-130">If the account is an Exchange account (*pclsidType*  is **CLSID_OlkMAPIAccount** ), and the account implements the address book, calling **IOlkAccount::GetAccountInfo** will not return **CLSID_OlkAddressBook** as a category in  *prgclsidCategory*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a9868-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9868-131">See also</span></span>

- [<span data-ttu-id="a9868-132">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="a9868-132">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="a9868-133">IOlkAccount::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="a9868-133">IOlkAccount::FreeMemory</span></span>](iolkaccount-freememory.md)

