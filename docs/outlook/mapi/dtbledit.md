---
title: DTBLEDIT
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLEDIT
api_type:
- COM
ms.assetid: ec3566a0-75ad-466d-a61e-f7d61ccb946d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d0418ac2ec5d01d58c63e4ad48a1066cc386e946
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774849"
---
# <a name="dtbledit"></a>DTBLEDIT

  
  
**适用于**： Outlook 
  
描述将显示表中生成的对话框中使用编辑控件。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[SizedDtblEdit](sizeddtbledit.md) <br/> |
   
```cpp
typedef struct _DTBLEDIT
{
  ULONG ulbLpszCharsAllowed;
  ULONG ulFlags;
  ULONG ulNumCharsAllowed;
  ULONG ulPropTag;
} DTBLEDIT, FAR *LPDTBLEDIT;

```

## <a name="members"></a>Members

 **ulbLpszCharsAllowed**
  
> 从**DTBLEDIT**结构开始到描述的限制，如果有，可以编辑控件中输入的字符的字符的字符串筛选器偏移量。 筛选器将不被解释为一个正则表达式和相同的筛选器应用于输入每个字符。 筛选器的格式如下所示： 
    
|**字符**|**说明**|
|:-----|:-----|
| `*` <br/> |允许任何字符 (例如， `"*"`)。  <br/> |
| `[ ]` <br/> |定义一组字符 (例如， `"[0123456789]".`)  <br/> |
| `-` <br/> |指示某个范围的字符 (例如， `"[a-z]"`)。  <br/> |
| `~` <br/> |指示不允许这些字符 (例如， `"[~0-9]"`)。  <br/> |
| `\` <br/> |用于 quote 任何以前符号 (例如，`"[\-\\\[\]]"`是指-， \, [，和] 允许字符)。  <br/> |
   
 **ulFlags**
  
> 用于指定格式的字符筛选器的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE
  
> 筛选器在 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，筛选器为 ANSI 格式。
    
 **ulNumCharsAllowed**
  
> 最大用户可以在文本框中键入的字符数。
    
 **ulPropTag**
  
> 属性标记类型 PT_TSTRING 的属性。 **UlPropTag**成员标识显示和编辑控件中编辑其数据的字符串属性。 
    
## <a name="remarks"></a>说明

**DTBLEDIT**结构介绍编辑控件上一个对话框，包含字母数字信息的区域。 几乎在所有对话框都有至少一个编辑控件。 编辑控件可以由用户可修改或只读的。 
  
编辑控件也可以是单个行或多行。 多行编辑控件通常具有与其关联的滚动条。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[PidTagControlType 规范属性](pidtagcontroltype-canonical-property.md)


[MAPI 结构](mapi-structures.md)

