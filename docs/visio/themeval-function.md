---
title: THEMEVAL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9eac3b8c-532c-4312-935d-fe8b63bcaf75
description: 从活动主题检索值。
ms.openlocfilehash: ba95b8a920174ee44c0349d7227258d3ee8a843c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415752"
---
# <a name="themeval-function"></a>THEMEVAL 函数

从活动主题检索值。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **THEMEVAL** ([ _"theme_value"_][， _default_])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _"theme_value"_ <br/> |可选  <br/> |**字符串** <br/> |主题定义中要获取值的单元格的名称。  <br/> |
| _default_ <br/> |可选  <br/> |各种  <br/> |如果文档没有主题，则 (没有主题定义) 。  <br/> |
   
## <a name="remarks"></a>备注

如果 **THEMEVAL** 函数没有收到任何参数，它将返回主机单元格的主题值。 此值存储在当前主题的定义中。 主机单元格必须能够被设置为返回值;如果单元格无法进行主题处理， **则 THEMEVAL** 将返回错误。 
  
如果 **THEMEVAL** 函数收到单个参数，它将从作为参数传入的主题定义中检索值。 为第一个参数传入的参数必须是整数或下表中列出的确切字符串之一。 
  
**THEMEVAL** 函数还可以接受第一个参数的整数，作为 1 到 8 之间的值。 使用整数值从主题的配色方案中按索引检索颜色。 因此，值"1"将返回主题中的"深色"颜色，"2"返回"浅色"，"3"返回"强调文字颜色 1"等。 
  
如果 **THEMEVAL** 函数收到两个参数，它将检索作为第一个参数传入的主题定义中的值。 但是，如果文档应用了"无主题"， **则 THEMEVAL** 函数将使用指定为第二个参数的值。 
  
**"theme_value"参数的可能参数**

