---
title: FORMULAEXISTS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033806
localization_priority: Normal
ms.assetid: 3d4f82d3-fcd0-536a-c4e1-94c362cde7c4
description: 指示引用的单元格是否包含公式。
ms.openlocfilehash: 1f28d429516d4f8b2357f1c2ab589700e38ff40a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420274"
---
# <a name="formulaexists-function"></a>FORMULAEXISTS 函数

指示引用的单元格是否包含公式。 
  
## <a name="syntax"></a>语法

FORMULAEXISTS (* * *cellref* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellref_ <br/> |必需  <br/> |**String** <br/> |要检查其中是否存在公式的单元格。  <br/> |
   
## <a name="remarks"></a>说明

如果单元格包含公式, 则 FORMULAEXISTS 函数返回 1; 否则返回1。如果它不包含公式, 则返回零 (0)。 
  

