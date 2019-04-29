---
title: 关于单元格引用
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251827
localization_priority: Normal
ms.assetid: e6a9aceb-90d7-fb53-eaf4-416a1ae2a98b
description: 您可以使用 ShapeSheet 单元格引用在公式间创建相互依赖关系。单元格引用使您能根据某一单元格的值计算另一单元格的值。例如，形状的 Width 单元格可能包含通过引用它的 Height 单元格的值来计算该形状的宽度的公式，这样，当用户纵向调整形状的大小时，它的宽度会保持与高度的比例。
ms.openlocfilehash: a92bcc560c535dc012ec5cb79db72250e78364c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409802"
---
# <a name="about-cell-references"></a>关于单元格引用

您可以使用 ShapeSheet 单元格引用在公式间创建相互依赖关系。单元格引用使您能根据某一单元格的值计算另一单元格的值。例如，形状的 Width 单元格可能包含通过引用它的 Height 单元格的值来计算该形状的宽度的公式，这样，当用户纵向调整形状的大小时，它的宽度会保持与高度的比例。
  
在单元格的公式中，可以引用同一形状的单元格或者其他对象（例如文档或页面）的单元格，这样，Microsoft Visio 将根据其他单元格的值为某个单元格计算值。
  
## <a name="what-cell-references-can-include"></a>可包括的单元格引用

单元格引用可以包含形状标识符 (ID) 或名称。 您始终可以使用形状 ID 来指代页面上的任何形状，不论该形状是否已命名。 如果没有为形状命名，则它的默认名称是 Sheet. *i* , 其中*i*是形状 ID。 ID 是在创建形状时分配的，除非您将形状移至其他页面或文档，否则 ID 不会改变。 如果页面上有多个形状同名，则必须包含分配的 ID。 
  
## <a name="cell-reference-syntax-and-examples"></a>单元格引用语法和示例

您使用的语法以及是否能按名称引用形状都取决于两个对象之间的关系。以下通用规则适用：
  
- 如果您编辑一个形状的公式，而某个形状是它的对等形状，则可以按名称引用这个对等形状。如果该对等形状是一个组合，则可以按名称引用该组合，但不能引用它的成员。您也不能按名称引用一个形状的父形状或父形状的对等形状。
    
- 您可以用语法 Sheet.ID 来引用页面上的任何形状，不论该形状是在组合中或者是一个形状的父形状。
    
- 含有非标准字符的名称必须用单引号引起来。非标准名称中的单引号字符前面必须有一个单引号。
    
|**要引用的单元格属于**|**使用此语法**|**示例**|
|:-----|:-----|:-----|
|同一形状  <br/> | CellName  <br/> | Width  <br/> |
| 形状、组合或参考线  <br/> | Shapename!CellName  <br/> | 红星!Angle  <br/> |
| 形状、组合或参考线，其中有多个同级的形状同名  <br/> | Shapename.ID!CellName  <br/> | 2!高度  <br/> |
| 带有已建立索引的行的命名列  <br/> | Section。 Column [index]  <br/> | 字符: 字体 [3]  <br/> |
| 带有已建立索引的行的未命名列  <br/> | 节。 ColumnIndex  <br/> | 暂存. A5  <br/> |
| 任何形状、页面、主控形状或样式  <br/> | Sheet.ID!CellName  <br/> | Sheet. 8!FillForegnd  <br/> |
| 主控形状  <br/> | 主控形状 [MasterName]!SheetName!CellReference  <br/> | 主控形状 [齿轮]!箭!geometry1.path  <br/> |
| 对象所在的页面或主控形状页面  <br/> | ThePage!CellReference  <br/> | ThePage!Vanishing_Point  <br/> |
| 文档中的另一页面  <br/> | 页面 [PageName]!SheetName!CellReference  <br/> | Pages [Page-3]!Sheet 4!BeginX  <br/> |
| 样式  <br/> | Styles!SheetName!CellReference  <br/> | Styles!管理器!LineColor  <br/> |
| 文档  <br/> | TheDoc!CellReference  <br/> | TheDoc!PreviewQuality  <br/> |
| 带有非标准名称的形状、页面、主控形状、文档或样式。  <br/> | "Sheetname"!CellName  <br/> | ' 1-D '!LineColor  <br/> |
   

