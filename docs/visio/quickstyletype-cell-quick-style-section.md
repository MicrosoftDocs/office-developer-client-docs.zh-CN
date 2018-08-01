---
title: QuickStyleType 单元格（“Quick Style”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7470417-0d70-433e-9496-604ca2eafee6
description: 确定快速样式的类型 (二维、 一维或连接器) 形状继承的。
ms.openlocfilehash: 211074800eee601d2658edbc03bb95d028920e54
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781006"
---
# <a name="quickstyletype-cell-quick-style-section"></a>QuickStyleType 单元格（“Quick Style”部分）

确定快速样式的类型 (二维、 一维或连接器) 形状继承的。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |Visio 自动选择  <br/> |
|1  <br/> |一维  <br/> |
|2  <br/> |二维  <br/> |
|3  <br/> |连接器  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**QuickStyleType**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleType  <br/> |
   
若要从某个程序按索引获取对**QuickStyleType**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleType** <br/> |
   

