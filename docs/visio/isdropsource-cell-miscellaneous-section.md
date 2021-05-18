---
title: IsDropSource 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm490
localization_priority: Normal
ms.assetid: 3b20e6ef-f1ac-5bb0-5ac3-4df3ae5e9bf9
description: 确定是否能通过将一个形状拖放到组合中的方法将形状添加到组合中。
ms.openlocfilehash: e8cb02a66f745530f12c7c8be56b9bdd771121b7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421891"
---
# <a name="isdropsource-cell-miscellaneous-section"></a>IsDropSource 单元格（“Miscellaneous”内容）

确定是否能通过将一个形状拖放到组合中的方法将形状添加到组合中。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |可以通过将一个形状拖放到组合中的方法将形状添加到组合中。  <br/> |
|FALSE  <br/> |不能将形状添加到组合中。  <br/> |
   
## <a name="remarks"></a>备注

您还可以采用以下方法设置此值：选择该形状，在 [“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“放下时将形状添加到组合”** 复选框。 
  
除了要为形状启用此行为，您还必须让组合可以接受拖入其中的形状。为此，请选择该组合，在 [“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“接受放下的形状”** 复选框。此值将存储在“Group Properties”内容的 IsDropTarget 单元格中。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 IsDropSource 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |IsDropSource  <br/> |
   
若要从某个程序按索引获取对 IsDropSource 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowMisc** <br/> |
|单元格索引：  <br/> |**visDropSource** <br/> |
   

