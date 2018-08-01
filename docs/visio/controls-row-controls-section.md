---
title: Controls 行（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1024624
localization_priority: Normal
ms.assetid: a57bdcd9-566b-5054-7458-7d84cbb78d23
description: 包含用于定义 x 和 y 单元格-为形状定义的坐标和每个控制手柄的行为。 形状将包含每个控制手柄的一个 Controls 行。
ms.openlocfilehash: ed1d57fce6d413b9eb7f5d119264bc2bfa968222
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779986"
---
# <a name="controls-row-controls-section"></a>Controls 行（“Controls”部分）

包含用于定义*x*和*y*单元格-为形状定义的坐标和每个控制手柄的行为。 形状将包含每个控制手柄的一个 Controls 行。 
  
控件行被命名控件。 *名称*，并且包含以下单元格。 有关详细信息，请参阅特定单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[x](x-cell-controls-section.md) <br/> |代表*x* -指示形状的控制手柄在本地坐标系中的位置的坐标。  <br/> |
|[y](y-cell-controls-section.md) <br/> |代表*y* -指示形状的控制手柄在本地坐标系中的位置的坐标。  <br/> |
|[X Dynamics](x-dynamics-cell-controls-section.md) <br/> |代表*x*的控制手柄的锚点在本地坐标系中的坐标。  <br/> |
|[Y Dynamics](y-dynamics-cell-controls-section.md) <br/> |代表*y* -控制手柄的锚点在本地坐标系中的坐标。  <br/> |
|[X 行为](x-behavior-cell-controls-section.md) <br/> |控制的行为*x*的类型的控制手柄的坐标在手柄移动后将表现。  <br/> |
|[Y Behavior](y-behavior-cell-controls-section.md) <br/> |控件类型的行为*y* -控制手柄的坐标在手柄移动后将表现。  <br/> |
|[Can Glue](can-glue-cell-controls-section.md) <br/> |确定控制手柄能否粘附到其他形状上。  <br/> |
|[提示](tip-cell-controls-section.md) <br/> |表示说明性文本字符串，用户将指针悬停于形状的控制手柄上时，此字符串以工具提示的形式显示。  <br/> |
   
## <a name="remarks"></a>注解

 您可以添加任意多个控件。  *名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。 若要添加到现有的 Controls 内容的控制手柄，右击某一行，然后单击快捷菜单上的**插入行**。 
  
可通过，这些行名称在 ShapeSheet 窗口中显示为红色文本来引用这些单元格。 若要为控件指定有意义的名称。 *名称*行中，单击行，然后键入*自定义*，例如，若要创建的行名称 Controls.Custom。 然后，可以引用使用 Controls.Custom.X 则 X 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

