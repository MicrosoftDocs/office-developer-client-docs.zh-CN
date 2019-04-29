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
description: 返回一个数字的 ANSI 字符。
ms.openlocfilehash: 6f1c459892331ec30ad93bbc860fcd038e8f4732
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418188"
---
# <a name="char-function"></a>CHAR 函数

返回一个数字的 ANSI 字符。
  
## <a name="syntax"></a>语法

CHAR (* * *number* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要获取其 ANSI 字符的数字。  <br/> |
   
## <a name="remarks"></a>说明

结果字符串的长度为一个字符。 number 参数必须是介于1和255之间的整数 (含这两个_值_), 否则函数将返回错误。 
  
## <a name="example"></a>示例

CHAR (9) 
  
返回制表符。 
  

