---
title: FIELDPICTURE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251592
localization_priority: Normal
ms.assetid: df88c55f-c098-dd4c-bf53-c7d7b60cf719
description: 返回格式图片字符串匹配的 Microsoft Visio 内部文本域格式代码。
ms.openlocfilehash: 1528cefd65ed0c7c1dde02fa390babf26442b4d3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780220"
---
# <a name="fieldpicture-function"></a>FIELDPICTURE 函数

返回格式图片字符串匹配的 Microsoft Visio 内部文本域格式代码。
  
## <a name="syntax"></a>语法

FIELDPICTURE (* **代码** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _code_ <br/> |必需  <br/> |**编号** <br/> | 文本域格式代码。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

格式图片字符串用于 FORMAT 函数中，可以定义日期、时间、数字和单位标签的扩展值。
  
## <a name="example"></a>示例

FIELDPICTURE(0) 
  
返回格式图片字符串“esc(0)”，当在 FORMAT 函数中使用时，指定了带有一个小数位和小写字母单位说明的数字。 
  

