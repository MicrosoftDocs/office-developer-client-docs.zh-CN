---
title: HeaderFooter 元素 （VisioDocument_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 026926cf-3d0b-984c-897e-9d28346b7ba7
description: 包含文档的页眉和页脚的元素。
ms.openlocfilehash: eabb19100c4b37a546c0a271cfba5a0c865a7e83
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384442"
---
# <a name="headerfooter-element-visiodocumenttype-complextype-visio-xml"></a>HeaderFooter 元素 （VisioDocument_Type 复杂类型） (Visio XML)

包含文档的页眉和页脚的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[HeaderFooter_Type](headerfooter_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="HeaderFooter" type="HeaderFooter_Type" minOccurs="0" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[VisioDocument](visiodocument-elementvisio-xml.md) <br/> |[VisioDocument_Type](visiodocument_type-complextypevisio-xml.md) <br/> |Microsoft Visio 文档的根元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[FooterCenter](footercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[FooterCenter_Type](footercenter_type-complextypevisio-xml.md) <br/> |包含文档页脚的中心部分显示的文本字符串。  <br/> |
|[FooterLeft](footerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[FooterLeft_Type](footerleft_type-complextypevisio-xml.md) <br/> |包含的文档的页脚部分中显示的文本字符串。  <br/> |
|[FooterMargin](footermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[FooterMargin_Type](footermargin_type-complextypevisio-xml.md) <br/> |指定文档的页脚的边距。  <br/> |
|[FooterRight](footerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[FooterRight_Type](footerright_type-complextypevisio-xml.md) <br/> |包含文档页脚的右侧部分显示的文本字符串。  <br/> |
|[HeaderCenter](headercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[HeaderCenter_Type](headercenter_type-complextypevisio-xml.md) <br/> |包含文档页眉的中心部分显示的文本字符串。  <br/> |
|[HeaderFooterFont](headerfooterfont-element-headerfooter_type-complextypevisio-xml.md) <br/> |[HeaderFooterFont_Type](headerfooterfont_type-complextypevisio-xml.md) <br/> |指定用于页眉和页脚文本的字体。  <br/> |
|[HeaderLeft](headerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[HeaderLeft_Type](headerleft_type-complextypevisio-xml.md) <br/> |包含文档页眉的左侧部分显示的文本字符串。  <br/> |
|[HeaderMargin](headermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[HeaderMargin_Type](headermargin_type-complextypevisio-xml.md) <br/> |指定文档的页眉的边距。  <br/> |
|[HeaderRight](headerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[HeaderRight_Type](headerright_type-complextypevisio-xml.md) <br/> |包含文档页眉的右侧部分显示的文本字符串。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|HeaderFooterColor  <br/> |xsd: string  <br/> |可选  <br/> |页眉和页脚以十六进制; 的文本颜色的 RGB 值例如，#rrggbb。  <br/> |Xsd: string 类型的值。  <br/> |
   

