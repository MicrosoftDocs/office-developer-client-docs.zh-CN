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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438034"
---
# <a name="address-cell-hyperlinks-section"></a>Address 单元格（“Hyperlinks”内容）

指定要跳转到的 URL 地址、文件名或 UNC 路径。
  
可以在"属性"对话框的"摘要"选项卡上的"超链接基础"框中为文档定义的基础路径指定 Address 作为相对路径 (单击"文件"选项卡，单击"**信息**"，单击"属性"**，然后单击"高级属性 **) "。**   如果文档没有基础路径，则应用程序会基于文档路径导航。 如果未保存文档，则超链接尚未定义。
  
## <a name="remarks"></a>备注

您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置 Address 单元格的值。 
  
若要从某个程序按索引获取对 Address 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |超链接。 *name*  .地址：Hyperlink。 *name*  是超链接行的名称  <br/> |
   
若要从另一个公式或使用 **CellsU** 属性从程序按名称获取对 Address 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visHLinkAddress** <br/> |
   

