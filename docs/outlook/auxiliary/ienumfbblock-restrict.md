---
title: IEnumFBBlockRestrict
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 887cea55-8f1c-45ec-3100-d03e1213d7c9
description: 将枚举限制为指定的时间段。
ms.openlocfilehash: e7f7a5d846d13422f9ed79ef26f1b9b0008463f6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431944"
---
# <a name="ienumfbblockrestrict"></a>IEnumFBBlock::Restrict

将枚举限制为指定的时间段。
  
## <a name="quick-info"></a>快速信息

请参阅 [IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Restrict(  
    FILETIME ftmStart, 
    FILETIME ftmEnd 
);

```

## <a name="parameters"></a>参数

_ftmStart_
  
>  [in]限制枚举的开始时间。 
    
_ftmEnd_
  
> [in]限制枚举的结束时间。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>备注

此方法还重置枚举。
  
## <a name="see-also"></a>另请参阅

- [IEnumFBBlock::Clone](ienumfbblock-clone.md)  
- [IEnumFBBlock::Next](ienumfbblock-next.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Skip](ienumfbblock-skip.md)  
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

