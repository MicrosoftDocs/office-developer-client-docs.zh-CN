---
title: NoCoauth 单元格 ("Document Properties" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f2095c9-ce09-48f7-b160-c9822d96a96c
description: 设置在合著会话中, 多个作者是否可以同时编辑存储在 microsoft SharePoint 2013 服务器或 microsoft OneDrive 上的文档。
ms.openlocfilehash: a76e2d3b2c3cf6e99e37596b016f448b0be56fd3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319437"
---
# <a name="nocoauth-cell-document-properties-section"></a>NoCoauth 单元格 ("Document Properties" 内容)

设置在合著会话中, 多个作者是否可以同时编辑存储在 microsoft SharePoint 2013 服务器或 microsoft OneDrive 上的文档。
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |文档不能为合著, 在打开时已被锁定, 无法编辑。  <br/> |
|FALSE  <br/> |该文档可以是合著。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**NoCoauth**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | NoCoauth  <br/> |
   
若要从某个程序按索引获取对**NoCoauth**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocNoCoauth** <br/> |
   

