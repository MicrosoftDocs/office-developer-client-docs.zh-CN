---
title: 'NoCoauth Cell (Document Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f2095c9-ce09-48f7-b160-c9822d96a96c
description: 设置存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive上的文档是否可以由多个作者在共同创作会话中同时编辑。
ms.openlocfilehash: a76e2d3b2c3cf6e99e37596b016f448b0be56fd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420512"
---
# <a name="nocoauth-cell-document-properties-section"></a>NoCoauth Cell (Document Properties Section) 

设置存储在 Microsoft SharePoint 2013 服务器或 Microsoft OneDrive上的文档是否可以由多个作者在共同创作会话中同时编辑。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |该文档无法共同授权，并且将在打开时锁定进行编辑。  <br/> |
|FALSE  <br/> |文档可以共同授权。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **NoCoauth** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | NoCoauth  <br/> |
   
若要从程序按索引获取对 **NoCoauth** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocNoCoauth** <br/> |
   

