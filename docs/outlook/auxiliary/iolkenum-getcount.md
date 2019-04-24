---
title: IOlkEnumGetCount
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dd7a7e62-4cf2-bdd3-8a00-4fff5ac575d3
description: 获取枚举数中的帐户数。
ms.openlocfilehash: 8571d5ff01501d980c8b6543607a658ad99085ca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322013"
---
# <a name="iolkenumgetcount"></a>IOlkEnum::GetCount

获取枚举数中的帐户数。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkEnum](iolkenum.md)。
  
```cpp
HRESULT IOlkEnum::GetCount ( 
    DWORD *pulCount 
);

```

## <a name="parameters"></a>参数

_pulCount_
  
> 排除一个指针, 指向要枚举的对象的数目。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [IOlkEnum::GetNext](iolkenum-getnext.md)  
- [IOlkEnum::Reset](iolkenum-reset.md) 
- [IOlkEnum::Skip](iolkenum-skip.md)

