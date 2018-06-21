---
title: NoProofing 单元格 （miscellaneous 内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 668f993c-b4d1-4762-9801-c578b17fdafd
description: 确定是否会自动更正拼写检查和拼写错误是否显示所选形状。 采用一个布尔值。
ms.openlocfilehash: 6c27e6740b547af83058519de8edd38fc3522b32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19780793"
---
# <a name="noproofing-cell-miscellaneous-section"></a>NoProofing 单元格 （miscellaneous 内容）

确定是否会自动更正拼写检查和拼写错误是否显示所选形状。 采用一个**布尔**值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |不自动更正拼写检查和拼写错误不显示所选形状。  <br/> |
|FALSE  <br/> |自动更正拼写检查和拼写错误显示为所选形状。  <br/> |
   
## <a name="remarks"></a>注解

若要获取 NoProofing 单元格的引用名称从另一个公式或从某个程序中，使用**CellsU**属性，使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |NoProofing  <br/> |
   
若要从某个程序按索引获取对 NoProofing 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowMisc** <br/> |
|单元格索引：  <br/> |**visObjNoProofing** <br/> |
   

