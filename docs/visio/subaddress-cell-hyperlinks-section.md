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
ms.openlocfilehash: 092a53bd7c9d5adb77ed35f3e2ef53888bd6ebea
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349320"
---
# <a name="subaddress-cell-hyperlinks-section"></a>SubAddress 单元格（“Hyperlinks”内容）

指定要链接到的目标文档内的位置。
  
## <a name="remarks"></a>注解

例如, 如果 Address 单元格是 "Drawing1", 则子地址单元格可以指定页面名称, 例如 "page-3"。 如果 Address 单元格是 Microsoft Excel 文件 "Samples", 则该单元格的值可以是工作表或工作表中的区域, 例如 "工作表函数" 或 "Sheet1!A1: D10 "。 如果 Address 单元格为 "https://www.microsoft.com/office/", 则该单元格的值可以是文档中的命名锚点, 如 "解决方案"。
  
您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上的 **“链接”** 组中，单击 **“超链接”**）中设置此单元格的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SubAddress 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 超链接。  *名称*。"子地址", 其中 "超级链接" *。 name*为行名称  <br/> |
   
若要从某个程序按索引获取对子**地址**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visHLinkSubAddress** <br/> |
   

