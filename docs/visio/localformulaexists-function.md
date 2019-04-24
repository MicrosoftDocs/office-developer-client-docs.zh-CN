---
title: LOCALFORMULAEXISTS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60105
localization_priority: Normal
ms.assetid: 2b757c8d-7732-0f9b-c836-ef755dd1c673
description: 指示引用的单元格是否包含局部公式。
ms.openlocfilehash: bd0a5dafecf1bd8dca1567392d880ecaaa3e0374
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344462"
---
# <a name="localformulaexists-function"></a>LOCALFORMULAEXISTS 函数

指示引用的单元格是否包含局部公式。 
  
## <a name="syntax"></a>语法

LOCALFORMULAEXISTS (* * *cellref* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellref_ <br/> |必需  <br/> |**String** <br/> | 要检查其中是否存在公式的单元格。  <br/> |
   
### <a name="return-value"></a>返回值

布尔值
  
## <a name="remarks"></a>注解

如果单元格中包含本地公式，则 LOCALFORMULAEXISTS 函数返回 1；如果没有公式或公式是继承而来的，则返回 0（零）。 
  

