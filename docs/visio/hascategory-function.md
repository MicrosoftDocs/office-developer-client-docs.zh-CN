---
title: HASCATEGORY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed3c997b-0a58-0432-c468-a24614b67f2e
description: 如果形状的类别列表中包含指定的字符串，则返回 TRUE。
ms.openlocfilehash: 902819f981b53aed96695e181ab556d3841d97c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433351"
---
# <a name="hascategory-function"></a>HASCATEGORY 函数

如果形状的类别列表中包含指定的字符串，则返回 TRUE。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

HASCATEGORY (* * *category* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _类别_ <br/> |必需  <br/> |**String** <br/> |要搜索的类别。  <br/> |
   
### <a name="return-value"></a>返回值

 **Boolean**
  
## <a name="remarks"></a>说明

 *类别*是用户定义的字符串, 可用于对形状进行分类。 可以在形状 ShapeSheet 的 User.msvShapeCategories 单元格中定义类别。 可以通过用分号分隔类别来为形状定义多个类别。 
  

