---
title: NAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251580
localization_priority: Normal
ms.assetid: 1ca67a09-9df2-37f5-b269-e761d76bb011
description: 作为字符串返回工作表的名称。
ms.openlocfilehash: 0d3a70573177d8e16a16972d0a08245381b209dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780783"
---
# <a name="name-function"></a>NAME 函数

作为字符串返回工作表的名称。
  
## <a name="syntax"></a>语法

名称 (* * *langID_opt* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _langID_opt_ <br/> |可选  <br/> |**编号** <br/> |用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

如果传递了非法的语言代码，则将使用本地语言。 
  

