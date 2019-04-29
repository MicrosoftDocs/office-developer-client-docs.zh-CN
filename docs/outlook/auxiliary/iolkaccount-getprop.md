---
title: IOlkAccountGetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5725eb52-3a78-897d-f9e3-c5a494fb78c0
description: 获取指定的帐户属性的值。
ms.openlocfilehash: d24df8cfa9d54bee4614c1f31e12268748b8c986
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433736"
---
# <a name="iolkaccountgetprop"></a>IOlkAccount::GetProp

获取指定的帐户属性的值。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
```cpp
HRESULT IOlkAccount::GetProp(  
DWORD dwProp, 
ACCT_VARIANT *pVar 
);
```

## <a name="parameters"></a>参数

_dwProp_
  
> 实时要获取的帐户属性的属性标记。
    
_pVar_
  
> 排除指定属性的值。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_ACCT_NOT_FOUND  <br/> |找不到给定帐户的属性。  <br/> |
|E_INVALIDARG  <br/> |指定了无效的属性标记。  <br/> |
   
## <a name="remarks"></a>说明

此方法返回后, 如果 account 属性的值是二进制或字符串类型, 则必须使用[IOlkAccount:: FreeMemory](iolkaccount-freememory.md)释放*pVar* 。
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkAccount::FreeMemory](iolkaccount-freememory.md)  
- [IOlkAccount::SetProp](iolkaccount-setprop.md)

