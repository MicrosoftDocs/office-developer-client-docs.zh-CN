---
title: IOlkAccountGetAccountInfo
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 97f08cde-d6e4-8935-1758-4018a3baf682
description: 获取指定的帐户的类型和类别信息。
ms.openlocfilehash: 85f27d1d5f47a372090b208821b52656a56559ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774268"
---
# <a name="iolkaccountgetaccountinfo"></a>IOlkAccount::GetAccountInfo

获取指定的帐户的类型和类别信息。
  
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
  
> [输出]帐户类型的类标识符。 该值必须为以下项之一：
    
   - CLSID_OlkPOP3Account 
    
   - CLSID_OlkIMAP4Account 
    
   - CLSID_OlkMAPIAccount 
    
   - CLSID_OlkHotmailAccount 
    
   - CLSID_OlkLDAPAccount
    
_pcCategories_
  
> [输出]中_prgclsidCategory_类别数目。
    
_prgclsidCategory_
  
> [输出]此帐户相关联的类别的数组。 数组的大小是 * _pcCategories_。 该数组中每个类别的值必须是下列选项之一：
    
   - CLSID_OlkMail
    
   - CLSID_OlkAddressBook
    
   - CLSID_OlkStore
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

此方法返回后，您必须使用[IOlkAccount::FreeMemory](iolkaccount-freememory.md)释放*prgclsidCategory* 。
  
**IOlkAccount::GetAccountInfo**不支持 Exchange 帐户的地址簿类别。 如果该帐户是 Exchange 帐户 （*pclsidType*是**CLSID_OlkMAPIAccount** ） 和帐户实现通讯簿、 调用**IOlkAccount::GetAccountInfo**不会返回**CLSID_OlkAddressBook**作为*中的类别prgclsidCategory* 。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccount::FreeMemory](iolkaccount-freememory.md)

