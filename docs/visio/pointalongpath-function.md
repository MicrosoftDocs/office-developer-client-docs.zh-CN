---
title: POINTALONGPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7f91e5d9-89b8-5a0d-e01f-aa81fbd5e1fd
description: 返回路径上某一点的坐标或在路径中的偏离量。
ms.openlocfilehash: 9ce6f8c171515b46aaff0ce07cbe7da4f1e958d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780890"
---
# <a name="pointalongpath-function"></a>POINTALONGPATH 函数

返回路径上某一点的坐标或在路径中的偏离量。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

POINTALONGPATH (* **部分** *，* **差旅** * * * *[，偏移量]* * * * * *[、 段]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**字符串** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _出差_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点经过的路径的百分比，用于标识点。必须为介于 0 和 1 之间的值。  <br/> |
| _偏移量_ <br/> |可选  <br/> |**Double** <br/> |点在路径中的偏移量。有关详细信息，请参阅“注解”。  <br/> |
| _段_ <br/> |可选  <br/> |**Integer** <br/> |用于计算坐标的路径段（从 1 开始）。  <br/> |
   
### <a name="return-value"></a>返回值

 **Point**
  
## <a name="remarks"></a>说明

如果_section_或_segment_不存在，Microsoft Visio 将返回 #REF ！。 
  
正*偏移*值指定点位于路径延伸方向的左侧。 
  
负*偏移*值指定点位于路径延伸方向的右侧。 
  
**点**是指以单个值表示的几何坐标有序对 (*x,y*)。 
  

