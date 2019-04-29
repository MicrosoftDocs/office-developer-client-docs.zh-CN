---
title: LinePattern 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm560
localization_priority: Normal
ms.assetid: a416762b-7294-c99f-d9f1-332c3ed35dff
description: 确定形状的线型。在 LinePattern 单元格中输入的值是一个数字，此数字是线型集合中的索引。
ms.openlocfilehash: eec5bed18777f7822f9544d59dce7722f2f732bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416753"
---
# <a name="linepattern-cell-line-format-section"></a>LinePattern 单元格（“Line Format”内容）

确定形状的线型。在 LinePattern 单元格中输入的值是一个数字，此数字是线型集合中的索引。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |没有线型  <br/> |
|1  <br/> |实线  <br/> |
|2 - 23  <br/> |各种线型  <br/> |
   
## <a name="remarks"></a>说明

可以在 **“线条”** 对话框中查看线型集合（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“虚线”**，然后单击 **“其他线条”**）。
  
若要指定自定义的线型，请使用本单元格中的 USE 函数。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LinePattern 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LinePattern  <br/> |
   
若要从某个程序按索引获取对 LinePattern 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLinePattern** <br/> |
   

