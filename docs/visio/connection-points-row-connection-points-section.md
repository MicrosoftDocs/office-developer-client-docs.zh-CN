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
description: 包含 x 坐标和 y 坐标、水平和垂直方向以及形状上的单个连接点的类型。 连接点的坐标以形状的原点为基准进行测量。 形状上的每个连接点都包含一个 Connection Points 行。
ms.openlocfilehash: 301ea4fb446d9acafd4b59af388c3e7b2d419e20
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415507"
---
# <a name="connection-points-row-connection-points-section"></a>Connection Points 行（“Connection Points”内容）

包含*x*坐标和*y*坐标、水平和垂直方向以及形状上的单个连接点的类型。 连接点的坐标以形状的原点为基准进行测量。 形状上的每个连接点都包含一个 Connection Points 行。 
  
如果命名了多个 Connection Points 行，则它们的名称将以 Connections. ShapeSheet 窗口中的*名称*。 Connection Points 行包含以下单元格。 有关详细信息，请参阅特定的单元格主题。 
  
|**单元格**|**说明**|
|:-----|:-----|
|[X](x-cell-connection-points-section.md) <br/> |连接点在本地坐标系中的*x*坐标。  <br/> |
|[Y](y-cell-connection-points-section.md) <br/> |连接点在本地坐标系中的*y*坐标。  <br/> |
|[DirX/A](dirxa-cell-connection-points-section.md) <br/> |匹配连接点所需的对齐向量的*x*分量。 它还用于确定动态连接线所附引线的方向。 此单元格采用浮点值。  <br/> |
|[DirY/B](diryb-cell-connection-points-section.md) <br/> |匹配连接点所需的对齐向量的*y*分量。 它还用于确定动态连接线所附引线的方向。 此单元格采用浮点值。  <br/> |
|[Type/C](typec-cell-connection-points-section.md) <br/> |连接点类型（0 = 向内；1 = 向外；2 = 向内 + 向外）。  <br/> |
|[D](d-cell-connection-points-section.md) <br/> |可用于输入或测试公式的草稿单元格。若要访问此单元格，可右击某一行，然后单击快捷菜单上的 **“更改行类型”**。<br/> |
   
## <a name="remarks"></a>说明

Connections. "*名称*" 行标记为 DirX/A、DirY/B 和 Type/C, 因为这些行可以是扩展行, 也可以是非扩展行。 
  
大多数连接点（通过用户界面创建的所有连接点）都是非扩展的，具有 DirX、DirY 和 Type 单元格。它们的行类型为 **visTagCnnctPt** 或 **visTagCnnctNamed**。
  
在非扩展行中，DirX 和 DirY 单元格共同定义了一个方向向量，该向量会影响到使用连接点进行连接时所涉及到的形状的转动。如果两个单元格皆为零，则该点为无方向。连接点的类型包括：
  
- 向内 (0)，表示形状粘附于它们。 这是默认值。
    
- 向外 (1)，表示这些连接点将粘附于向内连接点。
    
- 向内和向外 (2)，在此情况下，方向为向内方向，但是若用作向外连接则方向相反。
    
扩展行有 A、B、C 和 D 单元格，其行为类似“向内”类型的无方向的非扩展行。通常不使用扩展行，但在将数据与 A、B、C 和 D 单元格中的连接点相关联时可能要使用它们。它们的行类型为 **visTagCnnctPtABCD** 或 **visTagCnnctNamedABCD**。如果 D 单元格中存在公式，便可识别这是扩展行。 
  
 可以根据需要添加任意多的 Connections.  根据需要*命名*行, 为行分配有意义的名称, 并设置单元格的值。 若要向现有的 Connection Points 内容添加连接点，请右击某一行，然后单击快捷菜单上的 **“插入行”**。 
  
您可以按行名称引用连接点行单元格, 该名称在 ShapeSheet 窗口中显示为红色文本。 若要更改行名称, 请单击它, 然后键入一个名称 (如*Custom* ) 以创建行名称连接。自定义。 然后, 您可以使用 Connections 引用 x 单元格, 例如, 如果要使用行号, 则为 X1。 
  
您输入的行名称在该内容中必须是唯一的。 当您为 "连接点" 部分中的行创建名称时, Microsoft Office Visio 会将该节中的所有行都命名为默认名称 "Row_ *n* "。 
  
命名的 Connection Points 行与 Visio 5.0 之前的版本不兼容。用早期格式保存带有命名的 Connection Points 行的 Visio 绘图文件时，对命名的 Connection Points 行的引用会转换为索引引用，且行名称会丢失。
  

