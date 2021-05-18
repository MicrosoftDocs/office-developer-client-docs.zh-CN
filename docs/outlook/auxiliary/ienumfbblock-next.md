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

请参阅 [IEnumFBBlock](ienumfbblock.md)。
  
```cpp
HRESULT Next(  
        LONG celt,
        FBBlock_1 *pblk,
        LONG *pcfetch
);
```

## <a name="parameters"></a>参数

_celt_
  
> [in]pblk 中要检索的忙/闲  *数据块*  数。 
    
_pblk_
  
> [in]指向忙/闲块数组的指针。 数组分配了大小  *为 celt*  。 请求的忙/闲块将在此数组中返回。 
    
_pcfetch_
  
> [out]pblk 中实际返回的忙/闲块  *数*  。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |已返回请求的块数。  <br/> |
|S_FALSE  <br/> |请求的块数尚未返回。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 (忙/闲 API) ](constants-free-busy-api.md)  
- [FBBlock_1](fbblock_1.md)  
- [IEnumFBBlock::Clone](ienumfbblock-clone.md)  
- [IEnumFBBlock::Reset](ienumfbblock-reset.md)  
- [IEnumFBBlock::Restrict](ienumfbblock-restrict.md)  
- [IEnumFBBlock::Skip](ienumfbblock-skip.md)

