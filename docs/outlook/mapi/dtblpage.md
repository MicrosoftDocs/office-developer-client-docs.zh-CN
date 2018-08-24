---
title: DTBLPAGE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLPAGE
api_type:
- COM
ms.assetid: f899f434-a5d7-4b4f-98f9-c14c9f21b24b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd0caff8a6c7834bdd01ef4be64805bde66dd6d9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578820"
---
# <a name="dtblpage"></a>DTBLPAGE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将显示表中生成的对话框中使用的选项卡式的页面。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[SizedDtblPage](sizeddtblpage.md) <br/> |
   
```cpp
typedef struct _DTBLPAGE
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulbLpszComponent;
  ULONG ulContext;
} DTBLPAGE, FAR *LPDTBLPAGE;

```

## <a name="members"></a>Members

 **ulbLpszLabel**
  
> 在页面选项卡的字符的字符串标签的内存中的位置。
    
 **ulFlags**
  
> 用于指定所指的**ulbLpszLabelName**成员标签的格式的标志位掩码。 可以设置以下标记： 
    
MAPI_UNICODE 
  
> 标签为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。
    
 **ulbLpszComponent**
  
> 用于标识 MAPISVC 中的 **[帮助文件映射]** 节字符串的内存中的位置。INF 配置文件或 0。 在文件名 MAPISVC 中出现的情况下。INF 部分可以由用户，用于通过单击对话框中的**帮助**按钮访问选项卡式页上的扩展的帮助。 有关 MAPISVC 中的条目的详细信息。INF，请参阅[文件格式的 MAPISVC。INF](file-format-of-mapisvc-inf.md)。
    
 **ulContext**
  
> 定义由**ulbLpszComponent**成员在字符串中选项卡式页面的唯一标识符。 **UlbLpszComponent**成员和**ulContext**成员必须都为非零值来**帮助**按钮正常工作。 如果此标识符为 0，组件字符串为 NULL，则没有与页面相关的帮助。 
    
## <a name="remarks"></a>注解

**DTBLPAGE**结构介绍用于分隔多个相关的对话框的控件的选项卡式的页面。 通常，这些对话框是用于显示配置、 消息或收件人选项的属性表。 通过单击选项卡，用户可以张工作表之间切换。 
  
组件字符串和上下文标识符提供有关扩展的帮助是否可用于选项卡式页面的信息。 如果扩展的帮助可用，组件字符串和上下文标识符将提供有关如何访问它的信息。 组件字符串映射到的帮助文件;上下文标识符映射到初始的帮助主题。 如果组件字符串为 NULL 的上下文标识符为零，则扩展的帮助不可用。
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

