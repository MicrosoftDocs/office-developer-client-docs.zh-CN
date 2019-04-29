---
title: IOlkAccountManagerFreeMemory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: acb67186-ab38-e918-5402-2526307a5bd0
description: 释放由 IOlkAccountManager 接口分配的内存。
ms.openlocfilehash: 3e680e1e26d6c9b12c2dd4a7d48df4dbeae14154
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408486"
---
# <a name="iolkaccountmanagerfreememory"></a>IOlkAccountManager::FreeMemory

释放由[IOlkAccountManager](iolkaccountmanager.md)接口分配的内存。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::FreeMemory (  
    BYTE *pv, 
);
```

## <a name="parameters"></a>参数

_pv_
  
> 实时指向要释放的内存的指针。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>说明

使用此方法可释放由[IOlkAccountManager:: GetOrder](iolkaccountmanager-getorder.md)分配的内存。
  
## <a name="see-also"></a>另请参阅

- [IOlkAccountManager::GetOrder](iolkaccountmanager-getorder.md)

