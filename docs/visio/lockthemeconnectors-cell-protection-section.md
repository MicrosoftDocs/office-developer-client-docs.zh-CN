---
title: LockThemeConnectors 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae7ddd55-7bcc-4bb6-bab7-97806122f166
description: 防止 ConnectorsSchemeIndex 行的单元格中主题属性被更改通过应用新主题，或选择新连接器方案。 不阻止用户手动编辑 ShapeSheet 中的此值。
ms.openlocfilehash: c74bcf554f0f14de47480397a96680469826d2c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780647"
---
# <a name="lockthemeconnectors-cell-protection-section"></a>LockThemeConnectors 单元格（“Protection”部分）

防止**ConnectorsSchemeIndex**行的单元格中**主题属性**被更改通过应用新主题，或选择新连接器方案。 不阻止用户手动编辑 ShapeSheet 中的此值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |无法从其当前值更改**ConnectorsSchemeIndex**单元格，除非直接 ShapeSheet 中的更改。  <br/> |
|FALSE  <br/> |可以从其当前值通过 UI 更改**ConnectorsSchemeIndex**单元格。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockThemeConnectors**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockThemeConnectors  <br/> |
   
若要从某个程序按索引获取对**LockThemeConnectors**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockThemeConnectors** <br/> |
   