|**值**|**说明**|
|:-----|:-----|
|"Dark"  <br/> |从主题定义中检索深色 RGB 颜色。  <br/> |
|"Light"  <br/> |从主题定义中检索浅色 RGB 颜色。  <br/> |
|"BackgroundColor"  <br/> |从主题定义中检索背景 RGB 颜色。  <br/> |
|"AccentColor"  <br/> |从主题定义中检索 Accent1 RGB 颜色。  <br/> |
|"AccentColor2"  <br/> |从主题定义中检索 Accent2 RGB 颜色。  <br/> |
|"AccentColor3"  <br/> |从主题定义中检索 Accent3 RGB 颜色。  <br/> |
|"AccentColor4"  <br/> |从主题定义中检索 Accent4 RGB 颜色。  <br/> |
|"AccentColor5"  <br/> |从主题定义中检索 Accent5 RGB 颜色。  <br/> |
|"AccentColor6"  <br/> |从主题定义中检索 Accent6 RGB 颜色。  <br/> |
|"LinePattern"  <br/> |从主题定义中检索 LinePattern 单元格值。  <br/> |
|"LineWeight"  <br/> |从主题定义中检索 LineWeight 单元格值。  <br/> |
|"LineColor"  <br/> |从主题定义中检索 LineColor 单元格值。  <br/> |
|"LineCap"  <br/> |从主题定义中检索 LineCap 单元格值。  <br/> |
|"LineBegin"  <br/> |从主题定义中检索 BeginArrow 单元格值。  <br/> |
|"LineEnd"  <br/> |从主题定义中检索 EndArrow 单元格值。  <br/> |
|"LineColorTrans"  <br/> |从主题定义中检索 LineColorTrans 单元格值。  <br/> |
|"LineCompoundtype"  <br/> |从主题定义中检索 CompoundType 单元格值。  <br/> |
|"LineBegin"  <br/> |从主题定义中检索 BeginArrow 单元格值。  <br/> |
|"LineEnd"  <br/> |从主题定义中检索 EndArrow 单元格值。  <br/> |
|"LineBeginSize"  <br/> |从主题定义中检索 BeginArrowSize 单元格值。  <br/> |
|"LineEndSize"  <br/> |从主题定义中检索 EndArrowSize 单元格值。  <br/> |
|"LineRounding"  <br/> |从主题定义检索 Rounding 单元格值。  <br/> |
|"ConnectorColor"  <br/> |从主题定义中检索 LineColor 单元格值。  <br/> |
|"ConnectorPattern"  <br/> |从主题定义中检索 LinePattern 单元格值。  <br/> |
|"ConnectorWeight"  <br/> |从主题定义中检索 LineWeight 单元格值。  <br/> |
|"ConnectorTransparency"  <br/> |从主题定义中检索 LineColorTrans 单元格值。  <br/> |
|"ConnectorRounding"  <br/> |从主题定义检索 Rounding 单元格值。  <br/> |
|"ConnectorBegin"  <br/> |从主题定义中检索 BeginArrow 单元格值。  <br/> |
|"ConnectorEnd"  <br/> |从主题定义中检索 EndArrow 单元格值。  <br/> |
|"ConnectorBeginSize"  <br/> |从主题定义中检索 BeginArrowSize 单元格值。  <br/> |
|"ConnectorEndSize"  <br/> |从主题定义中检索 EndArrowSize 单元格值。  <br/> |
|"FillColor"  <br/> |从主题定义中检索 FillForegnd 单元格值。  <br/> |
|"FillColor2"  <br/> |从主题定义中检索 FillBkgnd 单元格值。  <br/> |
|"FillTransparency"  <br/> |从主题定义检索 FillForegndTrans 单元格值。  <br/> |
|"FillPattern"  <br/> |从主题定义中检索 FillPattern 单元格值。  <br/> |
|"LineGradientEnabled"  <br/> |从主题定义中检索 LineGradientEnabled 单元格值。  <br/> |
|"LineGradientDir"  <br/> |从主题定义中检索 LineGradientDir 单元格值。  <br/> |
|"LineGradientAngle"  <br/> |从主题定义中检索 LineGradientAngle 单元格值。  <br/> |
|"FillGradientEnabled"  <br/> |从主题定义中检索 FillGradientEnabled 单元格值。  <br/> |
|"FillGradientDir"  <br/> |从主题定义中检索 FillGradientDir 单元格值。  <br/> |
|"FillGradientAngle"  <br/> |从主题定义中检索 FillGradientAngle 单元格值。  <br/> |
|"RotateGradientWithShape"  <br/> |从主题定义检索 RotateGradientWithShape 单元格值。  <br/> |
|"UseGroupGradient"  <br/> |从主题定义中检索 UseGroupGradient 单元格值。  <br/> |
|"ShadowType"  <br/> |从主题定义中检索 ShapeShdwType 单元格值。  <br/> |
|"ShadowColor"  <br/> |从主题定义中检索 ShdwColor 单元格值。  <br/> |
|"ShadowTransparency"  <br/> |从主题定义中检索 ShdwColorTrans 单元格值。  <br/> |
|"ShadowMagnification"  <br/> |从主题定义中检索 ShapeShdwScaleFactor 单元格值。  <br/> |
|"ShadowBlur"  <br/> |从主题定义中检索 ShapeShdwBlur 单元格值。  <br/> |
|"ShadowXOffset"  <br/> |从主题定义中检索 ShapeShdwOffsetX 单元格值。  <br/> |
|"ShadowYOffset"  <br/> |从主题定义中检索 ShapeShdwOffsetY 单元格值。  <br/> |
|"ShadowDirection"  <br/> |从主题定义中检索 ShapeShdwObliqueAngle 单元格值。  <br/> |
|"ShadowPattern"  <br/> |从主题定义中检索 ShdwPattern 单元格值。  <br/> |
|"BevelTopType"  <br/> |从主题定义中检索 BevelTopType 单元格值。  <br/> |
|"BevelTopWidth"  <br/> |从主题定义中检索 BevelTopWidth 单元格值。  <br/> |
|"BevelTopHeight"  <br/> |从主题定义中检索 BevelTopHeight 单元格值。  <br/> |
|"BevelMaterial"  <br/> |从主题定义中检索 BevelMaterialType 单元格值。  <br/> |
|"BevelLighting"  <br/> |从主题定义中检索 BevelLightingType 单元格值。  <br/> |
|"BevelLightingAngle"  <br/> |从主题定义中检索 BevelLightingAngle 单元格值。  <br/> |
|"BevelContourColor"  <br/> |从主题定义中检索 BevelContourColor 单元格值。  <br/> |
|"BevelContourSize"  <br/> |从主题定义检索 BevelContourSize 单元格值。  <br/> |
|"ReflectionBlur"  <br/> |从主题定义中检索 ReflectionBlur 单元格值。  <br/> |
|"ReflectionDist"  <br/> |从主题定义中检索 ReflectionDist 单元格值。  <br/> |
|"ReflectionSize"  <br/> |从主题定义中检索 ReflectionSize 单元格值。  <br/> |
|"ReflectionTrans"  <br/> |从主题定义中检索 ReflectionTrans 单元格值。  <br/> |
|"SoftEdgesSize"  <br/> |从主题定义检索 SoftEdgesSize 单元格值。  <br/> |
|"GlowSize"  <br/> |从主题定义中检索 GlowSize 单元格值。  <br/> |
|"GlowColor"  <br/> |从主题定义中检索 GlowColor 单元格值。  <br/> |
|"GlowTransparency"  <br/> |从主题定义检索 GlowColorTrans 单元格值。  <br/> |
|"SketchAmount"  <br/> |从主题定义中检索 SketchAmount 单元格值。  <br/> |
|"SketchEnabled"  <br/> |从主题定义中检索 SketchEnabled 单元格值。  <br/> |
|"SketchFillChange"  <br/> |从主题定义中检索 SketchFillChange 单元格值。  <br/> |
|"SketchLineChange"  <br/> |从主题定义中检索 SketchLineChange 单元格值。  <br/> |
|"SketchLineWeight"  <br/> |从主题定义中检索 SketchLineWeight 单元格值。  <br/> |
|"LatinFont"  <br/> |从主题定义中检索 Font 单元格值。  <br/> |
|"TextColor"  <br/> |从主题定义中检索 Color 单元格值。  <br/> |
|"TextStyle"  <br/> |从主题定义中检索 Character.Style 单元格值。  <br/> |
|"ComplexFont"  <br/> |从主题定义中检索 ComplexScriptFont 单元格值。  <br/> |
|"AsianFont"  <br/> |从主题定义中检索 AsianFont 单元格值。  <br/> |
|"FillStop[x]Color"  <br/> |从主题定义中检索行  *x*  中的 Color 单元格值。  <br/> |
|"FillStop[x]Transparency"  <br/> |从主题定义中检索  *行 x*  中的 ColorTrans 单元格值。  <br/> |
|"FillStop[x]Position"  <br/> |从主题定义中检索行  *x*  中的 Position 单元格值。  <br/> |
|"LineStop[x]Color"  <br/> |从主题定义中检索行  *x*  中的 Color 单元格值。  <br/> |
|"LineStop[x]Transparency"  <br/> |从主题定义中检索  *行 x*  中的 ColorTrans 单元格值。  <br/> |
|"LineStop[x]Position"  <br/> |从主题定义中检索行  *x*  中的 Position 单元格值。  <br/> |
   
## <a name="example"></a>示例

 `THEMEVAL("5")`
  
从主题定义中返回"强调文字颜色 3"颜色。
  
 `THEMEVAL("LineWeight", "0.7 pt.")`
  
从主题定义中返回"LineWeight"单元格的值。 如果包含此函数的形状应用了"无主题"，该函数将返回"0.7 pt"。
  

