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
ms.openlocfilehash: f1dedf210dfe0dd8cac3d36fdec03fb497f6572c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780839"
---
# <a name="papersource-cell-printproperties-section"></a>PaperSource 单元格（“PrintProperties”部分）

确定页面的纸张来源。 
  
## <a name="remarks"></a>注解

此设置对应于 **“打印设置”** 对话框中的 **“纸张来源”** 设置（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后在 **“打印设置”** 选项卡上单击 **“设置”**）。
  
此单元格映射到常数 （前缀为 dmbin） 中定义为 Microsoft Windows wingdi.h 文件; 中的数字值例如，值 7 代表 DMBIN_AUTO。 
  
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
   

