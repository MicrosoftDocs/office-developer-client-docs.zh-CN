---
title: THEMECBV 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ef62f63f-b2ce-4d12-a294-93dbdc9a869d
description: 返回 RGB 值或一个整数，表示在文档的调色板中的索引中的活动主题的渐变设置存储的指定淡色或底纹值其中已修改作为参数传入的颜色 （数目）。
ms.openlocfilehash: 878da505a840234445d3e16d3b8a68e31eaf5fda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781518"
---
# <a name="themecbv-function"></a>THEMECBV 函数

返回 RGB 值或一个整数，表示在文档的调色板中的索引中的活动主题的渐变设置存储的指定淡色或底纹值其中已修改作为参数传入的颜色 （数目）。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **THEMECBV**（_颜色_， _gradient_stop_number_）
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**编号** <br/> |代表文档的调色板中的索引号。  <br/> |
| _gradient_stop_number_ <br/> |必需  <br/> |**编号** <br/> |渐变光圈 （淡色或底纹） 存储中的活动主题的渐变设置要应用的颜色。  <br/> |
   
## <a name="return-value"></a>返回值

 **编号**
  
## <a name="remarks"></a>说明

> [!NOTE]
> THEMECBV 函数无实际作用如果 QuickStyle 使用分配给该形状没有渐变作为参数传递中的颜色。 
  
主题中的渐变设置是一系列的编号对应于"浅色"（淡色） 或"变暗"（%底纹） 的渐变光圈。 这些阴影和淡色于要创建的渐变颜色效果的基本颜色。
  
**THEMECBV**采用颜色输入和输出颜色后它已修改的色调或指定渐变光圈 %底纹。 淡色和阴影来自主题的定义，如果当前的快速样式包含渐变填充。 如果活动的快速样式没有指定渐变填充或形状设置为无主题，此公式将只返回第一个参数中传递的颜色。 
  
## <a name="example"></a>示例

 `THEMECBV(FillForegnd, 5)`
  
返回由将淡色或中第五个渐变光圈的渐变底纹应用于指定在**FillForegnd**单元格的颜色的颜色。 
  
 `THEMECBV(RGB(255,0,0), 2)`
  
返回底纹或创建的第二个渐变光圈应用到基本颜色的红色的红色的淡色。
  

