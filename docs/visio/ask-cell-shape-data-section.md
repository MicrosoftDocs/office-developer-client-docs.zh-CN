---
title: Ask 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60
localization_priority: Normal
ms.assetid: b499a5eb-db8f-ebd0-d505-c9a002205e7d
description: 确定在创建实例或者重复或复制形状时，是否询问用户以输入该形状的形状数据。
ms.openlocfilehash: 0aa270ff918866d8f683a6408ccd71b6a22d555d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426862"
---
# <a name="ask-cell-shape-data-section"></a>Ask 单元格（“Shape Data”内容）

确定在创建实例或者重复或复制形状时，是否询问用户以输入该形状的形状数据。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |要求用户要在 **“定义形状数据”** 对话框中输入形状数据。  <br/> |
|FALSE  <br/> |不询问用户输入数据。  <br/> |
   
## <a name="remarks"></a>备注

此单元格中的值对应于 **“定义形状数据”** 对话框（右键单击形状，指向 **“数据”**，然后单击 **“定义形状数据”**）中的 **“放置时询问”** 复选框。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Ask 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Prop. *name*  .验证 Prop 在何处。  *name*  是自定义属性行的名称。  <br/> |
   
若要从某个程序按索引获取对 Ask 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionProp** <br/> |
|行索引：  <br/> |**visRowProp**  +  *i* 其中 *i* = 0、1、2,...  <br/> |
|单元格索引：  <br/> |**visCustPropsAsk** <br/> |
   

