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
ms.openlocfilehash: e601a59a68a3a7d248165d4e573c5abc34d27e2a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586464"
---
# <a name="sbinaryarray"></a>SBinaryArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的二进制值的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SBinaryArray
{
  ULONG cValues;
  SBinary FAR *lpbin;
} SBinaryArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 由**lpbin**成员指向数组中的值的数目。 
    
 **lpbin**
  
> 指向保存二进制值的数组[SBinary](sbinary.md)结构的指针。 
    
## <a name="remarks"></a>注解

**SBinaryArray**结构用于描述 PT_MV_BINARY 类型的属性。 
  
有关 PT_MV_BINARY 的详细信息，请参阅[列表的属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SBinary](sbinary.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

