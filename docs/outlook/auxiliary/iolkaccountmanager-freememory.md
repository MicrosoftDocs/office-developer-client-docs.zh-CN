---
title: IOlkAccountManagerFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: acb67186-ab38-e918-5402-2526307a5bd0
description: 释放内存分配 IOlkAccountManager 接口。
ms.openlocfilehash: 85ba4d0d47eb5c879fa562e3147860533ef59f23
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774333"
---
# <a name="iolkaccountmanagerfreememory"></a>IOlkAccountManager::FreeMemory

释放内存分配[IOlkAccountManager](iolkaccountmanager.md)接口。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::FreeMemory (  
    BYTE *pv, 
);
```

## <a name="parameters"></a>参数

_pv_
  
> [in]指向以释放内存的指针。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

使用此方法释放由[IOlkAccountManager::GetOrder](iolkaccountmanager-getorder.md)分配内存。
  
## <a name="see-also"></a>另请参阅

- [IOlkAccountManager::GetOrder](iolkaccountmanager-getorder.md)

