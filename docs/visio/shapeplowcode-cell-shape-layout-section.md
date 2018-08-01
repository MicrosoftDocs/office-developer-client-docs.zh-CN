---
title: ShapePlowCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm900
localization_priority: Normal
ms.assetid: acf07fd7-6aa6-1a92-9b7a-bd6fea8a7cb2
description: 确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。
ms.openlocfilehash: 5917abad653e7aaf40da05eafa3f9f1a90a2cf9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781284"
---
# <a name="shapeplowcode-cell-shape-layout-section"></a>ShapePlowCode 单元格（“Shape Layout”部分）

确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |按页上指定绘制。  <br/> |**visSLOPlowDefault** <br/> |
|1  <br/> |不绘制任何形状。  <br/> |**visSLOPlowNever** <br/> |
|2  <br/> |绘制每一个形状。  <br/> |**visSLOPlowAlways** <br/> |
   
## <a name="remarks"></a>说明

您还可以在**行为**对话框中的**位置**选项卡上设置为特定形状此单元格的值 (与选定形状，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡的**形状设计**组中，单击**行为**，然后单击**位置**选项卡）。 
  
若要在绘图页上设置此行为*所有*形状，请用页面布局部分中的 PlowCode 单元格。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePlowCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePlowCode  <br/> |
   
若要从某个程序按索引获取对 ShapePlowCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPlowCode** <br/> |
   

