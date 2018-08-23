---
title: 创建显示表和相关的结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a8548040-13ed-4a9f-a7ca-de610f94d7df
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e17306e2b90f26dcef0a0214e78080fe78752e5f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568565"
---
# <a name="creating-display-tables-and-related-structures"></a>创建显示表和相关的结构
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建显示表是类似于编写脚本语言的程序。 您可以创建显示表通过调用[BuildDisplayTable](builddisplaytable.md)或编写自定义代码以填充的行和列的表。 一般情况下，您应使用**BuildDisplayTable**技术，因为它是简单。 
  
您可以调用**BuildDisplayTable**提示 MAPI 创建显示表之前，没有的层次结构，必须建立。 顶级结构， [DTPAGE](dtpage.md)，描述单个选项卡式的属性页。 在每个**DTPAGE**结构是描述单个控件，例如编辑框或选项按钮的[DTCTL](dtctl.md)结构。 每个**DTCTL**结构包含特定于控件的类型的结构。 例如，如果**DTCTL**结构介绍编辑框控件，它将包含**DTBLEDIT**结构。 选项按钮的**DTCTL**结构包含一个**DTBLRADIOBUTTON**结构。 
  
这些结构直接相关**BuildDisplayTable**;拥有此函数的上下文之外没有意义。 调用**BuildDisplayTable**时，您将作为输入参数传递一个或多个**DTPAGE**结构。 **DTPAGE**结构包含数组**DTCTL**结构和**DTCTL**结构数组中的数目。 没有要显示在对话框中每个控件的一个结构。 **DTPAGE**结构还具有一个字符字符串，表示相应的帮助文件和对话框框资源的名称。 
  
**DTPAGE**结构中的每个**DTCTL**结构包含用于设置控件的属性的以下数据： 
  
- 设置**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 控件类型。
    
- 用于设置**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 控制标志。
    
- 通知设置**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 的数据。
    
- 用于设置**PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 控制结构。
    
**DTCTL**结构还包含资源标识符以及编辑和组合框控件、 字符筛选器。 
  
**DTCTL**结构的控制结构成员介绍了唯一的控件的类型的数据。 MAPI 定义每个控件类型不同的结构。 例如，编辑控件的数据表示由**DTBLEDIT**结构;由**DTBLLBX**结构表示列表框的数据。 
  
下图中显示三种类型的显示表结构之间的关系。 通过此显示表所述的对话框中有两个控件： 标签和编辑控件。 **DTBLLBX**结构有一个标签偏移的成员，如执行几个控制结构，描述标签的字符串的开始位置。 标签字符串通常放置在紧挨结构的内存。 
  
**显示表格结构**
  
![显示表结构](media/dtstruct.gif "显示表结构")
  
## <a name="see-also"></a>另请参阅

- [显示表实现](display-table-implementation.md)

