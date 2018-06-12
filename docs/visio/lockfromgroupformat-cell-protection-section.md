---
title: LockFromGroupFormat 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: abd175af-ad4e-b84a-2687-2c9358653499
ms.openlocfilehash: 95633ab7a4127564fef65062bcf328d4364ebd86
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780637"
---
# <a name="lockfromgroupformat-cell-protection-section"></a>LockFromGroupFormat 单元格（“Protection”内容）

阻止格式更改向组合形状被传播到及其子形状，同时仍允许用户直接设置所选的子形状的格式。 
  
LockFromGroupFormat 单元格的值对应于**保护**对话框中的**从组格式**复选框设置。 
  
若要引用 LockFromGroupFormat 单元格按名称从另一个公式或从使用**CellsU**属性的某个程序使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LockFromGroupFormat  <br/> |
   
要引用 LockFromGroupFormat 单元格的索引从某个程序，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLock** <br/> |
|单元格索引：  <br/> |**visLockFromGroupFormat** <br/> |
   
该单元格的默认值为 0 (False)。
  

