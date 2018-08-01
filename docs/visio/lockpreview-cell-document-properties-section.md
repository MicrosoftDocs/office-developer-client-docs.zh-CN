---
title: LockPreview 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251742
localization_priority: Normal
ms.assetid: 5a2bb1a7-e688-d32f-f231-ac6916d838a6
description: 确定每次保存绘图时是否保存预览。
ms.openlocfilehash: 2ef5ea12669a7a6a2b37d599afd24635f7509ac2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780634"
---
# <a name="lockpreview-cell-document-properties-section"></a>LockPreview 单元格（“Document Properties”部分）

确定每次保存绘图时是否保存预览。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 每次保存绘图时不保存预览。  <br/> |
| FALSE  <br/> | 每次保存绘图时保存预览。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockPreview 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockPreview  <br/> |
   
要从某个程序按索引获取对 LockPreview 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocLockPreview** <br/> |
   

