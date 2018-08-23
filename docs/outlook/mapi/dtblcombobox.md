---
title: DTBLCOMBOBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLCOMBOBOX
api_type:
- COM
ms.assetid: 73b68614-6aca-4669-b879-5631c5d6483c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8d2f2c82c61280bae88c715f8ffae19e10f00f9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577840"
---
# <a name="dtblcombobox"></a>DTBLCOMBOBOX

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述将显示表中生成的对话框中使用的组合框控件。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[SizedDtblComboBox](sizeddtblcombobox.md) <br/> |
   
```cpp
typedef struct _DTBLCOMBOBOX
{
  ULONG ulbLpszCharsAllowed;
  ULONG ulFlags;
  ULONG ulNumCharsAllowed;
  ULONG ulPRPropertyName;
  ULONG ulPRTableName;
} DTBLCOMBOBOX, FAR *LPDTBLCOMBOBOX;

```

## <a name="members"></a>Members

 **ulbLpszCharsAllowed**
  
> 从**DTBLCOMBOBOX**结构开始到字符的字符串筛选器，描述限制，如果任何，可以在组合框中输入的字符编辑控件的偏移量。 筛选器将不被解释为一个正则表达式和相同的筛选器应用于输入每个字符。 筛选器的格式如下所示： 
    
|**字符**|**说明**|
|:-----|:-----|
| `*` <br/> |允许任何字符 (例如， `"*"`)。  <br/> |
| `[ ]` <br/> |定义一组字符 (例如， `"[0123456789]"`)。  <br/> |
| `-` <br/> |指示某个范围的字符 (例如， `"[a-z]"`)。  <br/> |
| `~` <br/> |指示不允许这些字符。 (例如， `"[~0-9]"`)。  <br/> |
| `\` <br/> |用于 quote 任何以前符号 (例如，`"[\-\\\[\]]"`是指-， \, [，和] 允许字符)。  <br/> |
   
 **ulFlags**
  
> 用于指定格式的字符的字符串筛选器的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 筛选器在 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，筛选器为 ANSI 格式。
    
 **ulNumCharsAllowed**
  
> 可以在组合框的文本框中输入的字符的最大数量。
    
 **ulPRPropertyName**
  
> 属性标记类型 PT_TSTRING 的属性。 
    
 **ulPRTableName**
  
> 属性标记类型 PT_OBJECT 在其可以使用**OpenProperty**呼叫打开**IMAPITable**接口的属性。 表中必须包含一个列是由**ulPRPropertyName**成员标识的属性类型相同的属性。 Table 的行用于填充列表。 
    
## <a name="remarks"></a>注解

**DTBLCOMBOBOX**结构介绍组合框列表和选择字段组成的控件。 列表呈现从中可以选择用户，并选择字段显示当前选定内容的信息。 选择字段是还可用于在列表中尚未输入文本编辑控件。 
  
两个属性标记成员协同工作来协调列表显示与编辑控件。 当 MAPI 首次显示组合框中时，它会调用与要检索表示由**ulPRTableName**成员的表的显示表相关联的**IMAPIProp**实现**OpenProperty**方法。 此表有一个列包含由**ulPRPropertyName**成员属性的值的列。 因此，此列必须**ulPRPropertyName**属性类型相同的并且这两个列必须字符的字符串。 
  
组合框列表部分中显示的列的值。 因此， **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 不是有效属性标记为**ulPRPropertyName**。 当用户选择行之一，或在文本框中输入新的数据时， **ulPRPropertyName**属性设置为所选或输入值。 
  
若要显示的编辑控件的初始值，MAPI 调用[IMAPIProp::GetProps](imapiprop-getprops.md)检索显示表的属性值。 如果检索到的属性之一与匹配由**ulPRPropertyName**成员的属性，则其值成为的初始值。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[PidTagControlType 规范属性](pidtagcontroltype-canonical-property.md)


[MAPI 结构](mapi-structures.md)

