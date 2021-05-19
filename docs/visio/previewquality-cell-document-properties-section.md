---
title: PreviewQuality 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm815
localization_priority: Normal
ms.assetid: b7d90666-a1bb-f0de-32da-b2855977f648
description: 确定是以草稿质量显示绘图预览还是以详细视图显示绘图预览。
ms.openlocfilehash: 9db2d3e1eb829bfd2ad787fcfc94cd9ba5abaf9e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416816"
---
# <a name="previewquality-cell-document-properties-section"></a>PreviewQuality 单元格（“Document Properties”内容）

确定是以草稿质量显示绘图预览还是以详细视图显示绘图预览。
  
|**值**|**预览质量**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | Draft  <br/> |**visDocPreviewQualityDraft** <br/> |
| 1  <br/> | 详细  <br/> |**visDocPreviewQualityDetailed** <br/> |
   
## <a name="remarks"></a>备注

您还可以在"属性"对话框的"摘要"选项卡上设置此值 (单击 **"Office"** 按钮，单击"信息"选项卡，单击"文档属性"，然后单击"高级属性) "。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PreviewQuality 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PreviewQuality  <br/> |
   
若要从某个程序按索引获取对 PreviewQuality 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocPreviewQuality** <br/> |
   

