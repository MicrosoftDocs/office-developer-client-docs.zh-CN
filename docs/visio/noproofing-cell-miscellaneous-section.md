---
title: 'NoProofing Cell (Miscellaneous Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 668f993c-b4d1-4762-9801-c578b17fdafd
description: 确定是否自动更正拼写以及是否显示选定形状的拼写错误。 接受一个布尔值。
ms.openlocfilehash: 8d7eebcc349c54db3cd48d6c5fa3c8fa6f4f760e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431251"
---
# <a name="noproofing-cell-miscellaneous-section"></a>NoProofing Cell (Miscellaneous Section) 

确定是否自动更正拼写以及是否显示选定形状的拼写错误。 接受 **一个布尔** 值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |不会自动更正拼写，并且不会为选定的形状显示拼写错误。  <br/> |
|FALSE  <br/> |自动更正拼写，并显示选定形状的拼写错误。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式或程序按名称获取对 NoProofing 单元格的引用，请使用 **CellsU** 属性： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |NoProofing  <br/> |
   
若要从程序按索引获取对 NoProofing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowMisc** <br/> |
|单元格索引：  <br/> |**visObjNoProofing** <br/> |
   

