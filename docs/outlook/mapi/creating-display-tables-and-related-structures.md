---
title: 创建显示表和相关结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a8548040-13ed-4a9f-a7ca-de610f94d7df
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 350272324c3827f4630f0cf35e3ade0ff213ac4d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416242"
---
# <a name="creating-display-tables-and-related-structures"></a>创建显示表和相关结构
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建显示表类似于使用脚本语言编写程序。 可以通过调用 [BuildDisplayTable](builddisplaytable.md) 或编写自定义代码来填充表的行和列来创建显示表。 通常，你应该使用 **BuildDisplayTable** 技术，因为它更简单。 
  
在调用 **BuildDisplayTable** 以提示 MAPI 创建显示表之前，必须构建结构层次结构。 顶级结构 [DTPAGE](dtpage.md)描述了单个选项卡式属性页。 每个 **DTPAGE 结构** 都是描述单个控件（如编辑框或选项按钮）的 [DTCTL](dtctl.md) 结构。 每个 **DTCTL** 结构都包含特定于控件类型的结构。 例如，如果 **DTCTL** 结构描述编辑框控件，它将包含 **DTBLEDIT** 结构。 选项 **按钮的 DTCTL** 结构包含 **DTBLRADIOBUTTON** 结构。 
  
这些结构与 **BuildDisplayTable 直接相关**;它们在此函数的上下文之外没有任何意义。 调用 **BuildDisplayTable** 时，将一个或多个 **DTPAGE** 结构作为输入参数传递。 **DTPAGE** 结构包含一个 **DTCTL** 结构数组和该 **数组中 DTCTL** 结构的数量计数。 对话框中显示每个控件都有一个结构。 **DTPAGE** 结构还有一个字符串，表示相应的帮助文件和对话框资源的名称。 
  
**DTPAGE** 结构的每个 **DTCTL** 结构都包含以下数据，这些数据用于设置控件的属性： 
  
- 用于设置 [PidTagControlType](pidtagcontroltype-canonical-property.md) **PR_CONTROL_TYPE (** 控件) 。
    
- 用于设置 [PidTagControlFlags](pidtagcontrolflags-canonical-property.md) **PR_CONTROL_FLAGS (** 控件标记) 。
    
- 用于设置 [PidTagControlId](pidtagcontrolid-canonical-property.md) **PR_CONTROL_ID (的通知**) 。
    
- 用于设置 [PidTagControlStructure](pidtagcontrolstructure-canonical-property.md) **PR_CONTROL_STRUCTURE (** 控件) 。
    
**DTCTL** 结构还包含资源标识符，对于编辑框和组合框控件，还包含字符筛选器。 
  
**DTCTL** 结构的控件结构成员描述控件类型的唯一数据。 MAPI 为每个控件类型定义不同的结构。 例如，编辑控件的数据由 **DTBLEDIT** 结构表示;列表框的数据由 **DTBLLBX** 结构表示。 
  
下图显示了三种类型的显示表格结构之间的关系。 此显示表描述的对话框有两个控件：一个标签控件和一个编辑控件。 **DTBLLBX** 结构具有一个标签偏移成员，与若干控件结构一样，该成员描述标签的字符串开始的位置。 标签字符串通常放在紧随结构之后的内存中。 
  
**显示表格结构**
  
![显示表结构](media/dtstruct.gif "显示表结构")
  
## <a name="see-also"></a>另请参阅

- [显示表实现](display-table-implementation.md)

