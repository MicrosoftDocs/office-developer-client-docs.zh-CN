---
title: IEnumFBBlockSkip
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70fbdb41-46ea-d016-25a2-37e94962095d
description: 跳过指定的数量的忙/闲数据块。
ms.openlocfilehash: 63f699d09e143a879702e8dc76beb8a969a77b82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774196"
---
# <a name="ienumfbblockskip"></a>IEnumFBBlock::Skip

跳过指定的数量的忙/闲数据块。
  
## <a name="quick-info"></a>快速信息

请参阅[IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Skip(  
    LONG celt 
);
```

## <a name="parameters"></a>参数

_celt_
  
>  [in]忙/闲块，以跳过数。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [IEnumFBBlock::Clone](ienumfbblock-clone.md)  
- [IEnumFBBlock::Next](ienumfbblock-next.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Restrict](ienumfbblock-restrict.md)

