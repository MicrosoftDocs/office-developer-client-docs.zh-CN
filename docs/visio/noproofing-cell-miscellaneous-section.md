---
title: NoProofing 单元格 ("杂项" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 668f993c-b4d1-4762-9801-c578b17fdafd
description: 确定是否自动更正拼写, 以及是否显示所选形状的拼写错误。 采用布尔值。
ms.openlocfilehash: 8d7eebcc349c54db3cd48d6c5fa3c8fa6f4f760e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357223"
---
# <a name="noproofing-cell-miscellaneous-section"></a>NoProofing 单元格 ("杂项" 部分)

确定是否自动更正拼写, 以及是否显示所选形状的拼写错误。 采用**布尔**值。 
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |不会自动更正拼写, 并且不会显示所选形状的拼写错误。  <br/> |
|FALSE  <br/> |将自动更正拼写, 并显示所选形状的拼写错误。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式或从某个程序按名称获取对 NoProofing 单元格的引用, 请使用**CellsU**属性, 使用: 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |NoProofing  <br/> |
   
若要从某个程序按索引获取对 NoProofing 单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowMisc** <br/> |
|单元格索引：  <br/> |**visObjNoProofing** <br/> |
   

