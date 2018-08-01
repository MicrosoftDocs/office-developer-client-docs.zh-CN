---
title: Actions 行（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60017
localization_priority: Normal
ms.assetid: 29a7464a-b9d4-a8ea-161b-3044de32ed23
description: 包含指定快捷菜单或动作标记菜单上的自定义命令与关联的操作的单元格。 操作部分包含一个 Actions 行的每个操作。
ms.openlocfilehash: f25ab75fe2bec35b09d2910ef731d11264224b7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779629"
---
# <a name="actions-row-actions-section"></a>Actions 行（“Actions”部分）

包含指定快捷菜单或动作标记菜单上的自定义命令与关联的操作的单元格。 操作部分包含一个 Actions 行的每个操作。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
操作行被命名操作。 *名称*，并且包含以下单元格。 有关详细信息，请参阅特定单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[Action](action-cell-actions-section.md) <br/> |包含当用户选择快捷菜单或动作标记菜单上的项时要执行的公式。
  <br/> |
|[Menu](menu-cell-actions-section.md) <br/> |定义动作标记菜单或快捷菜单上的菜单项显示的名称。  <br/> |
|[TagName](tagname-cell-actions-section.md) <br/> |此动作应在其中显示的动作标记的逻辑名。  <br/> |
|[ButtonFace](buttonface-cell-actions-section.md) <br/> |标识在快捷菜单或动作标记菜单上的项旁边显示的图标。  <br/> |
|[SortKey](sortkey-cell-actions-section.md) <br/> |确定菜单项在动作标记菜单或快捷菜单上的显示顺序的数字。  <br/> |
|[Checked](checked-cell-actions-section.md) <br/> |指示是否在动作标记菜单或快捷菜单上选中该菜单项。  <br/> |
|[已禁用](disabled-cell-actions-section.md) <br/> |指示快捷菜单或动作标记菜单上的菜单项是否被禁用。  <br/> |
|[ReadOnly](readonly-cell-actions-section.md) <br/> |指示菜单项是否为只读（不能单击）。  <br/> |
|[不可见](invisible-cell-actions-section.md) <br/> |指示菜单项在动作标记菜单或快捷菜单上是否可见。  <br/> |
|[BeginGroup](begingroup-cell-actions-section.md) <br/> |指示是否向菜单中的菜单项上插入一个分隔符。  <br/> |
   
## <a name="remarks"></a>说明

 您可以添加任意多个操作。  *名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。 将自定义命令添加到现有的 Actions 内容中，右击某一行，然后单击快捷菜单上的**插入行**。 
  
可通过，这些行名称在 ShapeSheet 窗口中显示为红色文本来引用这些单元格。 操作分配有意义的名称。 *名称*行中，单击行，，然后键入名称，例如*自定义*，例如，若要创建的行名称指定有。 然后，您可以通过使用 Actions.Custom.Menu 引用 Menu 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

