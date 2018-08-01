---
title: IOlkAccountManagerEnumerateAccounts
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dbb8342b-e4e0-f89d-3e14-b4c7049095ef
description: 获取特定类别或类型的帐户。
ms.openlocfilehash: f9b332c0bbc90b1a8f5f944492448055f23c0668
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774340"
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
  
 **IOlkAccountManager::EnumerateAccounts** 不支持 Exchange 帐户的地址簿类别。 如果该帐户是 Exchange 帐户 （*pclsidType*是**CLSID_OlkMAPIAccount** ），以及您尝试枚举实现通讯簿的帐户 （*prgclsidCategory*是**CLSID_OlkAddressBook** ），调用**IOlkAccountManager::EnumerateAccounts**不会在帐户将枚举器重*ppEnum*返回 Exchange 帐户。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkEnum](iolkenum.md)

