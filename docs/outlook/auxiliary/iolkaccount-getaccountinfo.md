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
# <a name="iolkaccountgetaccountinfo"></a>IOlkAccount::GetAccountInfo

获取指定帐户的类型和类别信息。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
```cpp
HRESULT IOlkAccount::GetAccountInfo(  
    CLSID *pclsidType, 
    DWORD *pcCategories, 
    CLSID **prgclsidCategory 
);

```

## <a name="parameters"></a>参数

_pclsidType_
  
> 排除帐户类型的类标识符。 该值必须为以下项之一：
    
   - CLSID_OlkPOP3Account 
    
   - CLSID_OlkIMAP4Account 
    
   - CLSID_OlkMAPIAccount 
    
   - CLSID_OlkHotmailAccount 
    
   - CLSID_OlkLDAPAccount
    
_pcCategories_
  
> 排除_prgclsidCategory_中的类别数。
    
_prgclsidCategory_
  
> 排除与此帐户关联的类别的数组。 数组的大小为 * _pcCategories_。 数组中每个类别的值必须是下列值之一:
    
   - CLSID_OlkMail
    
   - CLSID_OlkAddressBook
    
   - CLSID_OlkStore
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>说明

此方法返回后, 必须使用[IOlkAccount:: FreeMemory](iolkaccount-freememory.md)释放*prgclsidCategory* 。
  
**IOlkAccount:: GetAccountInfo**不支持 Exchange 帐户的通讯簿类别。 如果帐户是 Exchange 帐户 (*pclsidType*为**CLSID_OlkMAPIAccount** ), 并且帐户实现了通讯簿, 则调用**IOlkAccount:: GetAccountInfo**不会将**CLSID_OlkAddressBook**作为中*的类别返回prgclsidCategory* 。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccount::FreeMemory](iolkaccount-freememory.md)

