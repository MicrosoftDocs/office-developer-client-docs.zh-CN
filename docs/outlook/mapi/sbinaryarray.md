---
title: SBinaryArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SBinaryArray
api_type:
- COM
ms.assetid: 2d5b7302-cad2-4522-beb1-7c6c711f42e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 12fefbe15491837878608540006e5dd7dc3033ea
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438286"
---
# <a name="sbinaryarray"></a>SBinaryArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含二进制值数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SBinaryArray
{
  ULONG cValues;
  SBinary FAR *lpbin;
} SBinaryArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpbin**成员指向的数组中的值的计数。 
    
 **lpbin**
  
> 指向保存二进制值的[SBinary](sbinary.md)结构的数组的指针。 
    
## <a name="remarks"></a>说明

**SBinaryArray**结构用于描述 PT_MV_BINARY 类型的属性。 
  
有关 PT_MV_BINARY 的详细信息, 请参阅[属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SBinary](sbinary.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

