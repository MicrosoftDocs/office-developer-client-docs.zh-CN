---
title: IEnumFBBlockClone
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5af36a87-e782-df63-4190-a608758fef50
description: 使用相同的时间限制创建枚举器的副本，但将光标设置为枚举器开头。
ms.openlocfilehash: 1a279430bf6a29611fa223bebbf8023c34967139
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413400"
---
# <a name="ienumfbblockclone"></a>IEnumFBBlock::Clone

使用相同的时间限制创建枚举器的副本，但将光标设置为枚举器开头。
  
## <a name="quick-info"></a>快速信息

请参阅 [IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Clone(  
     IEnumFBBlock **ppclone 
); 
```

## <a name="parameters"></a>参数

_ppclone_
  
> [out]指向指向 [IEnumFBBlock 接口副本的指针](ienumfbblock.md) 的指针。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_OUTOFMEMORY  <br/> |内存不足，无法进行复制。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API) ](constants-free-busy-api.md)
- [IEnumFBBlock::Next](ienumfbblock-next.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Restrict](ienumfbblock-restrict.md)  
- [IEnumFBBlock::Skip](ienumfbblock-skip.md)

