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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423998"
---
# <a name="dtblpage"></a>DTBLPAGE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在从显示表构建的对话框中使用的选项卡式页面。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[SizedDtblPage](sizeddtblpage.md) <br/> |
   
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
  
> 在页面选项卡的字符字符串标签的内存中的位置。
    
 **ulFlags**
  
> 用于指定 **ulbLpszLabelName** 成员指向的标签格式的标志的位掩码。 可以设置以下标志： 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未MAPI_UNICODE，则标签采用 ANSI 格式。
    
 **ulbLpszComponent**
  
> 标识 MAPISVC 中的 **[帮助文件映射]** 部分的字符字符串的内存中的位置。INF 配置文件或 0。 显示在 MAPISVC 中的文件名。用户可以使用 INF 部分通过单击对话框中的"帮助"按钮访问选项卡式页面的扩展帮助。 有关 MAPISVC 中的条目详细信息。INF，请参阅 [MAPISVC 的文件格式。INF](file-format-of-mapisvc-inf.md)。
    
 **ulContext**
  
> **ulbLpszComponent** 成员定义的字符串中选项卡式页面的唯一标识符。 **ulbLpszComponent** 成员和 **ulContext** 成员必须为非零，"帮助"**按钮必须** 都为非零。 如果此标识符为零且组件字符串为 NULL，则没有与页面关联的帮助。 
    
## <a name="remarks"></a>备注

**DTBLPAGE** 结构描述选项卡式页面用于分隔多个相关对话框的控件。 通常，这些对话框是显示配置、邮件或收件人选项的属性表。 通过单击该选项卡，用户可以从一个工作表切换到另一个工作表。 
  
组件字符串和上下文标识符提供有关扩展帮助是否可用于选项卡式页面的信息。 如果扩展帮助可用，则组件字符串和上下文标识符将提供有关如何访问它的信息。 组件字符串映射到帮助文件;上下文标识符映射到初始帮助主题。 如果上下文标识符为零且组件字符串为 NULL，则扩展帮助不可用。
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

