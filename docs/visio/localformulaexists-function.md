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
description: 指示是否引用的单元格包含本地公式。
ms.openlocfilehash: 1b749011de8554cb5b777fe92b20a6bcdb2fcb19
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780614"
---
# <a name="localformulaexists-function"></a>LOCALFORMULAEXISTS 函数

指示是否引用的单元格包含本地公式。 
  
## <a name="syntax"></a>语法

LOCALFORMULAEXISTS (* * *cellref* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellref_ <br/> |必需  <br/> |**字符串** <br/> | 要检查其中是否存在公式的单元格。  <br/> |
   
### <a name="return-value"></a>返回值

Boolean
  
## <a name="remarks"></a>注解

如果单元格中包含本地公式，则 LOCALFORMULAEXISTS 函数返回 1；如果没有公式或公式是继承而来的，则返回 0（零）。 
  

