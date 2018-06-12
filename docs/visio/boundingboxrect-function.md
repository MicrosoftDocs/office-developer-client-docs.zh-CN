---
title: BOUNDINGBOXRECT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1f66d2b2-ec9e-cd58-7642-96850fe4589e
description: 返回形状的边界框指定边缘的坐标。
ms.openlocfilehash: 2c850cb213ec0093ead53cd860f92e38da46f27e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779797"
---
# <a name="boundingboxrect-function"></a>BOUNDINGBOXRECT 函数

返回形状的边界框指定边缘的坐标。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010 
  
## <a name="syntax"></a>语法

BOUNDINGBOXRECT (* **索引** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _Index_ <br/> |必需  <br/> |**Integer** <br/> |要获取坐标的形状的边界框边缘。请参阅“注解”以了解可能的值。  <br/> |
   
### <a name="return-value"></a>返回值

 **编号**
  
## <a name="remarks"></a>备注

 *Index*可为以下值之一。 
  
|**Item**|**值**|
|:-----|:-----|
|左边缘  <br/> |0  <br/> |
|右边缘  <br/> |1  <br/> |
|上边缘  <br/> |2  <br/> |
|下边缘  <br/> |3  <br/> |
   
如果该形状具有父项，返回值位于该父坐标系统。
  

