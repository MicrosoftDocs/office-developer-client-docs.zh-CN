---
title: IOlkAccountSetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 883b1c5d-47dd-a006-b5f1-130691bdd019
description: 设置指定帐户属性的值。
ms.openlocfilehash: 94134cee7886177ab840a6caff7d70d65bf9d4cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431986"
---
# <a name="iolkaccountsetprop"></a>IOlkAccount::SetProp

设置指定帐户属性的值。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
```cpp
HRESULT IOlkAccount::SetProp(  
    DWORD dwProp, 
    ACCT_VARIANT *pVar 
);
```

## <a name="parameters"></a>参数

_dwProp_
  
> [in]要设置的帐户属性的属性标记。
    
_pVar_
  
> [in]指定属性的值。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |方法调用成功。  <br/> |
|E_INVALIDARG  <br/> |指定了无效的属性标记。  <br/> |
   
## <a name="remarks"></a>备注

使用 [IOlkAccount：：SaveChanges](iolkaccount-savechanges.md) 保存对帐户属性值的更改。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkAccount::GetProp](iolkaccount-getprop.md)

