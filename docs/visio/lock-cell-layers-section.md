---
title: Lock 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm590
localization_priority: Normal
ms.assetid: 47bb268f-acdd-7369-716c-bd51a32b8a49
description: 指定是否锁定属于该图层的形状，以免选取或编辑这些形状。
ms.openlocfilehash: d548a6f0fe0cac10d80d73c904739b2979ecf27f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438825"
---
# <a name="lock-cell-layers-section"></a>Lock 单元格（“Layers”内容）

指定是否锁定属于该图层的形状，以免选取或编辑这些形状。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |锁定形状。  <br/> |
|FALSE  <br/> |不锁定形状。  <br/> |
   
## <a name="remarks"></a>说明

还可以通过在 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中选择 **“锁定”** 来设置此值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Lock 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |"层"。已锁定 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Lock 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visLayerLock** <br/> |
   

