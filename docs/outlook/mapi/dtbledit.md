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
ms.openlocfilehash: b07ea265b5dcc6b9a9abb15c6be7ac9e0f94e8ed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404678"
---
# <a name="dtbledit"></a>DTBLEDIT

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在从显示表构建的对话框中使用的编辑控件。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[SizedDtblEdit](sizeddtbledit.md) <br/> |
   
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
  
> 从 **DTBLEDIT** 结构开始到描述可在编辑控件中输入的字符的限制（如果有）的字符串筛选器的偏移量。 筛选器不会解释为正则表达式，并且相同的筛选器将应用于输入的每一个字符。 筛选器的格式如下： 
    
|**字符**|**说明**|
|:-----|:-----|
| `*` <br/> |允许任何字符 (例如  `"*"` ，) 。  <br/> |
| `[ ]` <br/> |定义一组字符 ( `"[0123456789]".` 例如，)   <br/> |
| `-` <br/> |指示一系列字符 (例如  `"[a-z]"` ，) 。  <br/> |
| `~` <br/> |指示不允许使用这些字符 (例如  `"[~0-9]"` ，) 。  <br/> |
| `\` <br/> |用于引用前面的任何符号 (例如，允许使用  `"[\-\\\[\]]"` -、[和 \, ] 字符) 。  <br/> |
   
 **ulFlags**
  
> 用于指定字符筛选器格式的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE
  
> 筛选器采用 Unicode 格式。 如果未MAPI_UNICODE，筛选器采用 ANSI 格式。
    
 **ulNumCharsAllowed**
  
> 用户可在文本框中键入的最大字符数。
    
 **ulPropTag**
  
> 类型为 PT_TSTRING 的属性PT_TSTRING。 **ulPropTag** 成员标识在编辑控件中显示和编辑其数据的字符串属性。 
    
## <a name="remarks"></a>备注

**DTBLEDIT** 结构描述对话框中包含字母数字信息的编辑控件区域。 几乎所有对话框都至少有一个编辑控件。 用户可以修改编辑控件或只读控件。 
  
编辑控件还可以是单行或多行。 多行编辑控件通常具有与其关联的滚动条。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[PidTagControlType 规范属性](pidtagcontroltype-canonical-property.md)


[MAPI 结构](mapi-structures.md)

