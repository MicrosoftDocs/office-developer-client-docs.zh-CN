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
ms.openlocfilehash: 13dad61176a877295069317e4a5b51888b01bebb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778776"
---
# <a name="sizedadrlist"></a>SizedADRLIST

**适用于**： Outlook 
  
定义具有指定名称，其中包含指定的数目的[ADRENTRY](adrentry.md)结构[ADRLIST](adrlist.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**ADRLIST** <br/> |
   
```cpp
SizedADRLIST (_centries,_name)
```

## <a name="parameters"></a>参数

__centries_
  
> 要包含在新的**ADRLIST**结构**ADRENTRY**结构的计数。 
    
__名称_
  
> 新**ADRLIST**结构的的名称。 
    
## <a name="remarks"></a>说明

**SizedADRLIST**宏可以定义时已知数组长度要求具有显式边界的收件人列表。 下面的代码演示如何强制转换为**ADRLIST**结构指针**SizedADRLIST**宏的结果： 
  
```cpp
lpADRList = (LPADRLIST) &SizedADRList;
```

## <a name="see-also"></a>另请参阅

- [ADRLIST](adrlist.md)
- [ADRENTRY](adrentry.md)
- [与结构相关的宏](macros-related-to-structures.md)

