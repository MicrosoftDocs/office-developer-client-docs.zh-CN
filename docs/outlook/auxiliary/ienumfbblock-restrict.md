---
title: IEnumFBBlockRestrict
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 887cea55-8f1c-45ec-3100-d03e1213d7c9
description: 限制到指定的时间段枚举。
ms.openlocfilehash: 6b07fe52a84d6a808ab7400ff3e8982b1cce51ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774194"
---
# <a name="ienumfbblockrestrict"></a>IEnumFBBlock::Restrict

限制到指定的时间段枚举。
  
## <a name="quick-info"></a>快速信息

请参阅[IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Restrict(  
    FILETIME ftmStart, 
    FILETIME ftmEnd 
);

```

## <a name="parameters"></a>参数

_ftmStart_
  
>  [in]若要限制枚举的开始时间。 
    
_ftmEnd_
  
> [in]若要限制枚举的结束时间。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注释

此方法还重置枚举。
  
## <a name="see-also"></a>另请参阅

- [IEnumFBBlock::Clone](ienumfbblock-clone.md)  
- [IEnumFBBlock::Next](ienumfbblock-next.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Skip](ienumfbblock-skip.md)  
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

