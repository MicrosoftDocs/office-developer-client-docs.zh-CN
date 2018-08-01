---
title: Connection Points 行（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3005
localization_priority: Normal
ms.assetid: eaac62a5-f516-9b81-587a-8e0e02de59ee
description: 包含 x 和 y-坐标、 水平和垂直方向和指向形状上一次连接的类型。 从形状的原点的测量连接点的坐标。 形状包含每个连接点的一个 Connection Points 行。
ms.openlocfilehash: f1b8daf7f9845b85e76020c7f89c8c42b4500823
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779962"
---
# <a name="connection-points-row-connection-points-section"></a>Connection Points 行（“Connection Points”部分）

包含*x*和*y* -坐标、 水平和垂直方向和指向形状上一次连接的类型。 从形状的原点的测量连接点的坐标。 形状包含每个连接点的一个 Connection Points 行。 
  
如果命名 Connection Points 行，这些名称显示为连接。 在 ShapeSheet 窗口中的*名称*。 Connection Points 行包含以下单元格。 有关详细信息，请参阅特定单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-connection-points-section.md) <br/> |*X* -在本地坐标系中的连接点的坐标。  <br/> |
|[Y](y-cell-connection-points-section.md) <br/> |*Y* -在本地坐标系中的连接点的坐标。  <br/> |
|[DirX/A](dirxa-cell-connection-points-section.md) <br/> |*X* -组件所需的对齐向量的匹配连接点。 此外可用于确定动态连接线的附加的线路的方向。 此单元格采用浮点数据点值。  <br/> |
|[DirY/B](diryb-cell-connection-points-section.md) <br/> |*Y* -组件所需的对齐向量的匹配连接点。 此外可用于确定动态连接线的附加的线路的方向。 此单元格采用浮点数据点值。  <br/> |
|[Type/C](typec-cell-connection-points-section.md) <br/> |连接点类型（0 = 向内；1 = 向外；2 = 向内 + 向外）。  <br/> |
|[D](d-cell-connection-points-section.md) <br/> |可用于输入或测试公式的草稿单元格。若要访问此单元格，可右击某一行，然后单击快捷菜单上的 **“更改行类型”**。<br/> |
   
## <a name="remarks"></a>说明

在连接的单元格。 *名称*行之所以标为 DirX/A、 DirY/B 和 Type/C 因为这些行可能是扩展或非扩展行。 
  
大多数连接点（通过用户界面创建的所有连接点）都是非扩展的，具有 DirX、DirY 和 Type 单元格。它们的行类型为 **visTagCnnctPt** 或 **visTagCnnctNamed**。
  
在非扩展行中，DirX 和 DirY 单元格共同定义了一个方向向量，该向量会影响到使用连接点进行连接时所涉及到的形状的转动。如果两个单元格皆为零，则该点为无方向。连接点的类型包括：
  
- 向内 (0)，表示形状粘附于它们。这是默认值。
    
- 向外 (1)，表示这些连接点将粘附于向内连接点。
    
- 向内和向外 (2)，在此情况下，方向为向内方向，但是若用作向外连接则方向相反。
    
扩展行有 A、B、C 和 D 单元格，其行为类似“向内”类型的无方向的非扩展行。通常不使用扩展行，但在将数据与 A、B、C 和 D 单元格中的连接点相关联时可能要使用它们。它们的行类型为 **visTagCnnctPtABCD** 或 **visTagCnnctNamedABCD**。如果 D 单元格中存在公式，便可识别这是扩展行。 
  
 您可以添加任意多个连接。  *名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。 若要添加到现有的 Connection points 连接点，右击某一行，然后单击快捷菜单上的**插入行**。 
  
您可以引用 Connection Points 行单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。 若要更改行名称，单击它，，然后键入名称，例如*自定义*，例如，若要创建的行名称 Connections.Custom。 然后，可以引用 X 单元格使用 Connections.Custom.X，例如或 Connections.X1，如果您想要使用的行号。 
  
您输入的行名称在该内容中必须是唯一的。 在连接点部分中创建一个行的名称时，Microsoft Office Visio 使用默认名称，Connections.Row_ *n*姓名部分中的所有行。 
  
命名的 Connection Points 行与 Visio 5.0 之前的版本不兼容。用早期格式保存带有命名的 Connection Points 行的 Visio 绘图文件时，对命名的 Connection Points 行的引用会转换为索引引用，且行名称会丢失。
  

