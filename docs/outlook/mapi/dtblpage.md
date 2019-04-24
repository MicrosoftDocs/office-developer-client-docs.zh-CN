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
ms.openlocfilehash: 6f3d98a3133d79f78f4eb676d49ec85ef5a359f1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340115"
---
# <a name="dtblpage"></a>DTBLPAGE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍将在从显示表生成的对话框中使用的选项卡式页面。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[SizedDtblPage](sizeddtblpage.md) <br/> |
   
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
  
> 页面选项卡的字符字符串标签在内存中的位置。
    
 **ulFlags**
  
> 标志的位掩码, 用于指定**ulbLpszLabelName**成员指向的标签的格式。 可以设置以下标志: 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。
    
 **ulbLpszComponent**
  
> 在内存中标识 mapisvc.inf 中的 **[帮助文件映射]** 部分的字符串的位置 (以字符为单位)。INF 配置文件或0。 mapisvc.inf 中显示的文件名。INF 节可供用户用来通过单击对话框中的 "**帮助**" 按钮来访问选项卡式页面的扩展帮助。 有关 mapisvc.inf 中的条目的详细信息。INF, 请参阅[mapisvc.inf 的文件格式。INF](file-format-of-mapisvc-inf.md)。
    
 **ulContext**
  
> **ulbLpszComponent**成员定义的字符串中选项卡式页面的唯一标识符。 **ulbLpszComponent**成员和**ulContext**成员必须均为非零, "**帮助**" 按钮才能正常工作。 如果此标识符为零, 并且组件字符串为 NULL, 则没有与该页面关联的帮助。 
    
## <a name="remarks"></a>注解

**DTBLPAGE**结构描述了一个用于分隔多个相关对话框的选项卡式页面控件。 通常情况下, 这些对话框是用于显示配置、消息或收件人选项的属性表。 通过单击该选项卡, 用户可以从一张工作表切换到另一张。 
  
组件字符串和上下文标识符提供有关扩展的帮助是否适用于选项卡式页面的信息。 如果扩展的帮助可用, 组件字符串和上下文标识符将提供有关如何访问的信息。 组件字符串映射到帮助文件;上下文标识符映射到初始帮助主题。 如果上下文标识符为零, 并且组件字符串为 NULL, 则扩展帮助不可用。
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

