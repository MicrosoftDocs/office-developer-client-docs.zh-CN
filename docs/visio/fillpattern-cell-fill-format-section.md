---
title: FillPattern 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm375
localization_priority: Normal
ms.assetid: dac82a4f-4508-541a-e118-7d79df987232
description: 确定形状的填充图案。要指定自定义的填充图案，请使用本单元格中的 USE 函数。
ms.openlocfilehash: 26429e06ad432eaf7fae9188ac676cb4be3201c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780257"
---
# <a name="fillpattern-cell-fill-format-section"></a>FillPattern 单元格（“Fill Format”部分）

确定形状的填充图案。要指定自定义的填充图案，请使用本单元格中的 USE 函数。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |无（透明填充）。  <br/> |
|1  <br/> |前景纯色。  <br/> |
|2-40  <br/> |各种类型的填充图案，与 **“填充”** 对话框中的索引项相对应。  <br/> |
   
## <a name="remarks"></a>说明

您还可以使用 **“填充”** 对话框设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“填充”**，然后单击 **“填充选项”**）。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 FillPattern 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |FillPattern  <br/> |
   
若要从某个程序按索引获取对 FillPattern 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillPattern** <br/> |
   

