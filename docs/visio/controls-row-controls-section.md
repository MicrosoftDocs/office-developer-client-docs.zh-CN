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
description: 包含定义为形状定义的每个控制手柄的 x 坐标和 y 坐标和行为的单元格。 一个形状将包含每个控制手柄对应的一个控件行。
ms.openlocfilehash: dd5a96fe297cb62996ac2ab4d2974b8d1ae61a14
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282955"
---
# <a name="controls-row-controls-section"></a>Controls 行（“Controls”内容）

包含定义为形状定义的每个控制手柄的*x*坐标和*y*坐标和行为的单元格。 一个形状将包含每个控制手柄对应的一个控件行。 
  
Controls 行名为 Controls. *名称*并包含以下单元格。 有关详细信息，请参阅特定的单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[x](x-cell-controls-section.md) <br/> |表示表示形状的控制手柄在本地坐标系中的位置的*x*坐标。  <br/> |
|[y](y-cell-controls-section.md) <br/> |表示*y*坐标, 该坐标指示形状的控制手柄在本地坐标系中的位置。  <br/> |
|[X Dynamics](x-dynamics-cell-controls-section.md) <br/> |表示控制手柄的锚点在本地坐标系中的*x*坐标。  <br/> |
|[Y Dynamics](y-dynamics-cell-controls-section.md) <br/> |表示控制手柄的锚点在本地坐标系中的*y*坐标。  <br/> |
|[X Behavior](x-behavior-cell-controls-section.md) <br/> |控制控制手柄的*x*坐标在手柄移动后将表现的行为的类型。  <br/> |
|[Y Behavior](y-behavior-cell-controls-section.md) <br/> |控制控制手柄的*y*坐标在手柄移动后将表现的行为的类型。  <br/> |
|[Can Glue](can-glue-cell-controls-section.md) <br/> |确定控制手柄能否粘附到其他形状上。  <br/> |
|[尖](tip-cell-controls-section.md) <br/> |表示说明性文本字符串，用户将指针悬停于形状的控制手柄上时，此字符串以工具提示的形式显示。  <br/> |
   
## <a name="remarks"></a>注解

 可以根据需要添加任意多的 Controls.  根据需要*命名*行, 为行分配有意义的名称, 并设置单元格的值。 若要向现有的“Controls”内容添加控制手柄，请右击某一行，然后单击快捷菜单上的 **“插入行”**。 
  
可以通过上述单元格的行名称来引用这些单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。 为控件分配有意义的名称。 *名称*行, 请单击该行, 然后键入*Custom* , 例如, 创建行名称控件。自定义。 然后, 可以使用 Controls 引用 x 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

