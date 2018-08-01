---
title: IEnumFBBlockClone
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5af36a87-e782-df63-4190-a608758fef50
description: 创建一份枚举数，使用相同的时间限制，但设置光标到枚举的开头。
ms.openlocfilehash: 51503be2091fa01da6f636bf6944274068617f05
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774197"
---
# <a name="ienumfbblockclone"></a>IEnumFBBlock::Clone

创建一份枚举数，使用相同的时间限制，但设置光标到枚举的开头。
  
## <a name="quick-info"></a>快速信息

请参阅[IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Clone(  
     IEnumFBBlock **ppclone 
); 
```

## <a name="parameters"></a>参数

_ppclone_
  
> [输出]A 到指针的指针到[IEnumFBBlock](ienumfbblock.md)接口的副本。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_OUTOFMEMORY  <br/> |没有进行复制的内存不足。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API)](constants-free-busy-api.md)
- [IEnumFBBlock::Next](ienumfbblock-next.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Restrict](ienumfbblock-restrict.md)  
- [IEnumFBBlock::Skip](ienumfbblock-skip.md)

