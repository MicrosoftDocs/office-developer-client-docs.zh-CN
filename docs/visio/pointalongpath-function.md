---
title: POINTALONGPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7f91e5d9-89b8-5a0d-e01f-aa81fbd5e1fd
description: 返回路径上某一点的坐标或在路径中的偏离量。
ms.openlocfilehash: ce8b54bbd821cbfa6eb1f2789193ff8d7dda42d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430481"
---
# <a name="pointalongpath-function"></a>POINTALONGPATH 函数

返回路径上某一点的坐标或在路径中的偏离量。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

POINTALONGPATH (** *section* **， ** *travel* ** ** *[，offset]* ** ** *[，segment]* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**String** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _travel_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点经过的路径的百分比，用于标识点。必须为介于 0 和 1 之间的值。  <br/> |
| _offset_ <br/> |可选  <br/> |**Double** <br/> |点在路径中的偏移量。有关详细信息，请参阅“注解”。  <br/> |
| _segment_ <br/> |可选  <br/> |**Integer** <br/> |用于计算坐标的路径段（从 1 开始）。  <br/> |
   
### <a name="return-value"></a>返回值

 **Point**
  
## <a name="remarks"></a>备注

如果 _section_ 或 _segment_ 不存在，Microsoft Visio返回 #REF！。 
  
正  *偏移*  值指定移动方向左侧的点。 
  
负  *偏移*  值指定到达方向的右侧点。 
  
**点** 是指以单个值表示的几何坐标有序对 (*x,y*)。 
  

