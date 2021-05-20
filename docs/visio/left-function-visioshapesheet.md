---
title: LEFT 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1021757
localization_priority: Normal
ms.assetid: 0c2f6e06-b772-2006-ec7b-8695d097f146
description: 根据指定的字符数，返回文本字符串中最左侧的字符。
ms.openlocfilehash: aa4141cfc53bd41a6d58e8bc666b18a06fc80245
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427519"
---
# <a name="left-function-visioshapesheet"></a>LEFT 函数 (VisioShapeSheet)

根据指定的字符数，返回文本字符串中最左侧的字符。
  
## <a name="syntax"></a>语法

LEFT (** *text* **， [， ** *num_chars_opt* ** ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**String** <br/> |包含要提取的字符的文本字符串。  <br/> |
| _num_chars_opt_ <br/> |可选  <br/> |**Numeric** <br/> |要提取的字符数。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

0  _num_chars_opt_ 的值必须大于或等于零 (0) 。 
  
如果  _num_chars_opt_ 文本的长度，LEFT 将返回所有文本。 如果  _num_chars_opt，_ 则假定其为 1。 
  
## <a name="example"></a>示例

LEFT ("January 1, 2004", 3) 
  
返回值“Jan”。 
  

