---
title: D 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm205
localization_priority: Normal
ms.assetid: 28b18e8d-fecf-a798-813e-c1a310002244
description: 可用于输入或测试公式的草稿单元格。
ms.openlocfilehash: e7bd61b8bc7a1a3b765af738681d958e2c83ba05
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408171"
---
# <a name="d-cell-connection-points-section"></a>D 单元格（“Connection Points”内容）

一种草稿单元格，可用于输入或测试公式。
  
## <a name="remarks"></a>说明

若要访问 D 单元格，可右击一行，然后单击快捷菜单上的 **“更改行类型”**。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 D 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 连接. D [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 D 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionConnectionPts** <br/> |
| 行索引：  <br/> |**visRowConnectionPts** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCnnctD** <br/> |
   

