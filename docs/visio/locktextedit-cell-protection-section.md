---
title: LockTextEdit 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm665
localization_priority: Normal
ms.assetid: d8de5fa4-826b-e869-4d9f-997361d05fd8
description: 锁定形状的文本，使它无法编辑。
ms.openlocfilehash: f6e5176e3ab654b76c0641b8f642abcf6b1050dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404496"
---
# <a name="locktextedit-cell-protection-section"></a>LockTextEdit 单元格（“Protection”内容）

锁定形状的文本，使它无法编辑。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |不能编辑文本。  <br/> |
| FALSE  <br/> | 能够编辑文本。  <br/> |
   
## <a name="remarks"></a>备注

您仍然可以通过应用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）中的样式来设置文本的格式。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockTextEdit 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockTextEdit  <br/> |
   
若要从某个程序按索引获取对 LockTextEdit 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockTextEdit** <br/> |
   

