---
title: ANGLEALONGPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d7f8ca9a-3a89-abab-9805-bd1e24075c3f
description: 返回给定点上路径的切线角度。
ms.openlocfilehash: 0d38fc0e123a7e38b7826b55415cfc09c1789c0e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407324"
---
# <a name="anglealongpath-function"></a>ANGLEALONGPATH 函数

返回给定点上路径的切线角度。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

ANGLEALONGPATH (* * *section* * *, * **差旅** * * * *[, segment]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**String** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _传输_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点沿路径的百分比。 必须介于 0 到 1 之间。  <br/> |
| _段落_ <br/> |可选  <br/> |**Integer** <br/> |计算切线角度所用路径的从 1 开始的线段。  <br/> |
   
### <a name="return-value"></a>返回值

 **Double**
  
## <a name="remarks"></a>备注

如果包含_分段_值, 则 ANGLEALONGPATH 仅返回该线段的值。 
  
如果包含_线段_值, ANGLEALONGPATH 将通过使用_行进_沿_线段_计算 percertage 来确定切线的点。
  
如果_一节或一__段_不存在, Microsoft Visio 将返回 #REF!。 
  

