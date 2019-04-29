---
title: ClippingPath 单元格 ("外部图像信息" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ec70417-5b23-45af-95a0-1b26f6791699
description: 包含对图像所绑定的路径的几何图形的引用。
ms.openlocfilehash: cfbbb3ca7294f751f088df7c3284bf6461270af7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425510"
---
# <a name="clippingpath-cell-foreign-image-info-section"></a>ClippingPath 单元格 ("外部图像信息" 部分)

包含对图像所绑定的路径的几何图形的引用。 
  
## <a name="remarks"></a>说明

如果**ClippingPath**单元格指向有效的路径, 则会对图像进行剪切, 以便在路径中呈现图像。 如果**ClippingPath**单元格为空或包含无效的条目, 则将使用 "缩放" 和 "偏移" 值来呈现图像和矩形剪辑。 
  
> [!NOTE]
> 仅由图像 ShapeSheet 中的 " [Geometry](geometry-section.md) " 内容定义的路径是**ClippingPath**单元格的有效输入项。 跨工作表引用不能用于定义图像剪切路径。 
  
若要从另一个公式按名称获取对**ClippingPath**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ClippingPath  <br/> |
   
若要从某个程序按索引获取对**ClippingPath**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowForeign** <br/> |
| 单元格索引：  <br/> |**visFrgnImgClippingPath** <br/> |
   
## <a name="example"></a>示例

您可以通过执行以下操作, 将图像的边框形状更改为椭圆:
  
- 将图片插入绘图画布上。
    
- 右键单击图片, 然后选择 "**显示 ShapeSheet**"。
    
- 右键单击 ShapeSheet 中的任意位置, 然后选择 "**插入节**"。
    
- 在 "**插入内容**" 对话框中, 选择 "**几何图形**", 然后单击 **"确定"**。
    
- 在 "新建几何图形" 部分 (例如 "Geometry2") 中, 删除除一行之外的所有行。
    
- 右键单击其余的行, 然后单击 "**更改行类型**"。
    
- 在 "**更改行类型**" 对话框中, 选择 "**椭圆形**", 然后单击 **"确定"**。
    
- 在 "**外部图像**" 部分, 将 " **ClippingPath** " 单元格的`="Geometry2.Path"`公式设置为, 然后接受该公式。 
    

