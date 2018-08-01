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
ms.openlocfilehash: 840ce0c4ce73da378f80e5d8a185073ac3915daf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779649"
---
# <a name="address-cell-hyperlinks-section"></a>Address 单元格（“Hyperlinks”部分）

指定要跳转到的 URL 地址、文件名或 UNC 路径。
  
您可以为相对路径基于**属性**对话框的**摘要**选项卡上的**超链接基础**框中为文档定义的基路径指定地址 (单击**文件**选项卡，单击**信息**，单击 * * 属性 * *，然后单击**高级属性**)。 如果文档有无基路径，应用程序导航基于文档路径。 如果文档尚未保存，未定义超链接。
  
## <a name="remarks"></a>说明

您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置 Address 单元格的值。 
  
若要从某个程序按索引获取对 Address 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |超链接。 *名称*。地址位置超链接。 *name*是超链接行的名称  <br/> |
   
若要获取对 Address 单元格的引用按名称从另一个公式或从某个程序中，使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visHLinkAddress** <br/> |
   

