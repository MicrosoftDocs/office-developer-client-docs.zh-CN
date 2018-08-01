---
title: ClippingPath 单元格（“Foreign Image Info”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ec70417-5b23-45af-95a0-1b26f6791699
description: 包含引用的绑定图像的路径。
ms.openlocfilehash: 9f1c159e303c1d7bc3467c36756a422a3f325c7b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779877"
---
# <a name="clippingpath-cell-foreign-image-info-section"></a>ClippingPath 单元格（“Foreign Image Info”部分）

包含引用的绑定图像的路径。 
  
## <a name="remarks"></a>说明

如果**ClippingPath**单元格指向的有效路径，则剪裁图像，以便在路径呈现图像。 如果**ClippingPath**单元格为空或包含无效输入，然后将矩形剪辑，使用范围和偏移值呈现图像。 
  
> [!NOTE]
> 仅由[geometry](geometry-section.md)内容的图像的 ShapeSheet 中定义的路径是**ClippingPath**单元格的有效条目。 跨工作表引用不能用于定义图像剪辑路径。 
  
要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ClippingPath**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ClippingPath  <br/> |
   
若要从某个程序按索引获取对**ClippingPath**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowForeign** <br/> |
| 单元格索引：  <br/> |**visFrgnImgClippingPath** <br/> |
   
## <a name="example"></a>示例

可以通过执行以下操作来更改为一个椭圆图像的边框形状的：
  
- 插入到绘图画布上的图片。
    
- 右键单击该图片，然后选择**显示 ShapeSheet**。
    
- ShapeSheet 中的任意位置单击右键，然后选择**插入节**。
    
- **插入节**对话框中，选择**geometry** ，然后单击**确定**。
    
- 在新的 geometry 内容 (例如"Geometry2") 中，删除所有但一个行。
    
- 右键单击的剩余行，然后单击**更改行类型**。
    
- **更改行类型**对话框中，选择**椭圆**，然后单击**确定**。
    
- 在**Foreign Image**部分中，将设置为**ClippingPath**单元格的公式`="Geometry2.Path"`，然后接受公式。 
    

