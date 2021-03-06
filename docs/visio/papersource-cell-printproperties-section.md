---
title: PaperSource 单元格（“PrintProperties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60068
localization_priority: Normal
ms.assetid: 771a2ab4-578d-51c3-fabd-138f7952bb11
description: 确定页面的纸张来源。
ms.openlocfilehash: eb6e7daccb1743c43a30b34598e47187496e4aac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406757"
---
# <a name="papersource-cell-printproperties-section"></a>PaperSource 单元格（“PrintProperties”内容）

确定页面的纸张来源。 
  
## <a name="remarks"></a>备注

此设置对应于 **“打印设置”** 对话框中的 **“纸张来源”** 设置（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后在 **“打印设置”** 选项卡上单击 **“设置”**）。
  
此单元格中的数值映射到以 DMBIN (为前缀的常量) Microsoft Windows wingdi.h 文件中定义的 bin 选择;例如，值 7 表示DMBIN_AUTO。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PaperSource 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PaperSource  <br/> |
   
若要从某个程序按索引获取对 PaperSource 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPrintProperties** <br/> |
|单元格索引：  <br/> |**visPrintPropertiesPaperSource** <br/> |
   

