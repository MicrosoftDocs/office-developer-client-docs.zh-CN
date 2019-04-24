---
title: Relationships 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80005
localization_priority: Normal
ms.assetid: 4168cd98-9674-1233-254f-0afe81b7245b
description: 存储容器、列表、标注和形状之间的关系。
ms.openlocfilehash: b270366fe1045aea3d628150c82e7fd798fa21df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359967"
---
# <a name="relationships-cell-shape-layout-section"></a>Relationships 单元格（“Shape Layout”内容）

存储容器、列表、标注和形状之间的关系。 
  
## <a name="remarks"></a>注解

 Microsoft Visio 使用 "关系" 单元格来存储涉及此形状的关系。 一系列带有所示参数的 DEPENDSON 函数用于表示与该形状的关系，如下表中所示。 
  
|**第一个参数**|**其他参数**|
|:-----|:-----|
|1  <br/> |属于此容器成员的形状。  <br/> |
|双面  <br/> |属于此列表成员的形状。  <br/> |
|第三章  <br/> |与此形状相关的标注。  <br/> |
|4  <br/> |此形状是其成员的容器。  <br/> |
|5  <br/> |此列表项是其成员的列表。  <br/> |
|型  <br/> |与此标注相关的形状。  <br/> |
|步  <br/> |此形状位于其左边界边缘的容器。  <br/> |
|utf-8  <br/> |此形状位于其右边界边缘的容器。  <br/> |
|第  <br/> |此形状位于其上边界边缘的容器。  <br/> |
|10  <br/> |此形状位于其下边界边缘的容器。  <br/> |
|11x17  <br/> |此列表重叠的列表。  <br/> |
   
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Relationships 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |关系  <br/> |
   
若要从某个程序按索引获取对 Relationships 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLORelationships** <br/> |
   

