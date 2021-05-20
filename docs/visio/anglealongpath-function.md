---
title: ANGLEALONGPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d7f8ca9a-3a89-abab-9805-bd1e24075c3f
description: 返回给定点上路径的切线角度。
ms.openlocfilehash: a15e45ff6135972cd1cd78382147a493f8fc8d69
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160291"
---
# <a name="anglealongpath-function"></a>ANGLEALONGPATH 函数

返回给定点上路径的切线角度。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

ANGLEALONGPATH (***section***， ***travel*** ***[，segment]*** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**String** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _travel_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点沿路径的百分比。必须介于 0 到 1 之间。  <br/> |
| _segment_ <br/> |可选  <br/> |**Integer** <br/> |计算切线角度所用路径的从 1 开始的线段。  <br/> |
   
### <a name="return-value"></a>返回值

 **Double**
  
## <a name="remarks"></a>备注

如果  _包含段值_ ，ANGLEALONGPATH 将仅返回该段的值。 
  
如果包含线  _段_ 值，ANGLEALONGPATH 将通过使用  _travel_ 来计算线段的 percertage，确定切  _线点_。
  
如果任 _一节__或_ 段不存在，Microsoft Visio返回 #REF！。 
  

