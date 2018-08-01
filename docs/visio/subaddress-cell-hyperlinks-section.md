---
title: SubAddress 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm985
localization_priority: Normal
ms.assetid: 949448fd-0f85-b56a-945e-1da0e48609e8
description: 指定要链接到的目标文档内的位置。
ms.openlocfilehash: 0509b9b6a708924b5aeb69f16f3f4cd99573cc0c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781464"
---
# <a name="subaddress-cell-hyperlinks-section"></a>SubAddress 单元格（“Hyperlinks”部分）

指定要链接到的目标文档内的位置。
  
## <a name="remarks"></a>注解

例如，如果 Address 单元格，"Drawing1.vsdx"SubAddress 单元格可以指定一个页面名称，例如"第 3 页"。 如果 Address 单元格，Microsoft Excel 文件"Samples.xlsx"此单元格值可以是工作表或工作表，如"工作表函数"或"Sheet1 中范围 ！A1: D10"。 Address 单元格是否"http://www.microsoft.com/office/"，此单元格的值可以是在文档中，例如"解决方案"命名的定位。
  
您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上的 **“链接”** 组中，单击 **“超链接”**）中设置此单元格的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SubAddress 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 超链接。  *名称*。SubAddress 其中超链接 *.name*是行名称  <br/> |
   
若要从某个程序按索引获取对**SubAddress**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visHLinkSubAddress** <br/> |
   

