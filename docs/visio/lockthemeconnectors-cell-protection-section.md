---
title: LockThemeConnectors 单元格 ("Protection" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae7ddd55-7bcc-4bb6-bab7-97806122f166
description: 通过应用新主题或选择新的连接器方案, 防止主题属性行中的 ConnectorsSchemeIndex 单元格被更改。 不会阻止用户在 ShapeSheet 中手动编辑此值。
ms.openlocfilehash: 8097e50646fd59f4ac0212cbe9ca2ecfaadab7a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438405"
---
# <a name="lockthemeconnectors-cell-protection-section"></a>LockThemeConnectors 单元格 ("Protection" 部分)

通过应用新主题或选择新的连接器方案, 防止**主题属性**行中的**ConnectorsSchemeIndex**单元格被更改。 不会阻止用户在 ShapeSheet 中手动编辑此值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |除非直接在 ShapeSheet 中进行更改, 否则无法更改**ConnectorsSchemeIndex**单元格的当前值。  <br/> |
|FALSE  <br/> |可以通过 UI 更改**ConnectorsSchemeIndex**单元格的当前值。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**LockThemeConnectors**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockThemeConnectors  <br/> |
   
若要从某个程序按索引获取对**LockThemeConnectors**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockThemeConnectors** <br/> |
   

