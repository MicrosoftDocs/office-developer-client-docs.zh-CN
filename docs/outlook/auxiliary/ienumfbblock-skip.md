---
title: IEnumFBBlockSkip
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70fbdb41-46ea-d016-25a2-37e94962095d
description: 跳过指定数量的忙/闲数据块。
ms.openlocfilehash: cf8ae18b5ed2c24a48d44d9e8d461da7d95054d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425720"
---
# <a name="ienumfbblockskip"></a>IEnumFBBlock::Skip

跳过指定数量的忙/闲数据块。
  
## <a name="quick-info"></a>快速信息

请参阅 [IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Skip(  
    LONG celt 
);
```

## <a name="parameters"></a>参数

_celt_
  
>  [in]要跳过的忙/闲块数。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [IEnumFBBlock::Clone](ienumfbblock-clone.md)  
- [IEnumFBBlock::Next](ienumfbblock-next.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Restrict](ienumfbblock-restrict.md)

