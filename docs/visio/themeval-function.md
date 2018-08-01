---
title: THEMEVAL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9eac3b8c-532c-4312-935d-fe8b63bcaf75
description: 检索活动主题中的值。
ms.openlocfilehash: 7bbd017c859a0a167bbd279d60af029e98421375
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781523"
---
# <a name="themeval-function"></a>THEMEVAL 函数

检索活动主题中的值。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **THEMEVAL**([ _"theme_value"_] [，_默认_]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _"theme_value"_ <br/> |可选  <br/> |**字符串** <br/> |要获取值的主题定义中的单元格的名称。  <br/> |
| _default_ <br/> |可选  <br/> |各种  <br/> |如果文档不是应用了主题的默认值 （没有主题定义）。  <br/> |
   
## <a name="remarks"></a>说明

如果**THEMEVAL**函数不会收到任何参数，则返回的主机单元格应用了主题的值。 这是当前主题的定义中存储的值。 是承载单元格必须能够正在应用了主题返回值;如果单元格不能被应用了主题， **THEMEVAL**将返回错误。 
  
如果**THEMEVAL**函数接收单个参数，则可检索从主题定义作为参数传入的值。 为第一个参数中传递参数必须是整数或一个下表中列出的准确字符串。 
  
**THEMEVAL**函数还可以接受的第一个参数，一个整数，作为 1 到 8 之间的值。 使用整数值的主题的配色方案中的索引来检索一种颜色。 因此，值为"1"将返回主题中的"深色"、"2"返回"轻量型"颜色、"3"返回"强调文字颜色 1"的颜色，等等。 
  
如果**THEMEVAL**函数接收两个参数，则可检索从作为第一个参数传递中的主题定义值。 但是，如果文档有无主题应用于它，则**THEMEVAL**函数将使用为第二个参数指定的值。 
  
**"Theme_value"参数的可能参数**

|**值**|**说明**|
|:-----|:-----|
|"深色"  <br/> |检索的主题定义深 RGB 颜色。  <br/> |
|"轻量型"  <br/> |检索的主题定义浅色 RGB 颜色。  <br/> |
|"BackgroundColor"  <br/> |检索的主题定义背景 RGB 颜色。  <br/> |
|"AccentColor"  <br/> |检索的主题定义强调文字颜色 1 RGB 颜色。  <br/> |
|"AccentColor2"  <br/> |检索的主题定义 Accent2 RGB 颜色。  <br/> |
|"AccentColor3"  <br/> |检索的主题定义 Accent3 RGB 颜色。  <br/> |
|"AccentColor4"  <br/> |检索的主题定义 Accent4 RGB 颜色。  <br/> |
|"AccentColor5"  <br/> |检索的主题定义 Accent5 RGB 颜色。  <br/> |
|"AccentColor6"  <br/> |检索的主题定义 Accent6 RGB 颜色。  <br/> |
|"LinePattern"  <br/> |检索的主题定义 LinePattern 单元格的值。  <br/> |
|"线条粗细"  <br/> |检索的主题定义 LineWeight 单元格的值。  <br/> |
|"LineColor"  <br/> |检索的主题定义 LineColor 单元格的值。  <br/> |
|"LineCap"  <br/> |检索的主题定义 LineCap 单元格的值。  <br/> |
|"LineBegin"  <br/> |检索的主题定义 BeginArrow 单元格的值。  <br/> |
|"LineEnd"  <br/> |检索的主题定义 EndArrow 单元格的值。  <br/> |
|"LineColorTrans"  <br/> |检索的主题定义 LineColorTrans 单元格的值。  <br/> |
|"LineCompoundtype"  <br/> |检索的主题定义 CompoundType 单元格的值。  <br/> |
|"LineBegin"  <br/> |检索的主题定义 BeginArrow 单元格的值。  <br/> |
|"LineEnd"  <br/> |检索的主题定义 EndArrow 单元格的值。  <br/> |
|"LineBeginSize"  <br/> |检索的主题定义 BeginArrowSize 单元格的值。  <br/> |
|"LineEndSize"  <br/> |检索的主题定义 EndArrowSize 单元格的值。  <br/> |
|"LineRounding"  <br/> |检索的主题定义 Rounding 单元格的值。  <br/> |
|"ConnectorColor"  <br/> |检索的主题定义 LineColor 单元格的值。  <br/> |
|"ConnectorPattern"  <br/> |检索的主题定义 LinePattern 单元格的值。  <br/> |
|"ConnectorWeight"  <br/> |检索的主题定义 LineWeight 单元格的值。  <br/> |
|"ConnectorTransparency"  <br/> |检索的主题定义 LineColorTrans 单元格的值。  <br/> |
|"ConnectorRounding"  <br/> |检索的主题定义 Rounding 单元格的值。  <br/> |
|"ConnectorBegin"  <br/> |检索的主题定义 BeginArrow 单元格的值。  <br/> |
|"ConnectorEnd"  <br/> |检索的主题定义 EndArrow 单元格的值。  <br/> |
|"ConnectorBeginSize"  <br/> |检索的主题定义 BeginArrowSize 单元格的值。  <br/> |
|"ConnectorEndSize"  <br/> |检索的主题定义 EndArrowSize 单元格的值。  <br/> |
|"FillColor"  <br/> |检索的主题定义 FillForegnd 单元格的值。  <br/> |
|"FillColor2"  <br/> |检索的主题定义 FillBkgnd 单元格的值。  <br/> |
|"FillTransparency"  <br/> |检索的主题定义 FillForegndTrans 单元格的值。  <br/> |
|"FillPattern"  <br/> |检索的主题定义 FillPattern 单元格的值。  <br/> |
|"LineGradientEnabled"  <br/> |检索的主题定义 LineGradientEnabled 单元格的值。  <br/> |
|"LineGradientDir"  <br/> |检索的主题定义 LineGradientDir 单元格的值。  <br/> |
|"LineGradientAngle"  <br/> |检索的主题定义 LineGradientAngle 单元格的值。  <br/> |
|"FillGradientEnabled"  <br/> |检索的主题定义 FillGradientEnabled 单元格的值。  <br/> |
|"FillGradientDir"  <br/> |检索的主题定义 FillGradientDir 单元格的值。  <br/> |
|"FillGradientAngle"  <br/> |检索的主题定义 FillGradientAngle 单元格的值。  <br/> |
|"RotateGradientWithShape"  <br/> |检索的主题定义 RotateGradientWithShape 单元格的值。  <br/> |
|"UseGroupGradient"  <br/> |检索的主题定义 UseGroupGradient 单元格的值。  <br/> |
|"ShadowType"  <br/> |检索的主题定义 ShapeShdwType 单元格的值。  <br/> |
|"ShadowColor"  <br/> |检索的主题定义 ShdwColor 单元格的值。  <br/> |
|"ShadowTransparency"  <br/> |检索的主题定义 ShdwColorTrans 单元格的值。  <br/> |
|"ShadowMagnification"  <br/> |检索的主题定义 ShapeShdwScaleFactor 单元格的值。  <br/> |
|"ShadowBlur"  <br/> |检索的主题定义 ShapeShdwBlur 单元格的值。  <br/> |
|"ShadowXOffset"  <br/> |检索的主题定义 ShapeShdwOffsetX 单元格的值。  <br/> |
|"ShadowYOffset"  <br/> |检索的主题定义 ShapeShdwOffsetY 单元格的值。  <br/> |
|"ShadowDirection"  <br/> |检索的主题定义 ShapeShdwObliqueAngle 单元格的值。  <br/> |
|"ShadowPattern"  <br/> |检索的主题定义 ShdwPattern 单元格的值。  <br/> |
|"BevelTopType"  <br/> |检索的主题定义 BevelTopType 单元格的值。  <br/> |
|"BevelTopWidth"  <br/> |检索的主题定义 BevelTopWidth 单元格的值。  <br/> |
|"BevelTopHeight"  <br/> |检索的主题定义 BevelTopHeight 单元格的值。  <br/> |
|"BevelMaterial"  <br/> |检索的主题定义 BevelMaterialType 单元格的值。  <br/> |
|"BevelLighting"  <br/> |检索的主题定义 BevelLightingType 单元格的值。  <br/> |
|"BevelLightingAngle"  <br/> |检索的主题定义 BevelLightingAngle 单元格的值。  <br/> |
|"BevelContourColor"  <br/> |检索的主题定义 BevelContourColor 单元格的值。  <br/> |
|"BevelContourSize"  <br/> |检索的主题定义 BevelContourSize 单元格的值。  <br/> |
|"ReflectionBlur"  <br/> |检索的主题定义 ReflectionBlur 单元格的值。  <br/> |
|"ReflectionDist"  <br/> |检索的主题定义 ReflectionDist 单元格的值。  <br/> |
|"ReflectionSize"  <br/> |检索的主题定义 ReflectionSize 单元格的值。  <br/> |
|"ReflectionTrans"  <br/> |检索的主题定义 ReflectionTrans 单元格的值。  <br/> |
|"SoftEdgesSize"  <br/> |检索的主题定义 SoftEdgesSize 单元格的值。  <br/> |
|"GlowSize"  <br/> |检索的主题定义 GlowSize 单元格的值。  <br/> |
|"GlowColor"  <br/> |检索的主题定义 GlowColor 单元格的值。  <br/> |
|"GlowTransparency"  <br/> |检索的主题定义 GlowColorTrans 单元格的值。  <br/> |
|"SketchAmount"  <br/> |检索的主题定义 SketchAmount 单元格的值。  <br/> |
|"SketchEnabled"  <br/> |检索的主题定义 SketchEnabled 单元格的值。  <br/> |
|"SketchFillChange"  <br/> |检索的主题定义 SketchFillChange 单元格的值。  <br/> |
|"SketchLineChange"  <br/> |检索的主题定义 SketchLineChange 单元格的值。  <br/> |
|"SketchLineWeight"  <br/> |检索的主题定义 SketchLineWeight 单元格的值。  <br/> |
|"LatinFont"  <br/> |从主题定义检索 Font 单元格的值。  <br/> |
|"TextColor"  <br/> |检索的主题定义 Color 单元格的值。  <br/> |
|"文本样式"  <br/> |检索的主题定义 Character.Style 单元格的值。  <br/> |
|"ComplexFont"  <br/> |检索的主题定义 ComplexScriptFont 单元格的值。  <br/> |
|"AsianFont"  <br/> |检索的主题定义 AsianFont 单元格的值。  <br/> |
|"FillStop [x] 颜色"  <br/> |Color 单元格值行*x*中的检索的主题定义。  <br/> |
|"FillStop [x] 透明度"  <br/> |检索主题定义在行*x* ColorTrans 单元格的值。  <br/> |
|"FillStop [x] 位置"  <br/> |从主题定义检索位置行*x*中的单元格值。  <br/> |
|"LineStop [x] 颜色"  <br/> |Color 单元格值行*x*中的检索的主题定义。  <br/> |
|"LineStop [x] 透明度"  <br/> |检索主题定义在行*x* ColorTrans 单元格的值。  <br/> |
|"LineStop [x] 位置"  <br/> |从主题定义检索位置行*x*中的单元格值。  <br/> |
   
## <a name="example"></a>示例

 `THEMEVAL("5")`
  
返回从主题定义"强调文字颜色 3"颜色。
  
 `THEMEVAL("LineWeight", "0.7 pt.")`
  
返回从主题定义"线条粗细"单元格的值。 如果包含此函数的形状有无主题应用于它，则函数将返回 0.7 pt。。
  

