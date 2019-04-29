---
title: THEMEVAL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9eac3b8c-532c-4312-935d-fe8b63bcaf75
description: 检索活动主题中的值。
ms.openlocfilehash: ba95b8a920174ee44c0349d7227258d3ee8a843c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415752"
---
# <a name="themeval-function"></a>THEMEVAL 函数

检索活动主题中的值。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **THEMEVAL**([ _"theme_value"_] [, _default_]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _"theme_value"_ <br/> |可选  <br/> |**字符串** <br/> |要从中获取值的主题定义中的单元格的名称。  <br/> |
| _default_ <br/> |可选  <br/> |各种  <br/> |如果文档不具有主题 (没有主题定义), 则为默认值。  <br/> |
   
## <a name="remarks"></a>说明

如果**THEMEVAL**函数不接收任何参数, 它将返回主机单元格的主题值。 这是在当前主题的定义中存储的值。 主机单元格必须能够以有主题的的的的的的返回值。如果单元格不能有主题, **THEMEVAL**将返回错误。 
  
如果**THEMEVAL**函数接收单个参数, 它会从作为参数传入的主题定义中检索值。 为第一个参数传入的参数必须是整数或下表中列出的确切字符串之一。 
  
**THEMEVAL**函数还可以为第一个参数接受整数, 就像1到8之间的一个值。 使用 integer 值从主题的配色方案中按索引检索颜色。 因此, 值 "1" 将从主题中返回 "黑色" 颜色, "2" 返回 "浅色" 颜色, "3" 返回 "强调文字颜色 1" 的颜色等。 
  
如果**THEMEVAL**函数接收两个参数, 则它将从作为第一个参数传入的主题定义中检索值。 但是, 如果文档没有应用主题, 则**THEMEVAL**函数使用指定为第二个参数的值。 
  
**"theme_value" 参数的可能参数**

|**值**|**说明**|
|:-----|:-----|
|深浅  <br/> |检索主题定义中的深色 RGB 颜色。  <br/> |
|灯光  <br/> |从主题定义中检索浅 RGB 颜色。  <br/> |
|BackgroundColor  <br/> |检索主题定义中的背景 RGB 颜色。  <br/> |
|"AccentColor"  <br/> |检索主题定义中的 Accent1 RGB 颜色。  <br/> |
|"AccentColor2"  <br/> |检索主题定义中的 Accent2 RGB 颜色。  <br/> |
|"AccentColor3"  <br/> |检索主题定义中的 Accent3 RGB 颜色。  <br/> |
|"AccentColor4"  <br/> |检索主题定义中的 Accent4 RGB 颜色。  <br/> |
|"AccentColor5"  <br/> |检索主题定义中的 Accent5 RGB 颜色。  <br/> |
|"AccentColor6"  <br/> |检索主题定义中的 Accent6 RGB 颜色。  <br/> |
|LinePattern  <br/> |检索主题定义中的 LinePattern 单元格值。  <br/> |
|LineWeight  <br/> |从主题定义中检索线条的单元格值。  <br/> |
|LineColor  <br/> |检索主题定义中的 LineColor 单元格值。  <br/> |
|LineCap  <br/> |检索主题定义中的 LineCap 单元格值。  <br/> |
|"LineBegin"  <br/> |检索主题定义中的 BeginArrow 单元格值。  <br/> |
|"LineEnd"  <br/> |检索主题定义中的 EndArrow 单元格值。  <br/> |
|LineColorTrans  <br/> |检索主题定义中的 LineColorTrans 单元格值。  <br/> |
|"LineCompoundtype"  <br/> |检索主题定义中的 CompoundType 单元格值。  <br/> |
|"LineBegin"  <br/> |检索主题定义中的 BeginArrow 单元格值。  <br/> |
|"LineEnd"  <br/> |检索主题定义中的 EndArrow 单元格值。  <br/> |
|"LineBeginSize"  <br/> |检索主题定义中的 BeginArrowSize 单元格值。  <br/> |
|"LineEndSize"  <br/> |检索主题定义中的 EndArrowSize 单元格值。  <br/> |
|"LineRounding"  <br/> |从主题定义中检索舍入单元值。  <br/> |
|"ConnectorColor"  <br/> |检索主题定义中的 LineColor 单元格值。  <br/> |
|"ConnectorPattern"  <br/> |检索主题定义中的 LinePattern 单元格值。  <br/> |
|"ConnectorWeight"  <br/> |从主题定义中检索线条的单元格值。  <br/> |
|"ConnectorTransparency"  <br/> |检索主题定义中的 LineColorTrans 单元格值。  <br/> |
|"ConnectorRounding"  <br/> |从主题定义中检索舍入单元值。  <br/> |
|"ConnectorBegin"  <br/> |检索主题定义中的 BeginArrow 单元格值。  <br/> |
|"ConnectorEnd"  <br/> |检索主题定义中的 EndArrow 单元格值。  <br/> |
|"ConnectorBeginSize"  <br/> |检索主题定义中的 BeginArrowSize 单元格值。  <br/> |
|"ConnectorEndSize"  <br/> |检索主题定义中的 EndArrowSize 单元格值。  <br/> |
|FillColor  <br/> |检索主题定义中的 FillForegnd 单元格值。  <br/> |
|"FillColor2"  <br/> |检索主题定义中的 FillBkgnd 单元格值。  <br/> |
|"FillTransparency"  <br/> |检索主题定义中的 FillForegndTrans 单元格值。  <br/> |
|FillPattern  <br/> |检索主题定义中的 FillPattern 单元格值。  <br/> |
|LineGradientEnabled  <br/> |检索主题定义中的 LineGradientEnabled 单元格值。  <br/> |
|LineGradientDir  <br/> |检索主题定义中的 LineGradientDir 单元格值。  <br/> |
|LineGradientAngle  <br/> |检索主题定义中的 LineGradientAngle 单元格值。  <br/> |
|FillGradientEnabled  <br/> |检索主题定义中的 FillGradientEnabled 单元格值。  <br/> |
|FillGradientDir  <br/> |检索主题定义中的 FillGradientDir 单元格值。  <br/> |
|FillGradientAngle  <br/> |检索主题定义中的 FillGradientAngle 单元格值。  <br/> |
|RotateGradientWithShape  <br/> |检索主题定义中的 RotateGradientWithShape 单元格值。  <br/> |
|UseGroupGradient  <br/> |检索主题定义中的 UseGroupGradient 单元格值。  <br/> |
|"ShadowType"  <br/> |检索主题定义中的 ShapeShdwType 单元格值。  <br/> |
|"ShadowColor"  <br/> |检索主题定义中的 ShdwColor 单元格值。  <br/> |
|"ShadowTransparency"  <br/> |检索主题定义中的 ShdwColorTrans 单元格值。  <br/> |
|"ShadowMagnification"  <br/> |检索主题定义中的 ShapeShdwScaleFactor 单元格值。  <br/> |
|"ShadowBlur"  <br/> |检索主题定义中的 ShapeShdwBlur 单元格值。  <br/> |
|"ShadowXOffset"  <br/> |检索主题定义中的 ShapeShdwOffsetX 单元格值。  <br/> |
|"ShadowYOffset"  <br/> |检索主题定义中的 ShapeShdwOffsetY 单元格值。  <br/> |
|"ShadowDirection"  <br/> |检索主题定义中的 ShapeShdwObliqueAngle 单元格值。  <br/> |
|"ShadowPattern"  <br/> |检索主题定义中的 ShdwPattern 单元格值。  <br/> |
|BevelTopType  <br/> |检索主题定义中的 BevelTopType 单元格值。  <br/> |
|BevelTopWidth  <br/> |检索主题定义中的 BevelTopWidth 单元格值。  <br/> |
|BevelTopHeight  <br/> |检索主题定义中的 BevelTopHeight 单元格值。  <br/> |
|"BevelMaterial"  <br/> |检索主题定义中的 BevelMaterialType 单元格值。  <br/> |
|"BevelLighting"  <br/> |检索主题定义中的 BevelLightingType 单元格值。  <br/> |
|BevelLightingAngle  <br/> |检索主题定义中的 BevelLightingAngle 单元格值。  <br/> |
|BevelContourColor  <br/> |检索主题定义中的 BevelContourColor 单元格值。  <br/> |
|BevelContourSize  <br/> |检索主题定义中的 BevelContourSize 单元格值。  <br/> |
|ReflectionBlur  <br/> |检索主题定义中的 ReflectionBlur 单元格值。  <br/> |
|ReflectionDist  <br/> |检索主题定义中的 ReflectionDist 单元格值。  <br/> |
|ReflectionSize  <br/> |检索主题定义中的 ReflectionSize 单元格值。  <br/> |
|ReflectionTrans  <br/> |检索主题定义中的 ReflectionTrans 单元格值。  <br/> |
|SoftEdgesSize  <br/> |检索主题定义中的 SoftEdgesSize 单元格值。  <br/> |
|GlowSize  <br/> |检索主题定义中的 GlowSize 单元格值。  <br/> |
|GlowColor  <br/> |检索主题定义中的 GlowColor 单元格值。  <br/> |
|"GlowTransparency"  <br/> |检索主题定义中的 GlowColorTrans 单元格值。  <br/> |
|SketchAmount  <br/> |检索主题定义中的 SketchAmount 单元格值。  <br/> |
|SketchEnabled  <br/> |检索主题定义中的 SketchEnabled 单元格值。  <br/> |
|SketchFillChange  <br/> |检索主题定义中的 SketchFillChange 单元格值。  <br/> |
|SketchLineChange  <br/> |检索主题定义中的 SketchLineChange 单元格值。  <br/> |
|SketchLineWeight  <br/> |检索主题定义中的 SketchLineWeight 单元格值。  <br/> |
|"LatinFont"  <br/> |从主题定义中检索字体单元格值。  <br/> |
|TextColor  <br/> |从主题定义中检索 Color 单元值。  <br/> |
|文本  <br/> |检索主题定义中的字符样式单元值。  <br/> |
|"ComplexFont"  <br/> |检索主题定义中的 ComplexScriptFont 单元格值。  <br/> |
|AsianFont  <br/> |检索主题定义中的 AsianFont 单元格值。  <br/> |
|"FillStop [x] Color"  <br/> |从主题定义中检索行*x*中的颜色单元格值。  <br/> |
|"FillStop [x] 透明性"  <br/> |从主题定义中检索行*x*中的 ColorTrans 单元格值。  <br/> |
|"FillStop [x] 位置"  <br/> |从主题定义中检索行*x*中的 Position 单元格值。  <br/> |
|"LineStop [x] Color"  <br/> |从主题定义中检索行*x*中的颜色单元格值。  <br/> |
|"LineStop [x] 透明性"  <br/> |从主题定义中检索行*x*中的 ColorTrans 单元格值。  <br/> |
|"LineStop [x] 位置"  <br/> |从主题定义中检索行*x*中的 Position 单元格值。  <br/> |
   
## <a name="example"></a>示例

 `THEMEVAL("5")`
  
从主题定义中返回 "强调文字颜色 3" 颜色。
  
 `THEMEVAL("LineWeight", "0.7 pt.")`
  
从主题定义中返回 "线宽" 单元格的值。 如果包含此函数的形状未应用主题, 则函数返回 "0.7 pt."。
  

