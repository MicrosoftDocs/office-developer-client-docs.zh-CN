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
ms.openlocfilehash: bc511ea4b3ec4eea9e38f744bcb8f277108085cc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413855"
---
# <a name="flatentrylist"></a>FLATENTRYLIST

**适用于**：Outlook 2013 | Outlook 2016 
  
包含[FLATENTRY](flatentry.md)结构的数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbFLATENTRYLIST](cbflatentrylist.md)、 [CbNewFLATENTRYLIST](cbnewflatentrylist.md) <br/> |
   
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
  
> 由**abEntries**成员描述的数组中的**FLATENTRY**结构的计数。 
    
**cbEntries**
  
> 由**abEntries**描述的数组中的字节数。 
    
**abEntries**
  
> 包含一个或多个**FLATENTRY**结构的字节数组, 该数组排列端到端。 
    
## <a name="remarks"></a>说明

在**abEntries**数组中, 每个**FLATENTRY**结构在自然对齐的边界处对齐。 填充包含额外的字节以确保任意两个**FLATENTRY**结构之间的自然对齐。 数组中的第一个**FLATENTRY**结构始终正确对齐, 因为**abEntries**成员的偏移量为8。 若要计算下一个结构的偏移量, 请使用第一项的大小向上舍入到接下来的4个。 使用[CbFLATENTRY](cbflatentry.md)宏计算**FLATENTRY**结构的大小。 
  
例如, 第二个**FLATENTRY**结构从包含第一项的偏移加上第一项的长度加上第一项的偏移量到接下来的四个字节的偏移量。 第一个条目的长度是其**cb**成员的长度加上其**abEntry**成员的长度。 
  
下面的代码示例指示如何在**FLATENTRYLIST**结构中计算偏移量。 假定_lpFlatEntry_是指向列表中第一个结构的指针。 
  
```cpp
(offsetof(lpFlatEntry->ab) // for example, 4
+ lpFlatEntry->cb // size of lpFlatEntry->ab 
+ 4) & ~3 // round to next 4 byte boundary
```

## <a name="see-also"></a>另请参阅

- [FLATENTRY](flatentry.md)
- [PidTagReplyRecipientEntries 规范属性](pidtagreplyrecipiententries-canonical-property.md)
- [MAPI 结构](mapi-structures.md)

