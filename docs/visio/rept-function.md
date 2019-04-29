---
title: REPT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027335
localization_priority: Normal
ms.assetid: 53362a32-ac27-42a3-ace1-c6184ab20b52
description: 按照给定的次数重复显示文本。
ms.openlocfilehash: 84e7167fcee426c607e6967aff0530362685dd35
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412077"
---
# <a name="rept-function"></a>REPT 函数

按照给定的次数重复显示文本。 
  
## <a name="syntax"></a>语法

REPT (* * *text* * *, * * *number_times* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**String** <br/> | 要重复的文本。  <br/> |
| _number_times_ <br/> |必需  <br/> |**Number** <br/> |指定文本重复次数的正数。  <br/> |
   
## <a name="remarks"></a>说明

如果*number_times*为: 
  
- 为零 (0)，REPT 将返回“”（空文本）。
    
- 不是整数，将被截断。
    
## <a name="example"></a>示例

REPT ("\*", 5) 
  
\* \*返回\*。 \* \* 
  

