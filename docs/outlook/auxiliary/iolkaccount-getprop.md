---
title: IOlkAccountGetProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5725eb52-3a78-897d-f9e3-c5a494fb78c0
description: 获取指定的帐户属性的值。
ms.openlocfilehash: 2c0756f416a209d37eff2209a82c298837f85f3d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774285"
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
  
> [in]要获取的帐户属性属性标记。
    
_pVar_
  
> [输出]指定的属性的值。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_ACCT_NOT_FOUND  <br/> |为给定的帐户未找到属性。  <br/> |
|E_INVALIDARG  <br/> |指定了无效的属性标记。  <br/> |
   
## <a name="remarks"></a>说明

此方法返回，如果帐户属性的值为二进制或字符串类型后，您必须使用[IOlkAccount::FreeMemory](iolkaccount-freememory.md)释放*pVar* 。
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkAccount::FreeMemory](iolkaccount-freememory.md)  
- [IOlkAccount::SetProp](iolkaccount-setprop.md)

