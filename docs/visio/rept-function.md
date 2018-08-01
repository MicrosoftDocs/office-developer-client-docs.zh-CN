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
description: 将文本重复给定的次数。
ms.openlocfilehash: 761f2f95824d5bdab4995b2867bfeac6be64bc12
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781120"
---
# <a name="rept-function"></a>REPT 函数

将文本重复给定的次数。 
  
## <a name="syntax"></a>语法

REPT (* **文本** *，* * *number_times* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**字符串** <br/> | 要重复的文本。  <br/> |
| _number_times_ <br/> |必需  <br/> |**编号** <br/> |指定文本重复次数的正数。  <br/> |
   
## <a name="remarks"></a>注解

如果*number_times:* 
  
- 为零 (0)，REPT 将返回“”（空文本）。
    
- 不是整数，将被截断。
    
## <a name="example"></a>示例

REPT ("\*"，5) 
  
返回\* \* \* \* \*。 
  

