---
title: 'PublishedPage 元素 (PublishSettings_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c1eca66b-5840-790a-459f-e06680d11c05
description: 指定在 2013 年 3 月，是否使用 Visio Services 在浏览器中Microsoft SharePoint Server页面。
ms.openlocfilehash: 614c01f12b9a7525620704e5417a106e8703c983
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538373"
---
# <a name="publishedpage-element-publishsettings_type-complextype-visio-xml"></a>PublishedPage 元素 (PublishSettings_Type complexType)  (Visio XML) 

指定在 2013 年 3 月，是否使用 Visio Services 在浏览器中Microsoft SharePoint Server页面。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[PublishedPage_Type](publishedpage_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="PublishedPage" type="PublishedPage_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[PublishSettings](publishsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[PublishSettings_Type](publishsettings_type-complextypevisio-xml.md) <br/> |指定使用 Visio Services 打开图表时所使用的设置。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |绘图页的标识符。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
   

