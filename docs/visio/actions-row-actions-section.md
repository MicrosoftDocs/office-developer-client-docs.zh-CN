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
description: 包含指定与快捷菜单或动作标记菜单上的自定义命令相关联的动作的单元格。 对于每个动作，“Actions”内容中均包含一个与其对应的 Actions 行。
ms.openlocfilehash: 37464e98b3e4f7d07b2ae4bd391b31ec009b6726
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408003"
---
# <a name="actions-row-actions-section"></a>Actions 行（“Actions”内容）

包含指定与快捷菜单或动作标记菜单上的自定义命令相关联的动作的单元格。 对于每个动作，“Actions”内容中均包含一个与其对应的 Actions 行。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
Actions 行名为 Actions. *name*  并包含以下单元格。 有关详细信息，请参阅特定的单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[Action](action-cell-actions-section.md) <br/> |包含当用户选择快捷菜单或动作标记菜单上的项时要执行的公式。  <br/> |
|[菜单](menu-cell-actions-section.md) <br/> |定义显示在动作标记或快捷菜单上的菜单项的名称。  <br/> |
|[TagName](tagname-cell-actions-section.md) <br/> |此动作应在其中显示的动作标记的逻辑名。  <br/> |
|[ButtonFace](buttonface-cell-actions-section.md) <br/> |标识在快捷菜单或动作标记菜单上的项旁边显示的图标。  <br/> |
|[SortKey](sortkey-cell-actions-section.md) <br/> |确定菜单项在动作标记菜单或快捷菜单上的显示顺序的数字。  <br/> |
|[Checked](checked-cell-actions-section.md) <br/> |指示是否在动作标记或快捷菜单上检查菜单项。  <br/> |
|[Disabled](disabled-cell-actions-section.md) <br/> |指示快捷菜单或动作标记菜单上的菜单项是否被禁用。  <br/> |
|[ReadOnly](readonly-cell-actions-section.md) <br/> |指示菜单项是否为只读（不能单击）。  <br/> |
|[不可见](invisible-cell-actions-section.md) <br/> |指示菜单项在动作标记菜单或快捷菜单上是否可见。  <br/> |
|[BeginGroup](begingroup-cell-actions-section.md) <br/> |指示是否在菜单项上方的菜单中插入分隔符。  <br/> |
   
## <a name="remarks"></a>备注

 可以根据需要添加任意多的 Actions.  *命名*  行（如需要）为行指定有意义的名称，并设置单元格值。 若要向现有的“Actions”内容添加自定义命令，请右键单击某一行，然后单击快捷菜单上的 **“插入行”**。 
  
可以通过上述单元格的行名称来引用这些单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。 若要为 Actions. *name*  row， click the row， and then type a name such as  *Custom*  ， for example， to create the row name Actions.Custom. 然后可使用 Actions.Custom.Menu 引用 Menu 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

