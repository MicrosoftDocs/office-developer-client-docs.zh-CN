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
ms.openlocfilehash: 5256efbff734d4555ac263dd330e3349c789cd74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406974"
---
# <a name="dtblcombobox"></a>DTBLCOMBOBOX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在基于显示表构建的对话框中使用的组合框控件。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[SizedDtblComboBox](sizeddtblcombobox.md) <br/> |
   
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
  
> 从 **DTBLCOMBOBOX** 结构开始到描述可在组合框的编辑控件中输入的字符的限制（如果有）的字符串筛选器的偏移量。 筛选器不会解释为正则表达式，并且相同的筛选器将应用于输入的每一个字符。 筛选器的格式如下： 
    
|**字符**|**说明**|
|:-----|:-----|
| `*` <br/> |允许任何字符 (例如  `"*"` ，) 。  <br/> |
| `[ ]` <br/> |定义一组字符 (例如  `"[0123456789]"` ，) 。  <br/> |
| `-` <br/> |指示一系列字符 (例如  `"[a-z]"` ，) 。  <br/> |
| `~` <br/> |指示不允许这些字符。  (，例如  `"[~0-9]"` ，) 。  <br/> |
| `\` <br/> |用于引用前面的任何符号 (例如，允许使用  `"[\-\\\[\]]"` -、[和 \, ] 字符) 。  <br/> |
   
 **ulFlags**
  
> 用于指定字符串筛选器格式的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 筛选器采用 Unicode 格式。 如果未MAPI_UNICODE，筛选器采用 ANSI 格式。
    
 **ulNumCharsAllowed**
  
> 可以在组合框的文本框中输入的最大字符数。
    
 **ulPRPropertyName**
  
> 类型为 PT_TSTRING 的属性PT_TSTRING。 
    
 **ulPRTableName**
  
> 属性类型的属性标记PT_OBJECT **OpenProperty** 调用打开 **IMAPITable** 接口。 该表必须具有一个列，其属性与 **ulPRPropertyName** 成员标识的属性的类型相同。 表的行用于填充列表。 
    
## <a name="remarks"></a>备注

**DTBLCOMBOBOX** 结构描述一个组合框一个包含列表和选择字段的控件。 该列表显示用户可以从中选择的信息，并且选择字段显示当前所选内容。 选择字段是一个编辑控件，可用于输入列表中尚未包含的文本。 
  
这两个属性标记成员协同工作，以协调列表显示与编辑控件。 当 MAPI 首次显示组合框时，它将调用与显示表关联的 **IMAPIProp** 实现 **OpenProperty** 方法，以检索 **ulPRTableName** 成员表示的表。 此表有一列，列包含 **ulPRPropertyName** 成员所代表的属性的值。 因此，此列的类型必须与 **ulPRPropertyName** 属性的类型相同，并且两列都必须是字符串。 
  
列的值显示在组合框的列表部分。 因此 **，PR_NULL (** [PidTagNull](pidtagnull-canonical-property.md)) 不是 **ulPRPropertyName 的有效属性标记**。 当用户选择其中一行或在文本框中输入新数据时 **，ulPRPropertyName** 属性将设置为选定或输入的值。 
  
若要显示编辑控件的初始值，MAPI 将调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 来检索显示表的属性值。 如果检索的属性之一与 **ulPRPropertyName** 成员所代表的属性匹配，则其值将成为初始值。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[PidTagControlType 规范属性](pidtagcontroltype-canonical-property.md)


[MAPI 结构](mapi-structures.md)

