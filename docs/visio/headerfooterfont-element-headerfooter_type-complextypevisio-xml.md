---
title: HeaderFooterFont 元素 （HeaderFooter_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4e69dd4f-7281-e988-b1fd-93ac8c775c03
description: 指定用于页眉和页脚文本的字体。
ms.openlocfilehash: f14d973caddc77394881d1b1dfd62a43f10cd7bb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385968"
---
# <a name="headerfooterfont-element-headerfootertype-complextype-visio-xml"></a>HeaderFooterFont 元素 （HeaderFooter_Type 复杂类型） (Visio XML)

指定用于页眉和页脚文本的字体。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[HeaderFooterFont_Type](headerfooterfont_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="HeaderFooterFont" type="HeaderFooterFont_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[HeaderFooter](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[HeaderFooter_Type](headerfooter_type-complextypevisio-xml.md) <br/> |包含文档的页眉和页脚的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|字符集  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定字体的字符集。 等效于 GDI LOGFONTlfCharSet 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|ClipPrecision  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定字体的剪辑精度。 等效于 GDI LOGFONTlfClipPrecision 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|行距  <br/> |xsd:int  <br/> |可选  <br/> |指定字体的行距属性。 等效于 GDI LOGFONTlfEscapement 域。  <br/> |Xsd:int 类型的值。  <br/> |
|FaceName  <br/> |xsd: string  <br/> |可选  <br/> |包含有关字体的信息。  <br/> |Xsd: string 类型的值。  <br/> |
|高度  <br/> |xsd:int  <br/> |可选  <br/> |以绘图单位表示指定形状的高度。  <br/> |Xsd:int 类型的值。  <br/> |
|斜体  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定字体是否为斜体。 等效于 GDI LOGFONTlfItalic 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|Orientation  <br/> |xsd:int  <br/> |可选  <br/> |指定字体的方向。 等效于 GDI LOGFONTlfOrientation 域。  <br/> |Xsd:int 类型的值。  <br/> |
|OutPrecision  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定字体的输出精度属性。 等效于 GDI LOGFONTlfOutPrecision 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|PitchAndFamily  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定的间距和字体的系列。 等效于 GDI LOGFONTlfPitchAndFamily 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|质量  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定字体的输出质量。 等效于 GDI LOGFONTlfQuality 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|删除线  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定字体是否删除线字体。 等效于 GDI LOGFONTlfStrikeOut 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|下划线  <br/> |xsd:unsignedByte  <br/> |可选  <br/> |指定字体是否加下划线。 等效于 GDI LOGFONTlfUnderline 域。  <br/> |Xsd:unsignedByte 类型的值。  <br/> |
|权重  <br/> |xsd:int  <br/> |可选  <br/> |指定字体的权重。 等效于 GDI LOGFONTlfWeight 域。  <br/> |Xsd:int 类型的值。  <br/> |
|宽度  <br/> |xsd:int  <br/> |可选  <br/> |包含以绘图单位表示的关联形状的宽度。  <br/> |Xsd:int 类型的值。  <br/> |
   

