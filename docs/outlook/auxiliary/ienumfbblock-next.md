---
title: IEnumFBBlockNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b46358c-bcab-f097-8746-fabfd4722b3c
description: 获取枚举中的下一个指定数量的忙/闲数据块。
ms.openlocfilehash: f6ec49a9bac6bcf4fff67991d55c7656f6c8cce2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422136"
---
# <a name="ienumfbblocknext"></a>IEnumFBBlock::Next

获取枚举中的下一个指定数量的忙/闲数据块。
  
## <a name="quick-info"></a>快速信息

请参阅[IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Next(  
        LONG celt,
        FBBlock_1 *pblk,
        LONG *pcfetch
);
```

## <a name="parameters"></a>参数

_celt_
  
> 实时*pblk*中要检索的忙/闲数据块的数量。 
    
_pblk_
  
> 实时指向一组空闲/忙碌块的指针。 数组分配的大小为*celt* 。 在此数组中返回请求的忙/闲块。 
    
_pcfetch_
  
> 排除*pblk*中实际返回的忙/闲块的数量。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |已返回请求的块数。  <br/> |
|S_FALSE  <br/> |尚未返回请求数量的块数。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API)](constants-free-busy-api.md)  
- [FBBlock_1](fbblock_1.md)  
- [IEnumFBBlock::Clone](ienumfbblock-clone.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Restrict](ienumfbblock-restrict.md)  
- [IEnumFBBlock::Skip](ienumfbblock-skip.md)

