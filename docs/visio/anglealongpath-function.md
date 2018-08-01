---
title: ANGLEALONGPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d7f8ca9a-3a89-abab-9805-bd1e24075c3f
description: 返回给定点上路径的切线角度。
ms.openlocfilehash: ec5529037275fc8661972cc7403886cd33150b38
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779666"
---
# <a name="anglealongpath-function"></a>ANGLEALONGPATH 函数

返回给定点上路径的切线角度。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

ANGLEALONGPATH (* **部分** *，* **差旅** * * * *[、 段]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**字符串** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _出差_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点沿路径的百分比。必须介于 0 到 1 之间。  <br/> |
| _段_ <br/> |可选  <br/> |**Integer** <br/> |计算切线角度所用路径的从 1 开始的线段。  <br/> |
   
### <a name="return-value"></a>返回值

 **Double**
  
## <a name="remarks"></a>注解

如果包含_segment_值，ANGLEALONGPATH 会返回该线段仅的值。 
  
如果包含_segment_值，ANGLEALONGPATH 通过使用_差旅_计算_segment_来确定切线点。
  
如果_section_或_segment_不存在，Microsoft Visio 将返回 #REF ！。 
  

