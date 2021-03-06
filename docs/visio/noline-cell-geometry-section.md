---
title: NoLine 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm715
localization_priority: Normal
ms.assetid: f9624af2-c087-3dde-9140-339c438b3652
description: 确定是否围绕路径的边界来绘制线条。
ms.openlocfilehash: ad3744ae8deb4ffb4dd2282e50590439c4b218a4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433750"
---
# <a name="noline-cell-geometry-section"></a>NoLine 单元格（“Geometry”内容）

确定是否围绕路径的边界来绘制线条。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不围绕路径的边界绘制线条，该路径是填充区域的边界。  <br/> |
| FALSE  <br/> | 围绕路径的边界绘制线条。  <br/> |
   
## <a name="remarks"></a>备注

在您将线条的颜色改为白色后，尽管在白色的背景下看不到它，但该线条仍然是存在的。如果将此单元格的值设置为 TRUE，则不绘制任何线条。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoLine 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry  *i*  .NoLine，其中  *i*  = <1>、2、3...  <br/> |
   
要从某个程序按索引获取对 NoLine 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 行索引：  <br/> |**visRowComponent** <br/> |
| 单元格索引：  <br/> |**visCompNoLine** <br/> |
   

