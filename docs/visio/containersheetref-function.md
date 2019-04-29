---
title: CONTAINERSHEETREF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bbdb2dea-4f75-b73e-a98a-0031f34dff2c
description: 返回对包含形状的指定容器的工作表引用。
ms.openlocfilehash: 473d8c0b81ecc568c1d4f3a3b3a885e1ceb4e00d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437264"
---
# <a name="containersheetref-function"></a>CONTAINERSHEETREF 函数

返回对包含形状的指定容器的工作表引用。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

CONTAINERSHEETREF (* * *index* * * * * *[, category]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _index_ <br/> |必需  <br/> |**Integer** <br/> |从 1 开始的容器索引。 有关详细信息，请参阅"说明"。  <br/> |
| _类别_ <br/> |可选  <br/> |**字符串** <br/> |容器的类别。 有关详细信息，请参阅“注解”。  <br/> |
   
### <a name="return-value"></a>返回值

ShapeSheet 参考
  
## <a name="remarks"></a>说明

根据容器从前向后的 Z 顺序计算容器的索引。
  
 *类别*是用户定义的字符串, 可用于对形状进行分类。 可以在形状 ShapeSheet 的 User.msvShapeCategories 单元格中定义类别。 可以通过用分号分隔类别为形状定义多个类别。 
  
如果形状不是容器的成员，或者没有容器与指定的索引号和类别相匹配，则 CONTAINERSHEETREF 返回 #REF!。
  
## <a name="example"></a>示例

CONTAINERSHEETREF (1)!高度 
  
返回容器的 Height 单元格中的值，该容器位于形状所属页面的最顶层。 
  

