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
description: 返回与 Microsoft Visio 内部文本域格式代码匹配的格式图片字符串。
ms.openlocfilehash: 1ab24c602c7975cf6be22a564a8b9ee9aa0d6f46
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431454"
---
# <a name="fieldpicture-function"></a>FIELDPICTURE 函数

返回与 Microsoft Visio 内部文本域格式代码匹配的格式图片字符串。
  
## <a name="syntax"></a>语法

FIELDPICTURE (* **代码** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _code_ <br/> |必需  <br/> |**Number** <br/> | 文本域格式代码。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>说明

格式图片字符串用于 FORMAT 函数中，可以定义日期、时间、数字和单位标签的扩展值。
  
## <a name="example"></a>示例

FIELDPICTURE (0) 
  
返回格式图片字符串“esc(0)”，当在 FORMAT 函数中使用时，指定了带有一个小数位和小写字母单位说明的数字。 
  

