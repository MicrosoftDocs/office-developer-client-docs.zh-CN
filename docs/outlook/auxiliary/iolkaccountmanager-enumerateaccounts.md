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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322048"
---
# <a name="iolkaccountmanagerenumerateaccounts"></a>IOlkAccountManager::EnumerateAccounts

获取特定类别或类型的帐户。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::EnumerateAccounts (  
    const CLSID *pclsidCategory, 
    const CLSID *pclsidType, 
    DWORD dwFlags, 
    IOlkEnum **ppEnum 
);

```

## <a name="parameters"></a>参数

_pclsidCategory_
  
> [] in要枚举的类别的类标识符。该值必须为以下项之一：
    
   - CLSID_OlkMail 
    
   -  CLSID_OlkAddressBook 
    
   - CLSID_OlkStore 
    
_pclsidType_
  
> [] in要枚举的帐户类型的类标识符。该值必须为以下项之一：
    
   - CLSID_OlkPOP3Account
    
   - CLSID_OlkIMAP4Account
    
   - CLSID_OlkMAPIAccount
    
   - CLSID_OlkHotmailAccount
    
   - CLSID_OlkLDAPAccount
    
_dwFlags_
  
> [] in若要修改行为的标志。仅支持的值是 OLK_ACCOUNT_NO_FLAGS。
    
_ppEnum_
  
> [out] An enumerator that supports the [IOlkEnum](iolkenum.md) interface. 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
   
## <a name="remarks"></a>注解

为类别指定 NULL 返回指定类型的所有帐户的枚举。同样，指定 NULL 类型返回指定的类别的所有帐户的枚举。
  
 **IOlkAccountManager::EnumerateAccounts** 不支持 Exchange 帐户的地址簿类别。 如果帐户是 Exchange 帐户 (*pclsidType*为**CLSID_OlkMAPIAccount** ), 并且您尝试枚举实现通讯簿的帐户 (*prgclsidCategory*为**CLSID_OlkAddressBook** ), 请调用**IOlkAccountManager:: EnumerateAccounts**将不会返回帐户枚举器*ppEnum*中的 Exchange 帐户。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkEnum](iolkenum.md)

