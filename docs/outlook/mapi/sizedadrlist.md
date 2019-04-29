---
title: SizedADRLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedADRLIST
api_type:
- COM
ms.assetid: 5c64d74a-83a7-4122-b1d1-fcca0f4a6cdb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c35a1eb54b29c04bc8eed453272b59aae0ea737e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423459"
---
# <a name="sizedadrlist"></a>SizedADRLIST

**适用于**：Outlook 2013 | Outlook 2016 
  
定义具有指定名称的[ADRLIST](adrlist.md)结构, 其中包含指定数量的[ADRENTRY](adrentry.md)结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**ADRLIST** <br/> |
   
```cpp
SizedADRLIST (_centries,_name)
```

## <a name="parameters"></a>参数

__centries_
  
> 要包含在新**ADRLIST**结构中的**ADRENTRY**结构的计数。 
    
__名称_
  
> 新**ADRLIST**结构的名称。 
    
## <a name="remarks"></a>说明

**SizedADRLIST**宏允许您在已知数组长度要求时定义具有显式边界的收件人列表。 下面的代码演示如何将**SizedADRLIST**宏的结果转换为**ADRLIST**结构指针: 
  
```cpp
lpADRList = (LPADRLIST) &SizedADRList;
```

## <a name="see-also"></a>另请参阅

- [ADRLIST](adrlist.md)
- [ADRENTRY](adrentry.md)
- [与结构相关的宏](macros-related-to-structures.md)

