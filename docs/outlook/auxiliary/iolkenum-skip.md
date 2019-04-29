---
title: IOlkEnumSkip
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e83e409c-f201-df9d-5e30-879adf15318d
description: 在枚举数中跳过指定数量的帐户。
ms.openlocfilehash: d4063b0ff4852e6932cf50789eea3caa81d4d586
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404776"
---
# <a name="iolkenumskip"></a>IOlkEnum::Skip

在枚举数中跳过指定数量的帐户。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkEnum](iolkenum.md)。
  
```cpp
HRESULT IOlkEnum::Skip(  
    DWORD cSkip 
);
```

## <a name="parameters"></a>参数

_cSkip_
  
> 实时要跳过的帐户数。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [IOlkEnum::GetCount](iolkenum-getcount.md) 
- [IOlkEnum::GetNext](iolkenum-getnext.md)  
- [IOlkEnum::Reset](iolkenum-reset.md)

