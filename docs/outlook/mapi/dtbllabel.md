---
title: DTBLLABEL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLLABEL
api_type:
- COM
ms.assetid: 5837facf-acd3-48fe-9610-f88085d99aef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28f6471f74fb0fcc4f7e2f4114f0790e1564e17e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774856"
---
# <a name="dtbllabel"></a>DTBLLABEL

  
  
**适用于**： Outlook 
  
描述将显示表中生成的对话框中使用的标签。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏  <br/> |[SizedDtblLabel](sizeddtbllabel.md) <br/> |
   
```cpp
typedef struct _DTBLLABEL
{
  ULONG ulbLpszLabelName;
  ULONG ulFlags;
} DTBLLABEL, FAR *LPDTBLLABEL;

```

## <a name="members"></a>Members

 **ulbLpszLabelName**
  
> 在内存中的字符的字符串标签的位置。
    
 **ulFlags**
  
> 用于指定所指的**ulbLpszLabelName**成员标签的格式的标志位掩码。 可以设置以下标记： 
    
MAPI_UNICODE 
  
> 标签为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。
    
## <a name="remarks"></a>说明

**DTBLLABEL**结构介绍与另一种控件添加到该控件的含义显示一个标签控件文本。 例如，大多数编辑控件位于旁边通知的类型信息的用户输入的标签。 某些控件，如组框和单选按钮，将保留其自己的标签。 
  
标签可以包括 Windows 加速键，标识为关注连字符的字符 (&amp;)。 按下加速键将焦点放入第一个 nonlabel，nonbutton 关注此标签显示表中的控件。
  
没有支持多行标签。 显示多行需要多个标签。
  
不能设置为只读的编辑控件中使用标签。 区别在于，可以选择并复制而标签不能编辑控件。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

