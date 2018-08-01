---
title: FLATENTRYLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLATENTRYLIST
api_type:
- COM
ms.assetid: b465d015-9b62-4986-b0df-118121f60602
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8f17c3cf3d3d00930f87acd004b24f683a3fc8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774940"
---
# <a name="flatentrylist"></a>FLATENTRYLIST

**适用于**： Outlook 
  
包含一个[FLATENTRY](flatentry.md)结构数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbFLATENTRYLIST](cbflatentrylist.md) [CbNewFLATENTRYLIST](cbnewflatentrylist.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cEntries;
  ULONG cbEntries;
  BYTE abEntries[MAPI_DIM];
} FLATENTRYLIST, FAR *LPFLATENTRYLIST;

```

## <a name="members"></a>Members

**cEntries**
  
> **FLATENTRY**结构由**abEntries**成员描述该数组中的计数。 
    
**cbEntries**
  
> 描述**abEntries**数组中的字节数。 
    
**abEntries**
  
> 字节数组，其中包含一个或多个**FLATENTRY**结构排列的端到端。 
    
## <a name="remarks"></a>说明

在**abEntries**数组中，每个**FLATENTRY**结构自然地对齐边界上对齐。 额外字节都作为包含填充使任意两个**FLATENTRY**结构之间的确保自然对齐。 该数组中的第一个**FLATENTRY**结构对齐始终正确，因为**abEntries**成员的偏移量为 8。 若要计算的偏移量的下一个结构，使用向上舍入到 4 的下一步的倍数的第一个条目的大小。 使用[CbFLATENTRY](cbflatentry.md)宏来计算**FLATENTRY**结构的大小。 
  
例如，第二个**FLATENTRY**结构开始在偏移量为组成的第一个条目的偏移量以及舍入到下一步的四个字节的第一个条目的长度。 第一个条目的长度是其**cb**成员长度加上其**abEntry**成员的长度。 
  
下面的代码示例指示如何计算**FLATENTRYLIST**结构中的偏移量。 假定该_lpFlatEntry_是指向列表中的第一个结构的指针。 
  
```cpp
(offsetof(lpFlatEntry->ab) // for example, 4
+ lpFlatEntry->cb // size of lpFlatEntry->ab 
+ 4) & ~3 // round to next 4 byte boundary
```

## <a name="see-also"></a>另请参阅

- [FLATENTRY](flatentry.md)
- [PidTagReplyRecipientEntries 规范属性](pidtagreplyrecipiententries-canonical-property.md)
- [MAPI 结构](mapi-structures.md)

