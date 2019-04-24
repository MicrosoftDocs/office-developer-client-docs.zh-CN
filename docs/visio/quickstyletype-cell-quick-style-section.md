---
title: QuickStyleType 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7470417-0d70-433e-9496-604ca2eafee6
description: 确定形状继承的快速样式 (二维、1维或连接符) 的类型。
ms.openlocfilehash: 95aced62c6397fc3229de29b98d3f18e5f69d05b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282577"
---
# <a name="quickstyletype-cell-quick-style-section"></a>QuickStyleType 单元格 ("快速样式" 部分)

确定形状继承的快速样式 (二维、1维或连接符) 的类型。 
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |Visio 自动选择  <br/> |
|1  <br/> |一维  <br/> |
|双面  <br/> |二维  <br/> |
|第三章  <br/> |Connector  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**QuickStyleType**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleType  <br/> |
   
若要从某个程序按索引获取对**QuickStyleType**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleType** <br/> |
   

