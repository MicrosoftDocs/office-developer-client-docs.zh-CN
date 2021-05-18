---
title: IOlkAccountManagerEnumerateAccounts
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dbb8342b-e4e0-f89d-3e14-b4c7049095ef
description: 获取特定类别或类型的帐户。
ms.openlocfilehash: d0d383dee0e76dd6310d01bd1482e307c2374856
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423046"
---
# <a name="iolkaccountmanagerenumerateaccounts"></a><span data-ttu-id="1f50a-103">IOlkAccountManager::EnumerateAccounts</span><span class="sxs-lookup"><span data-stu-id="1f50a-103">IOlkAccountManager::EnumerateAccounts</span></span>

<span data-ttu-id="1f50a-104">获取特定类别或类型的帐户。</span><span class="sxs-lookup"><span data-stu-id="1f50a-104">Gets an enumerator for the accounts of the specific category or type.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="1f50a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="1f50a-105">Quick info</span></span>

<span data-ttu-id="1f50a-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="1f50a-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::EnumerateAccounts (  
    const CLSID *pclsidCategory, 
    const CLSID *pclsidType, 
    DWORD dwFlags, 
    IOlkEnum **ppEnum 
);

```

## <a name="parameters"></a><span data-ttu-id="1f50a-107">参数</span><span class="sxs-lookup"><span data-stu-id="1f50a-107">Parameters</span></span>

<span data-ttu-id="1f50a-108">_pclsidCategory_</span><span class="sxs-lookup"><span data-stu-id="1f50a-108">_pclsidCategory_</span></span>
  
> <span data-ttu-id="1f50a-p101">[] in要枚举的类别的类标识符。该值必须为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="1f50a-p101">[in] The class identifier of the category to enumerate. The value must be one of the following:</span></span>
    
   - <span data-ttu-id="1f50a-111">CLSID_OlkMail</span><span class="sxs-lookup"><span data-stu-id="1f50a-111">CLSID_OlkMail</span></span> 
    
   -  <span data-ttu-id="1f50a-112">CLSID_OlkAddressBook</span><span class="sxs-lookup"><span data-stu-id="1f50a-112">CLSID_OlkAddressBook</span></span> 
    
   - <span data-ttu-id="1f50a-113">CLSID_OlkStore</span><span class="sxs-lookup"><span data-stu-id="1f50a-113">CLSID_OlkStore</span></span> 
    
<span data-ttu-id="1f50a-114">_pclsidType_</span><span class="sxs-lookup"><span data-stu-id="1f50a-114">_pclsidType_</span></span>
  
> <span data-ttu-id="1f50a-p102">[] in要枚举的帐户类型的类标识符。该值必须为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="1f50a-p102">[in] The class identifier of the account type to enumerate. The value must be one of the following:</span></span>
    
   - <span data-ttu-id="1f50a-117">CLSID_OlkPOP3Account</span><span class="sxs-lookup"><span data-stu-id="1f50a-117">CLSID_OlkPOP3Account</span></span>
    
   - <span data-ttu-id="1f50a-118">CLSID_OlkIMAP4Account</span><span class="sxs-lookup"><span data-stu-id="1f50a-118">CLSID_OlkIMAP4Account</span></span>
    
   - <span data-ttu-id="1f50a-119">CLSID_OlkMAPIAccount</span><span class="sxs-lookup"><span data-stu-id="1f50a-119">CLSID_OlkMAPIAccount</span></span>
    
   - <span data-ttu-id="1f50a-120">CLSID_OlkHotmailAccount</span><span class="sxs-lookup"><span data-stu-id="1f50a-120">CLSID_OlkHotmailAccount</span></span>
    
   - <span data-ttu-id="1f50a-121">CLSID_OlkLDAPAccount</span><span class="sxs-lookup"><span data-stu-id="1f50a-121">CLSID_OlkLDAPAccount</span></span>
    
<span data-ttu-id="1f50a-122">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="1f50a-122">_dwFlags_</span></span>
  
> <span data-ttu-id="1f50a-p103">[] in若要修改行为的标志。仅支持的值是 OLK_ACCOUNT_NO_FLAGS。</span><span class="sxs-lookup"><span data-stu-id="1f50a-p103">[in] Flags to modify behavior. The only supported value is OLK_ACCOUNT_NO_FLAGS.</span></span>
    
<span data-ttu-id="1f50a-125">_ppEnum_</span><span class="sxs-lookup"><span data-stu-id="1f50a-125">_ppEnum_</span></span>
  
> <span data-ttu-id="1f50a-126">[out] An enumerator that supports the [IOlkEnum](iolkenum.md) interface.</span><span class="sxs-lookup"><span data-stu-id="1f50a-126">[out] An enumerator that supports the [IOlkEnum](iolkenum.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="1f50a-127">返回值</span><span class="sxs-lookup"><span data-stu-id="1f50a-127">Return values</span></span>

|<span data-ttu-id="1f50a-128">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="1f50a-128">**HRESULT**</span></span>|<span data-ttu-id="1f50a-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="1f50a-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f50a-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f50a-130">S_OK</span></span>  <br/> |<span data-ttu-id="1f50a-131">调用成功。</span><span class="sxs-lookup"><span data-stu-id="1f50a-131">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="1f50a-132">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="1f50a-132">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="1f50a-133">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="1f50a-133">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f50a-134">备注</span><span class="sxs-lookup"><span data-stu-id="1f50a-134">Remarks</span></span>

<span data-ttu-id="1f50a-p104">为类别指定 NULL 返回指定类型的所有帐户的枚举。同样，指定 NULL 类型返回指定的类别的所有帐户的枚举。</span><span class="sxs-lookup"><span data-stu-id="1f50a-p104">Specifying NULL for category returns an enumerator of all accounts of the specified type. Similarly, specifying NULL for type returns an enumerator of all accounts of the specified category.</span></span>
  
 <span data-ttu-id="1f50a-137">**IOlkAccountManager::EnumerateAccounts** 不支持 Exchange 帐户的地址簿类别。</span><span class="sxs-lookup"><span data-stu-id="1f50a-137">**IOlkAccountManager::EnumerateAccounts** does not support the address book category for an Exchange account.</span></span> <span data-ttu-id="1f50a-138">如果该帐户是 Exchange 帐户 (*pclsidType* 为 **CLSID_OlkMAPIAccount** ) ，并且您尝试枚举实现通讯簿 (*prgclsidCategory* 的帐户为 **CLSID_OlkAddressBook** ) ，则调用 **IOlkAccountManager：：EnumerateAccounts** 将不会在帐户枚举器 *ppEnum* 中返回 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="1f50a-138">If the account is an Exchange account (*pclsidType*  is **CLSID_OlkMAPIAccount** ), and you are trying to enumerate accounts that implement the address book (*prgclsidCategory*  is **CLSID_OlkAddressBook** ), calling **IOlkAccountManager::EnumerateAccounts** will not return the Exchange account in the accounts enumerator  *ppEnum*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1f50a-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f50a-139">See also</span></span>

- [<span data-ttu-id="1f50a-140">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="1f50a-140">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="1f50a-141">IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="1f50a-141">IOlkEnum</span></span>](iolkenum.md)

