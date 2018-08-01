---
title: 面向 Visio ShapeSheet 开发人员的新增功能
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1046253
localization_priority: Normal
ms.assetid: d4f0cf7a-ac4b-c914-7887-e1d65e9d59fa
description: Visio 2013 的自定义绘图解决方案提供了功能强大的单个平台。 新的 ShapeSheet 单元格和函数，新自动化对象、 属性、 方法和事件，以及为您提供更多选项定义和控制在您的解决方案元素的行为。
ms.openlocfilehash: 26bf8f6071c9f67d017d8ffc3a47fb1f820df01d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781666"
---
# <a name="whats-new-for-visio-shapesheet-developers"></a>面向 Visio ShapeSheet 开发人员的新增功能

Visio 2013 的自定义绘图解决方案提供了功能强大的单个平台。 新的 ShapeSheet 单元格和函数，新自动化对象、 属性、 方法和事件，以及为您提供更多选项定义和控制在您的解决方案元素的行为。
  
## <a name="new-and-changed-cells"></a>新的和更改的单元格
<a name="vis15_WhatsNew_Cells"> </a>

下表列出了可用于构建 ShapeSheet 解决方案 Visio 2013 中的新单元格。
  
|**新单元格**|**Section**|
|:-----|:-----|
|[BevelBottomHeight](bevelbottomheight-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelBottomType](bevelbottomtype-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelBottomWidth](bevelbottomwidth-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelContourColor](bevelcontourcolor-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelContourSize](bevelcontoursize-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelDepthColor](beveldepthcolor-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelDepthSize](beveldepthsize-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelLightingAngle](bevellightingangle-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelLightingType](bevellightingtype-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelMaterialType](bevelmaterialtype-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelTopHeight](beveltopheight-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelTopType](beveltoptype-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[BevelTopWidth](beveltopwidth-cell-bevel-properties-section.md) <br/> |Bevel 属性  <br/> |
|[ClippingPath](clippingpath-cell-foreign-image-info-section.md) <br/> |Foreign Image Info  <br/> |
|[ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md) <br/> |主题属性  <br/> |
|[CompoundType](compoundtype-cell-line-format-section.md) <br/> |行格式  <br/> |
|[ConnectorSchemeIndex](connectorschemeindex-cell-theme-properties-section.md) <br/> |主题属性  <br/> |
|[DistanceFromGround](distancefromground-cell-3-d-rotation-properties.md) <br/> |三维旋转属性  <br/> |
|[DocLockReplace](doclockreplace-cell-document-properties-section.md) <br/> |文档属性  <br/> |
|[EffectSchemeIndex](effectschemeindex-cell-theme-properties-section.md) <br/> |主题属性  <br/> |
|[FillGradientAngle](fillgradientangle-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
|[FillGradientDir](fillgradientdir-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
|[FillGradientEnabled](fillgradientenabled-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
|[FontSchemeIndex](fontschemeindex-cell-theme-properties-section.md) <br/> |主题属性  <br/> |
|[GlowColor](glowcolor-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[GlowColorTrans](glowcolortrans-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[GlowSize](glowsize-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[KeepTextFlat](keeptextflat-cell-3-d-rotation-properties-section.md) <br/> |三维旋转属性  <br/> |
|[LineGradientAngle](linegradientangle-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
|[LineGradientDir](linegradientdir-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
|[LineGradientEnabled](linegradientenabled-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
|[LockReplace](lockreplace-cell-protection-section.md) <br/> |保护  <br/> |
|[LockThemeConnectors](lockthemeconnectors-cell-protection-section.md) <br/> |保护  <br/> |
|[LockThemeFonts](lockthemefonts-cell-protection-section.md) <br/> |保护  <br/> |
|[LockThemeIndex](lockthemeindex-cell-protection-section.md) <br/> |保护  <br/> |
|[NoCoauth](nocoauth-cell-document-properties-section.md) <br/> |文档属性  <br/> |
|[PageLockReplace](pagelockreplace-cell-page-properties-section.md) <br/> |页面属性  <br/> |
|[角度来看](perspective-cell-3-d-rotation-properties-section.md) <br/> |三维旋转属性  <br/> |
|[QuickStyleEffectsMatrix](quickstyleeffectsmatrix-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[QuickStyleFillColor](quickstylefillcolor-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[QuickStyleFillMatrix](quickstylefillmatrix-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[QuickStyleFontColor](quickstylefontcolor-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[QuickStyleLineColor](quickstylelinecolor-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[QuickStyleLineMatrix](quickstylelinematrix-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[QuickStyleShadowColor](quickstyleshadowcolor-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[QuickStyleType](quickstyletype-cell-quick-style-section.md) <br/> |快速样式  <br/> |
|[ReflectionBlur](reflectionblur-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[ReflectionDist](reflectiondist-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[ReflectionSize](reflectionsize-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[ReflectionTrans](reflectiontrans-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[ReplaceCopyCells](replacecopycells-cell-change-shape-behavior-section.md) <br/> |更改形状行为  <br/> |
|[ReplaceLockFormat](replacelockformat-cell-change-shape-behavior-section.md) <br/> |更改形状行为  <br/> |
|[ReplaceLockShapeData](replacelockshapedata-cell-change-shape-behavior-section.md) <br/> |更改形状行为  <br/> |
|[ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md) <br/> |更改形状行为  <br/> |
|[RotateGradientWithShape](rotategradientwithshape-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
|[RotationType](rotationtype-cell-3-d-rotation-properties-section.md) <br/> |三维旋转属性  <br/> |
|[RotationXAngle](rotationxangle-cell-3-d-rotation-properties-section.md) <br/> |三维旋转属性  <br/> |
|[RotationYAngle](rotationyangle-cell-3-d-rotation-properties-section.md) <br/> |三维旋转属性  <br/> |
|[RotationZAngle](rotationzangle-cell-3-d-rotation-properties-section.md) <br/> |三维旋转属性  <br/> |
|[ShapeShdwBlur](shapeshdwblur-cell-fill-format-section.md) <br/> |填充格式  <br/> |
|[ShapeShdwShow](shapeshdwshow-cell-fill-format-section.md) <br/> |填充格式  <br/> |
|[SketchAmount](sketchamount-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[SketchEnabled](sketchenabled-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[SketchFillChange](sketchfillchange-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[SketchLineChange](sketchlinechange-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[SketchLineWeight](sketchlineweight-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[SketchSeed](sketchseed-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[SoftEdgesSize](softedgessize-cell-additional-effect-properties-section.md) <br/> |其他效果属性  <br/> |
|[ThemeIndex](themeindex-cell-theme-properties-section.md) <br/> |主题属性  <br/> |
|[UseGroupGradient](usegroupgradient-cell-gradient-properties-section.md) <br/> |渐变属性  <br/> |
   
下表列出了 Visio 2013 中已更改的单元格。
  
|**更改的单元格**|**备注**|
|:-----|:-----|
|[ShdwType](shdwtype-cell-page-properties-section.md) <br/> |新值和自动化常量  <br/> |
   
## <a name="new-rows"></a>新行
<a name="vis15_WhatsNew_Rows"> </a>

下表列出了可用于构建 ShapeSheet 解决方案 Visio 2013 中的新行。
  
|**新行**|**Section**|
|:-----|:-----|
|[GradientStop](gradient-stop-row-fill-gradient-section.md) <br/> |填充渐变  <br/> |
|[GradientStop](gradient-stop-row-line-gradient-section.md) <br/> |行渐变  <br/> |
|[RelCubBezTo](relcubbezto-row-geometry-section.md) <br/> |几何图形  <br/> |
|[RelEllipticalArcTo](relellipticalarcto-row-geometry-section.md) <br/> |几何图形  <br/> |
|[RelLineTo](rellineto-row-geometry-section.md) <br/> |几何图形  <br/> |
|[RelMoveTo](relmoveto-row-geometry-section.md) <br/> |几何图形  <br/> |
|[RelQuadBezTo](relquadbezto-row-geometry-section.md) <br/> |几何图形  <br/> |
   
## <a name="new-and-deprecated-functions"></a>新的和已弃用的功能
<a name="vis15_WhatsNew_Functions"> </a>

下表列出了 Visio 2013 中的新功能。
  
|**新函数**|
|:-----|
|[字体](font-function.md) <br/> |
|[ISTHEMED](isthemed-function.md) <br/> |
|[LANGUAGE](language-function.md) <br/> |
|[THEMECBV](themecbv-function.md) <br/> |
||
|[THEMEVAL](themeval-function.md) <br/> |
   
下表列出了 Visio 2013 中弃用的功能。
  
|**已弃用的函数**|**备注**|
|:-----|:-----|
|**CELLISTHEMED** <br/> |由[ISTHEMED](isthemed-function.md)函数取代。  <br/> |
   

