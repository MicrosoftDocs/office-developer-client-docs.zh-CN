---
title: PaperKind 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60067
localization_priority: Normal
ms.assetid: b2c9616f-a144-eb99-54b6-b53745c7b4d6
description: 指定打印绘图页的纸张类型。
ms.openlocfilehash: 694aa1fb8b52f5ae323c47e9aab8715b4a48dfb0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408444"
---
# <a name="paperkind-cell-print-properties-section"></a>PaperKind 单元格（“Print Properties”内容）

指定打印绘图页的纸张类型。
  
## <a name="remarks"></a>备注

此设置对应于"打印设置"对话框中的"纸张大小"设置 ("设计"选项卡上，单击"页面设置"箭头，然后在"打印设置"选项卡上单击"设置"按钮) 。    
  
此单元格中的数值映射到以 DMPAPER (为前缀) Microsoft Windows wingdi.h 文件中定义的常量。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PaperKind 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PaperKind  <br/> |
   
若要从某个程序按索引获取对 PaperKind 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPrintProperties** <br/> |
|单元格索引：  <br/> |**visPrintPropertiesPaperKind** <br/> |
   

