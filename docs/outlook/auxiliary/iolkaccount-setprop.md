---
title: IOlkAccountSetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 883b1c5d-47dd-a006-b5f1-130691bdd019
description: 设置指定的帐户属性的值。
ms.openlocfilehash: 2bb8a323f5f3399b9eac1cfdf9ac18faddfdb259
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774302"
---
# <a name="iolkaccountsetprop"></a>IOlkAccount::SetProp

设置指定的帐户属性的值。
  
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
  
> [in]要设置的帐户属性属性标记。
    
_pVar_
  
> [in]指定的属性的值。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |方法调用成功。  <br/> |
|E_INVALIDARG  <br/> |指定无效的属性标记。  <br/> |
   
## <a name="remarks"></a>说明

使用[IOlkAccount::SaveChanges](iolkaccount-savechanges.md)将更改保存到帐户属性的值。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkAccount::GetProp](iolkaccount-getprop.md)

