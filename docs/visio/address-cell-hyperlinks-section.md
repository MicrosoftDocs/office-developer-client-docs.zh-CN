---
title: Address 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251387
localization_priority: Normal
ms.assetid: 3864aadd-3f86-c20e-1a74-b0aaff5106f7
description: 指定要跳转到的 URL 地址、文件名或 UNC 路径。
ms.openlocfilehash: 0fbb89e18a2d7a849e2369c0d41aac4a647f067b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338547"
---
# <a name="address-cell-hyperlinks-section"></a>Address 单元格（“Hyperlinks”内容）

指定要跳转到的 URL 地址、文件名或 UNC 路径。
  
您可以根据在 "**属性**" 对话框 (依次单击 "**文件**" 选项卡、"**信息**"、"属性" 和 "属性") 的 "**摘要**" 选项卡上为文档定义的基准路径, 将地址指定为相对路径。 ****, 然后单击 "**高级属性**")。 如果文档没有基础路径，则应用程序会基于文档路径导航。 如果未保存文档，则超链接尚未定义。
  
## <a name="remarks"></a>注解

您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置 Address 单元格的值。 
  
若要从某个程序按索引获取对 Address 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |超链接。 *名称*。超链接的地址。 *name*是超链接行的名称  <br/> |
   
若要从另一个公式或从使用**CellsU**属性的某个程序按名称获取对 Address 单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visHLinkAddress** <br/> |
   

