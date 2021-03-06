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
# <a name="iolkaccountmanagerfindaccount"></a>IOlkAccountManager::FindAccount

按属性值查找帐户。
  
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
  
> [in]要搜索的属性。 必须是 [PROP_ACCT_ID](prop_acct_id.md) 或 [PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)。
    
_pVar_
  
> [in]要匹配的值。
    
_ppAccount_
  
> [out]找到的帐户。 此对象支持 [IOlkAccount](iolkaccount.md) 接口。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_ACCT_NOT_FOUND  <br/> |找不到指定的帐户。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
|E_OLK_PARAM_NOT_SUPPORTED  <br/> |一个或多个参数无效。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [ACCT_VARIANT](acct_variant.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountHelper](iolkaccounthelper.md)

