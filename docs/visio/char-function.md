---
title: CHAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251406
localization_priority: Normal
ms.assetid: 0803d5d3-d804-5ffe-604d-661b35d1fc01
description: 返回数字的 ANSI 字符。
ms.openlocfilehash: 209614d20dd663ed2f7ca030c25500d43f925c95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779856"
---
# <a name="char-function"></a>CHAR 函数

返回数字的 ANSI 字符。
  
## <a name="syntax"></a>语法

CHAR (* **数量** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**编号** <br/> |要获取其 ANSI 字符数。  <br/> |
   
## <a name="remarks"></a>备注

结果字符串是一个字符的长度。 _号码_参数必须是介于 1 和 255 之间 （含） 的整数或函数将返回错误。 
  
## <a name="example"></a>示例

CHAR(9) 
  
返回制表符。 
  

