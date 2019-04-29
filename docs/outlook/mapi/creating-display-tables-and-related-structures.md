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
  
创建显示表类似于编写带有脚本语言的程序。 您可以通过调用[BuildDisplayTable](builddisplaytable.md)或编写自定义代码来填充表的行和列, 来创建显示表。 通常情况下, 应使用**BuildDisplayTable**技术, 因为它更简单。 
  
在您可以调用**BuildDisplayTable**以提示 MAPI 创建显示表之前, 必须生成一个结构层次结构。 顶级结构[DTPAGE](dtpage.md)描述单个选项卡式属性页。 在每个**DTPAGE**结构中, 都是一个用于描述单个控件 (如编辑框或选项按钮) 的[DTCTL](dtctl.md)结构。 每个**DTCTL**结构都包含一个特定于控件类型的结构。 例如, 如果**DTCTL**结构描述编辑框控件, 它将包含一个**DTBLEDIT**结构。 选项按钮的**DTCTL**结构包含**DTBLRADIOBUTTON**结构。 
  
这些结构直接与**BuildDisplayTable**相关联。它们在此函数的上下文之外没有任何意义。 调用**BuildDisplayTable**时, 会将一个或多个**DTPAGE**结构作为输入参数传递。 **DTPAGE**结构包含**DTCTL**结构的数组以及数组中**DTCTL**结构的数目。 对话框中显示的每个控件都有一个结构。 **DTPAGE**结构还具有一个字符串, 表示相应的帮助文件和对话框资源的名称。 
  
**DTPAGE**结构中的每个**DTCTL**结构都包含用于设置控件属性的以下数据: 
  
- 用于设置**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 的控件类型。
    
- 用于设置**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 的控件标志。
    
- 用于设置**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 的通知数据。
    
- 用于设置**PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 的控制结构。
    
**DTCTL**结构还包含资源标识符和 "编辑" 和 "组合框" 控件 (一个字符筛选器)。 
  
**DTCTL**结构的控制结构成员描述了控件类型所特有的数据。 MAPI 为每种控件类型定义了不同的结构。 例如, 编辑控件的数据由**DTBLEDIT**结构表示;列表框中的数据由**DTBLLBX**结构表示。 
  
三种类型的显示表结构之间的关系如下图所示。 此显示表所描述的对话框包含两个控件: 标签和编辑控件。 **DTBLLBX**结构具有一个 label 偏移量成员, 这是几个控制结构, 用于描述标签的字符串的起始位置。 标签字符字符串通常放在紧随结构之后的内存中。 
  
**显示表格结构**
  
![显示表结构](media/dtstruct.gif "显示表结构")
  
## <a name="see-also"></a>另请参阅

- [显示表实现](display-table-implementation.md)

