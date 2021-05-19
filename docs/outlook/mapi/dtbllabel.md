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
  
描述将在从显示表构建的对话框中使用的标签。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
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
  
> 字符字符串标签的内存位置。
    
 **ulFlags**
  
> 用于指定 **ulbLpszLabelName** 成员指向的标签格式的标志的位掩码。 可以设置以下标志： 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未MAPI_UNICODE，则标签采用 ANSI 格式。
    
## <a name="remarks"></a>备注

**DTBLLABEL** 结构描述与另一种类型的控件一起显示的标签控件文本，以向该控件添加含义。 例如，大多数编辑控件都位于标签旁边，以通知用户要输入的信息类型。 某些控件（如分组框和单选按钮）会保留它们自己的标签。 
  
标签可以包含一个Windows加速键，该加速键标识为与号 &amp; () 。 按加速键会将焦点放在显示表中此标签后的第一个非标签非按钮控件中。
  
不支持多行标签。 显示多行需要多个标签。
  
不能将标签用作只读编辑控件。 区别在于，可以选择和复制编辑控件，而标签不能。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

