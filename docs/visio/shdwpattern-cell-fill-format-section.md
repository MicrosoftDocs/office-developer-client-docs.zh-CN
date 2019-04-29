---
title: ShdwPattern 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm935
localization_priority: Normal
ms.assetid: eca73b80-9835-9011-1dce-187ccee92e76
description: 确定某一形状的阴影的填充图案。
ms.openlocfilehash: c2591fbc9f208b1bf9c7d0c85e6de765cd9825f6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427610"
---
# <a name="shdwpattern-cell-fill-format-section"></a>ShdwPattern 单元格（“Fill Format”内容）

确定某一形状的阴影的填充图案。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |无（透明填充）  <br/> |
|1  <br/> |前景纯色  <br/> |
|2 - 40  <br/> |各种类型的图案  <br/> |
   
## <a name="remarks"></a>说明

若要设置填充图案，请输入一个介于 0 和 40 之间的数字，该数字是图案集合中的索引。您可以在 **“填充”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“填充”**，然后单击 **“填充选项”**）中查看填充图案集合。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwPattern 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShdwPattern  <br/> |
   
若要从某个程序按索引获取对 ShdwPattern 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillShdwPattern** <br/> |
   

