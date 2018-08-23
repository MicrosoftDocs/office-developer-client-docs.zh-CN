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
ms.openlocfilehash: 493176029be3e7b154188aa164a95a8bc9c0e7d9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569741"
---
# <a name="dtblradiobutton"></a>DTBLRADIOBUTTON

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
介绍将成为单选按钮组的一部分的一个单选按钮。 将显示表中生成的对话框中使用的单选按钮组。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 在内存中的单选按钮的字符的字符串标签的位置。
    
 **ulFlags**
  
> 用于指定所指的**ulbLpszLabel**成员标签的格式的标志位掩码。 可以设置以下标记： 
    
MAPI_UNICODE 
  
> 标签为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。
    
 **ulcButtons**
  
> 单选按钮组中的按钮的计数。 显示表的连续行中都必须包含其他按钮的组中的**DTBLRADIOBUTTON**结构。 每个这些行应**ulcButtons**成员的包含相同的值。 
    
 **ulPropTag**
  
> 属性标记类型 PT_LONG 的属性。 单选按钮组中的初始选择基于此属性的初始值。 组中的每个按钮必须**ulPropTag**设置为相同的属性。 
    
 **lReturnValue**
  
> 标识所选的按钮的唯一编号。
    
## <a name="remarks"></a>注解

**DTBLRADIOBUTTON**结构介绍与一组按钮关联的一个按钮控件的单选按钮。 可以检查组中的只有一个按钮;设置一个按钮使未设置组中的其他按钮。 
  
将按钮的数目是组中的单选按钮数。 显示表中的后续行中必须是其他单选按钮组中的结构。 每个这些结构应具有相同的值，它按钮的计数。
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)
  
[DTCTL](dtctl.md)
  
[SizedDtblButton](sizeddtblbutton.md)


[MAPI 结构](mapi-structures.md)

