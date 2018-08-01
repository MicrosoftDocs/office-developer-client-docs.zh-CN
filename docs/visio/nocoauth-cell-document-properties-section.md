---
title: NoCoauth 单元格（“Document Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f2095c9-ce09-48f7-b160-c9822d96a96c
description: 设置是否文档存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive 可以编辑多个作者同时共同创作的会话中。
ms.openlocfilehash: a20c3a5aa1392e0e6c3bef124f536b91b9642f47
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780794"
---
# <a name="nocoauth-cell-document-properties-section"></a>NoCoauth 单元格（“Document Properties”部分）

设置是否文档存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive 可以编辑多个作者同时共同创作的会话中。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |文档无法合著，并且锁定以进行编辑时打开。  <br/> |
|FALSE  <br/> |可以合著文档。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**NoCoauth**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | NoCoauth  <br/> |
   
若要从某个程序按索引获取对**NoCoauth**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocNoCoauth** <br/> |
   

