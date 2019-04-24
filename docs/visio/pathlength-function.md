---
title: PATHLENGTH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f47ea08-fb5e-7d48-e84a-2a6570564924
description: 返回在指定 Geometry 节中定义的路径的长度。
ms.openlocfilehash: e4f90c2bb886f54164bedab5f8d78fc528758414
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344413"
---
# <a name="pathlength-function"></a>PATHLENGTH 函数

返回在指定 Geometry 节中定义的路径的长度。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

PATHLENGTH (* * *section* * * * * *[, segment]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**String** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _段落_ <br/> |可选  <br/> |**Integer** <br/> |要度量的路径段（从 1 开始）。  <br/> |
   
### <a name="return-value"></a>返回值

 **Double**
  
## <a name="remarks"></a>备注

如果_section_或_segment_不存在, Microsoft Visio 将返回 #REF!。 
  
如果包含_线段_值, 则 PATHLENGTH 仅返回该线段的长度。 
  

