---
title: BOUNDINGBOXRECT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1f66d2b2-ec9e-cd58-7642-96850fe4589e
description: 返回形状的边界框指定边缘的坐标。
ms.openlocfilehash: 0018118eb0991fe9dc1da0eb000566b69d8a4b4d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418069"
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
| _Index_ <br/> |必需  <br/> |**Integer** <br/> |要获取坐标的形状的边界框边缘。 请参阅“注解”以了解可能的值。  <br/> |
   
### <a name="return-value"></a>返回值

 **Number**
  
## <a name="remarks"></a>说明

 *索引*可以是下列值之一。 
  
|**项**|**值**|
|:-----|:-----|
|左边缘  <br/> |0  <br/> |
|右边缘  <br/> |1  <br/> |
|上边缘  <br/> |双面  <br/> |
|下边缘  <br/> |第三章  <br/> |
   
如果形状具有父级, 则返回值位于父项的坐标系统中。
  

