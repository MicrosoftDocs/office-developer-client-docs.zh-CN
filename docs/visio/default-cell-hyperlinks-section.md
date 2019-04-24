---
title: Default 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251545
localization_priority: Normal
ms.assetid: 0edea0ea-58dd-15da-6d4f-185d40133452
description: 确定形状或页的默认超链接。将此单元格的值设置为 TRUE 可以将一个超链接设置为默认超链接。
ms.openlocfilehash: 9991bd0e241c5dfd4fda65aeff8b6cc203ad3458
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360275"
---
# <a name="default-cell-hyperlinks-section"></a>Default 单元格（“Hyperlinks”内容）

确定形状或页的默认超链接。将此单元格的值设置为 TRUE 可以将一个超链接设置为默认超链接。
  
## <a name="remarks"></a>注解

您还可以使用以下方法设置默认超链接：选择一个形状，在 **“插入”** 选项卡上单击 **“超链接”**，选择一个超链接，然后单击 **“默认值”**。默认的超链接以粗体文本显示。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Default 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |超链接。 *名称*。超链接的默认位置。 *名称*是行名称  <br/> |
   
若要从某个程序按索引获取对 Default 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionHyperlink** <br/> |
|行索引：  <br/> |**visRow1stHyperlink** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visHLinkDefault** <br/> |
   

