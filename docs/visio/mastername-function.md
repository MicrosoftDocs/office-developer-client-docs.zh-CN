---
title: MASTERNAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251581
localization_priority: Normal
ms.assetid: 519d79d4-9178-2231-c26d-aa7f31a43412
description: 返回工作表的主控形状名称为 string，或返回字符串任何主控形状，如果表没有主控形状。
ms.openlocfilehash: c1d5891fba0f967cde4a4e9ca58d07f87239f0b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780702"
---
# <a name="mastername-function"></a>MASTERNAME 函数

返回工作表的主控形状名称为 string，或将返回字符串"\<任何主控形状\>"如果表没有主控形状。
  
## <a name="syntax"></a>语法

MASTERNAME ([* * *langID_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _langID_opt_ <br/> |可选  <br/> |**编号** <br/> |用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>注解

如果传递了非法的语言代码，则将使用本地语言。 
  

