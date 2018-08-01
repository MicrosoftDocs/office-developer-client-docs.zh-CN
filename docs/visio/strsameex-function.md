---
title: STRSAMEEX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251787
localization_priority: Normal
ms.assetid: 056b54ae-1475-9480-6ebc-5c34ef48e0f8
description: 确定两个字符串是否相同。
ms.openlocfilehash: 129c7429fbb3b3e5d09193b8be570045d43a0f0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781458"
---
# <a name="strsameex-function"></a>STRSAMEEX 函数

确定两个字符串是否相同。
  
## <a name="syntax"></a>语法

STRSAMEEX ("* * *string1* * *"，"* * *string2* * *"，* * *localeID* * *，* **标志** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _string1_ <br/> |必需  <br/> |**字符串** <br/> |要比较的第一个字符串。  <br/> |
| _string2_ <br/> |必需  <br/> |**字符串** <br/> | 要比较的第二个字符串。  <br/> |
| _localeID_ <br/> |必需  <br/> |**Numeric** <br/> |区域设置 ID 代码。  <br/> |
| _标志_ <br/> |必需  <br/> |**Numeric** <br/> | 指定比较类型的位。  <br/> |
   
### <a name="return-value"></a>返回值

Boolean
  
## <a name="remarks"></a>说明

如果两个输入字符串相同，则 STRSAMEEX 会返回 TRUE；如果它们不同，则返回 FALSE。使用此函数来比较多字节字符串或使用特定区域设置的大小写规则来进行比较。
			

  
您可以将下列任意标志的组合与 STRSAMEEX 函数一起使用。
  
|**Flag**|**说明**|
|:-----|:-----|
|1  <br/> |忽略大小写。  <br/> |
|2  <br/> |忽略不占位字符。  <br/> |
|4  <br/> |忽略符号。  <br/> |
|4096  <br/> |将标点视为符号。  <br/> |
|65536  <br/> |不区分平假名和片假名字符。  <br/> |
|131072  <br/> |不区分同一字符的单字节字符和双字节字符。  <br/> |
   

