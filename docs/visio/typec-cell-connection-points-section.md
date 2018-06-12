---
title: Type / C 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251723
localization_priority: Normal
ms.assetid: 2264d026-2041-3855-2b23-553ce67ae69d
description: 确定连接点类型。
ms.openlocfilehash: 12c953a160ab99aad007e9b2bb9089d651aee553
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781577"
---
# <a name="type--c-cell-connection-points-section"></a>Type / C 单元格（“Connection Points”内容）

确定连接点类型。
  
|**值**|**类型**|**自动化常量**|
|:-----|:-----|:-----|
|0  <br/> |向内  <br/> |**visCnnctTypeInward** <br/> |
|1  <br/> |向外  <br/> |**visCnnctTypeOutward** <br/> |
|2  <br/> |向内&amp;向外  <br/> |**visCnnctTypeInwardOutward** <br/> |
   
## <a name="remarks"></a>备注

您还可以通过选择**连接器**工具，选择一个形状，然后右键单击连接点设置连接点类型。 若要执行此操作，您需要以[开发人员](run-in-developer-mode-display-the-developer-tab.md)模式运行。 
  
若要获取的引用类型 / C 单元格按名称从另一个公式或从程序使用**CellsU**属性，使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Connections.Type [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要获取的引用类型 / C 单元格从某个程序按索引使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionConnectionPts** <br/> |
|行索引：  <br/> |**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCnnctType**（非扩展行）**visCnnctC**（扩展的行）  <br/> |
   
有关扩展行和非扩展行的信息，请参见 Connection Points 行。
  

