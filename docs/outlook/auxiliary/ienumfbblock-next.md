---
title: IEnumFBBlockNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b46358c-bcab-f097-8746-fabfd4722b3c
description: 获取枚举中的下一个指定的数量的忙/闲数据块。
ms.openlocfilehash: ec366cf102d3c75487f9485cfae7764d68695f10
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774203"
---
# <a name="ienumfbblocknext"></a>IEnumFBBlock::Next

获取枚举中的下一个指定的数量的忙/闲数据块。
  
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
  
> [in]中*pblk*检索块的忙/闲数据。 
    
_pblk_
  
> [in]一个指向忙/闲块的数组。 该数组被分配*celt*的大小。 该数组中返回的请求的忙/闲基块。 
    
_pcfetch_
  
> [输出]忙/闲块中*pblk*实际返回数。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |已返回块的请求的数。  <br/> |
|S_FALSE  <br/> |不返回了块的请求的数。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API)](constants-free-busy-api.md)  
- [FBBlock_1](fbblock_1.md)  
- [IEnumFBBlock::Clone](ienumfbblock-clone.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Restrict](ienumfbblock-restrict.md)  
- [IEnumFBBlock::Skip](ienumfbblock-skip.md)

