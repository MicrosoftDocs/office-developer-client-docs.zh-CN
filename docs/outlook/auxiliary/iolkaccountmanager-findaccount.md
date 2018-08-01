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
# <a name="iolkaccountmanagerfindaccount"></a>IOlkAccountManager::FindAccount

属性值来查找帐户。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::FindAccount (  
    DWORD dwProp, 
    ACCT_VARIANT *pVar, 
    IOlkAccount **ppAccount 
);
```

## <a name="parameters"></a>参数

_dwProp_
  
> [in]要搜索的属性。 必须[PROP_ACCT_ID](prop_acct_id.md)或[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)。
    
_pVar_
  
> [in]要匹配的值。
    
_ppAccount_
  
> [输出]找到该帐户。 此对象支持[IOlkAccount](iolkaccount.md)接口。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_ACCT_NOT_FOUND  <br/> |找不到指定的帐户。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
|E_OLK_PARAM_NOT_SUPPORTED  <br/> |一个或多个参数均无效。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [ACCT_VARIANT](acct_variant.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountHelper](iolkaccounthelper.md)

