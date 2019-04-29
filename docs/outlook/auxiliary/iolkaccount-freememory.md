---
title: IOlkAccountFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3b2ee5aa-7639-d86d-447e-50bda54aa3ec
description: 释放由 IOlkAccount 接口分配的内存。
ms.openlocfilehash: a7f763ba4fc260a517f8b7df4d3791f4a8fd23b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406197"
---
# <a name="iolkaccountfreememory"></a>IOlkAccount::FreeMemory

释放由[IOlkAccount](iolkaccount.md)接口分配的内存。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
```cpp
HRESULT IOlkAccount::FreeMemory (  
    BYTE *pv, 
); 

```

## <a name="parameters"></a>参数

_pv_
  
> 实时指向要释放的内存的指针。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>说明

使用此方法释放由[IOlkAccount:: GetProp](iolkaccount-getprop.md) (如果指定的帐户属性的值是二进制或字符串类型) 和[IOlkAccount:: GetAccountInfo](iolkaccount-getaccountinfo.md)分配的内存。
  
## <a name="see-also"></a>另请参阅

- [IOlkAccount::GetAccountInfo](iolkaccount-getaccountinfo.md)  
- [IOlkAccount::GetProp](iolkaccount-getprop.md)

