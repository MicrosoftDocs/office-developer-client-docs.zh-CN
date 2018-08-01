---
title: IOlkAccountFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3b2ee5aa-7639-d86d-447e-50bda54aa3ec
description: 释放内存分配 IOlkAccount 接口。
ms.openlocfilehash: ce3046db29cb2cac7d7ee72a3e4e9125346a4ac4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774277"
---
# <a name="iolkaccountfreememory"></a>IOlkAccount::FreeMemory

释放内存分配[IOlkAccount](iolkaccount.md)接口。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
```cpp
HRESULT IOlkAccount::FreeMemory (  
    BYTE *pv, 
); 

```

## <a name="parameters"></a>参数

_pv_
  
> [in]指向要释放内存的指针。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

使用此方法以释放内存分配[IOlkAccount::GetProp](iolkaccount-getprop.md) （如果指定的帐户属性的值为二进制或字符串类型） 和[IOlkAccount::GetAccountInfo](iolkaccount-getaccountinfo.md)。
  
## <a name="see-also"></a>另请参阅

- [IOlkAccount::GetAccountInfo](iolkaccount-getaccountinfo.md)  
- [IOlkAccount::GetProp](iolkaccount-getprop.md)

