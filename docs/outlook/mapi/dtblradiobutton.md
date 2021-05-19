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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434597"
---
# <a name="dtblradiobutton"></a>DTBLRADIOBUTTON

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述一个将成为单选按钮组的一部分的单选按钮。 单选按钮组将在从显示表构建的对话框中使用。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 单选按钮的字符字符串标签的内存位置。
    
 **ulFlags**
  
> 用于指定 **ulbLpszLabel** 成员指向的标签格式的标志的位掩码。 可以设置以下标志： 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未MAPI_UNICODE，则标签采用 ANSI 格式。
    
 **ulcButtons**
  
> 单选按钮组中按钮的计数。 组中其他按钮的 **DTBLRADIOBUTTON** 结构必须包含在显示表的连续行中。 其中每一行应包含 **ulcButtons 成员相同的** 值。 
    
 **ulPropTag**
  
> 类型为 PT_LONG 的属性PT_LONG。 单选按钮组中的初始选择基于此属性的初始值。 组内每个按钮都必须将 **ulPropTag** 设置为同一属性。 
    
 **lReturnValue**
  
> 标识所选按钮的唯一编号。
    
## <a name="remarks"></a>备注

**DTBLRADIOBUTTON** 结构描述单选按钮与一组按钮关联的按钮控件。 只能检查该组中的一个按钮;设置一个按钮会导致取消设置组中其他按钮。 
  
按钮计数是组中单选按钮的数量。 组中其他单选按钮的结构必须显示在显示表中的后续行中。 其中每个结构应具有相同的按钮计数值。
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)
  
[DTCTL](dtctl.md)
  
[SizedDtblButton](sizeddtblbutton.md)


[MAPI 结构](mapi-structures.md)

