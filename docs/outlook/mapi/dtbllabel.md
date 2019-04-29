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
ms.openlocfilehash: aa3345740c534b5ff156f062e731c98bc6164eed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410684"
---
# <a name="dtbllabel"></a>DTBLLABEL

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍将在从显示表生成的对话框中使用的标签。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏  <br/> |[SizedDtblLabel](sizeddtbllabel.md) <br/> |
   
```cpp
typedef struct _DTBLLABEL
{
  ULONG ulbLpszLabelName;
  ULONG ulFlags;
} DTBLLABEL, FAR *LPDTBLLABEL;

```

## <a name="members"></a>Members

 **ulbLpszLabelName**
  
> 字符字符串标签在内存中的位置。
    
 **ulFlags**
  
> 标志的位掩码, 用于指定**ulbLpszLabelName**成员指向的标签的格式。 可以设置以下标志: 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。
    
## <a name="remarks"></a>说明

**DTBLLABEL**结构描述了与另一种类型的控件一起显示的标签控件文本, 以向该控件添加含义。 例如, 大多数编辑控件放置在标签旁边, 以通知用户要输入的信息类型。 某些控件 (如分组框和单选按钮) 包含自己的标签。 
  
该标签可以包括 Windows 加速器, 标识为 "&" 符后面的字符&amp;()。 按加速键会将焦点放在显示表中此标签后面的第一个 nonlabel、nonbutton 控件中。
  
不支持多行标签。 显示多个行需要多个标签。
  
不能将标签用作只读的编辑控件。 区别在于, 可以选择和复制编辑控件, 而不能复制标签。 
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

