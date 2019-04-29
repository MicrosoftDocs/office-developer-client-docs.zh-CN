---
title: Value 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1095
localization_priority: Normal
ms.assetid: 3ca662c8-1ce4-89a9-3264-1ba533fcd444
description: 包含域的函数。
ms.openlocfilehash: d5a09dd0d59341125db897484f74addff22328de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430943"
---
# <a name="value-cell-text-fields-section"></a>Value 单元格（“Text Fields”内容）

包含域的函数。
  
## <a name="remarks"></a>说明

您可以使用 **“域”** 对话框（在 **“插入”** 选项卡上的 **“文本”** 组中单击 **“域”**）设置此单元格的值。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Value 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Fields 值 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionTextField** <br/> |
|行索引：  <br/> |**visRowField** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visFieldCell** <br/> |
   

