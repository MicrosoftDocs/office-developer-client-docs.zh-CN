---
title: Description 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm230
localization_priority: Normal
ms.assetid: 2f571c65-6b7a-5a3a-c075-3c52d3ab989b
description: 代表超链接的说明性文本字符串。
ms.openlocfilehash: b58e6dc3ec2fc3b64db00e0f19e0718fe897aaa3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396622"
---
# <a name="description-cell-hyperlinks-section"></a>Description 单元格（“Hyperlinks”部分）

代表超链接的说明性文本字符串。 
  
## <a name="remarks"></a>注解

此单元格用于存储有关超链接; 注释例如，"我们定价网站链接。"
  
您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置此单元格的值。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Description 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 超链接。  *名称*。说明其中超链接。  *Name*是超链接行的名称  <br/> |
   
要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visHLinkDescription** <br/> |
   

