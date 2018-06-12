---
title: HASCATEGORY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed3c997b-0a58-0432-c468-a24614b67f2e
description: 如果形状的类别列表中包含指定的字符串，则返回 TRUE。
ms.openlocfilehash: 2445b4c3af63b331b303897997ce38b0747f17fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780388"
---
# <a name="hascategory-function"></a>HASCATEGORY 函数

如果形状的类别列表中包含指定的字符串，则返回 TRUE。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010 
  
## <a name="syntax"></a>语法

HASCATEGORY (* **类别** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _category_ <br/> |必需  <br/> |**字符串** <br/> |要搜索的类别。  <br/> |
   
### <a name="return-value"></a>返回值

 **Boolean**
  
## <a name="remarks"></a>备注

 *类别*是可用于对形状进行分类的用户定义的字符串。 您可以在形状的 ShapeSheet User.msvShapeCategories 单元格中定义类别。 您可以通过使用分号分隔类别来定义形状的多个类别。 
  

