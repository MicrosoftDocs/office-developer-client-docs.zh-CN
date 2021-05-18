---
title: DisplayLevel 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80001
localization_priority: Normal
ms.assetid: 08b730c4-5dd8-106e-ddf3-da2c942e2ef6
description: 确定形状的显示级别分隔条（Z 顺序分组的相对范围）。
ms.openlocfilehash: 4f7e3fcb2d28f8c4c0706502c66444c121ae6ee6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408143"
---
# <a name="displaylevel-cell-shape-layout-section"></a>DisplayLevel 单元格（“Shape Layout”内容）

确定形状的显示级别分隔条（Z 顺序分组的相对范围）。
  
## <a name="remarks"></a>备注

Z 顺序是形状在绘图页上的显示顺序。当一个形状与另一个形状重叠时，Z 顺序较高的形状显示在 Z 顺序较低的形状之前。 
  
显示级别将形状分为不同的组或分隔条。和下层分隔条中的形状相比，给定分隔条中所有形状的 Z 顺序都较高。默认情况下，大多数形状的显示级别为零 (0)。
  
显示级别的范围从 -32,767 到 +32,767。具有相同显示级别的形状组合为一个分隔条，这些形状在该分隔条内仍根据 Z 顺序彼此分级。
  
可以使用命令"前移"、"向后发送"、"**前** 移"和"发送到后退"来更改带内形状的 Z **顺序**。 如果这些命令将形状从给定带区中移开，Microsoft Visio 将在形状的 DisplayLevel 单元格中显示保留值 -32768，除非该单元格受到保护。 在这种情况下，无法将形状移动到其他带区，并且Visio警告"形状保护和/或图层属性阻止完全执行此命令"。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DisplayLevel 单元格的引用，请使用以下内容。 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |DisplayLevel  <br/> |
   
若要从某个程序按索引获取对 DisplayLevel 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLODisplayLevel** <br/> |
   

