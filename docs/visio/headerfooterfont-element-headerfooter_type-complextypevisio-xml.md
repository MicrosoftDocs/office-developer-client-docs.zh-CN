---
title: 'HeaderFooterFont 元素 (HeaderFooter_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4e69dd4f-7281-e988-b1fd-93ac8c775c03
description: 指定用于页眉和页脚文本的字体。
ms.openlocfilehash: b87ba96d551bf943dd330aa428f2c943c9d29269
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541083"
---
# <a name="headerfooterfont-element-headerfooter_type-complextype-visio-xml"></a>HeaderFooterFont 元素 (HeaderFooter_Type COMPLEXType)  (Visio XML) 

指定用于页眉和页脚文本的字体。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[HeaderFooterFont_Type](headerfooterfont_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="HeaderFooterFont" type="HeaderFooterFont_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[HeaderFooter](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[HeaderFooter_Type](headerfooter_type-complextypevisio-xml.md) <br/> |包含文档页眉和页脚的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|CharSet  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体的字符集。 相当于"GDI LOGFONTlfCharSet"字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|ClipPrecision  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体的剪裁精度。 相当于"GDI LOGFONTlfClipPrecision"字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|转义  <br/> |xsd：int  <br/> |可选  <br/> |指定字体的转义属性。 相当于 GDI LOGFONTlfEscapement 字段。  <br/> |xsd：int 类型的值。  <br/> |
|FaceName  <br/> |xsd：string  <br/> |可选  <br/> |包含有关字体的信息。  <br/> |xsd：string 类型的值。  <br/> |
|Height  <br/> |xsd：int  <br/> |可选  <br/> |指定形状的高度（以绘图单位表示）。  <br/> |xsd：int 类型的值。  <br/> |
|斜体  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体是否为 italic。 相当于 GDI LOGFONTlfItalic 字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|Orientation  <br/> |xsd：int  <br/> |可选  <br/> |指定字体的方向。 相当于 GDI LOGFONTlfOrientation 字段。  <br/> |xsd：int 类型的值。  <br/> |
|OutPrecision  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体的输出精度属性。 相当于"GDI LOGFONTlfOutPrecision"字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|PitchAndFamily  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体的俯仰和系列。 相当于 GDI LOGFONTlfPitchAndFamily 字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|质量  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体的输出质量。 相当于"GDI LOGFONTlfQuality"字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|StrikeOut  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体是否是删除线字体。 相当于"GDI LOGFONTlfStrikeOut"字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|下划线  <br/> |xsd：unsignedByte  <br/> |可选  <br/> |指定字体是否带下划线。 相当于"GDI LOGFONTlfUnderline"字段。  <br/> |xsd：unsignedByte 类型的值。  <br/> |
|粗细  <br/> |xsd：int  <br/> |可选  <br/> |指定字体的粗细。 相当于"GDI LOGFONTlfWeight"字段。  <br/> |xsd：int 类型的值。  <br/> |
|Width  <br/> |xsd：int  <br/> |可选  <br/> |包含关联形状的宽度（以绘图单位表示）。  <br/> |xsd：int 类型的值。  <br/> |
   

