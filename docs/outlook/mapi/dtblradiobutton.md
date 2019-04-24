---
title: DTBLRADIOBUTTON
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLRADIOBUTTON
api_type:
- COM
ms.assetid: 64cef938-ef6f-43bb-8f6e-d4cd4d6c9888
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 94e412f2f542298adcedf4414c19b5303330cf2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339415"
---
# <a name="dtblradiobutton"></a>DTBLRADIOBUTTON

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍一个单选按钮组, 该按钮将成为单选按钮组的一部分。 单选按钮组将在根据显示表生成的对话框中使用。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _DTBLRADIOBUTTON
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulcButtons;
  ULONG ulPropTag;
  long lReturnValue;
} DTBLRADIOBUTTON, FAR *LPDTBLRADIOBUTTON;

```

## <a name="members"></a>Members

 **ulbLpszLabel**
  
> 单选按钮的字符字符串标签在内存中的位置。
    
 **ulFlags**
  
> 标志的位掩码, 用于指定**ulbLpszLabel**成员指向的标签的格式。 可以设置以下标志: 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。
    
 **ulcButtons**
  
> 单选按钮组中的按钮数。 组中其他按钮的**DTBLRADIOBUTTON**结构必须包含在显示表的连续行中。 这些行中的每一行应包含**ulcButtons**成员的相同值。 
    
 **ulPropTag**
  
> 类型为 PT_LONG 的属性的属性标记。 单选按钮组中的初始选择基于此属性的初始值。 该组中的每个按钮都必须将**ulPropTag**设置为同一属性。 
    
 **lReturnValue**
  
> 标识所选按钮的唯一编号。
    
## <a name="remarks"></a>注解

**DTBLRADIOBUTTON**结构描述了一个单选按钮与一组按钮相关联的按钮控件。 只能选中组中的一个按钮;设置一个按钮将导致取消设置组中的其他按钮。 
  
按钮计数是组中的单选按钮的数目。 组中其他单选按钮的结构必须位于显示表的后续行中。 这些结构中的每一个都应具有相同的按钮计数值。
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)
  
[DTCTL](dtctl.md)
  
[SizedDtblButton](sizeddtblbutton.md)


[MAPI 结构](mapi-structures.md)

