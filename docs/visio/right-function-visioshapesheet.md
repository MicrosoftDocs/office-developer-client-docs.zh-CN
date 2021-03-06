---
title: RIGHT 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027314
localization_priority: Normal
ms.assetid: 910f0297-d588-2048-f308-03f3c2389bba
description: 根据指定的字符数，返回文本字符串中的最后一个或多个字符。
ms.openlocfilehash: faf14ef55b34e51bac11129d6857e381d07357c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411454"
---
# <a name="right-function-visioshapesheet"></a>RIGHT 函数 (VisioShapeSheet)

根据指定的字符数，返回文本字符串中的最后一个或多个字符。
  
## <a name="syntax"></a>语法

RIGHT (** *text* ** [， ** *num_chars_opt* ** ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**String** <br/> | 包含要提取的字符的文本字符串。  <br/> |
| _num_chars_opt_ <br/> |可选  <br/> |**Number** <br/> |要提取的字符数。默认值为 1。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

0  _num_chars_opt_ 的值必须大于或等于零 (0) 。 
  
如果  _num_chars_opt_ 文本的长度，RIGHT 将返回所有文本。 如果  _num_chars_opt，_ 则假定其为 1。 
  
## <a name="example"></a>示例

RIGHT ("January 1, 2004", 4) 
  
返回值 2004。 
  

