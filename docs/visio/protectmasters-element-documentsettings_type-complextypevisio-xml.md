---
title: 'ProtectMasters 元素 (DocumentSettings_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: edc46630-c320-6b4e-4747-961075dd5fd7
description: 指定是否阻止用户创建、编辑或删除主控形状。 用户仍可从主控形状创建新形状，无论此设置如何。
ms.openlocfilehash: 34ace8c873b133f44ea7bd7c9c2e4127a103a760
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540691"
---
# <a name="protectmasters-element-documentsettings_type-complextype-visio-xml"></a>ProtectMasters 元素 (DocumentSettings_Type COMPLEXType)  (Visio XML) 

指定是否阻止用户创建、编辑或删除主控形状。 用户仍可从主控形状创建新形状，无论此设置如何。 
  
此元素的可能值的范围是"0"或"1"。 值"0"指示用户可以创建、编辑或删除主控形状。 值"1"指示用户无法创建、编辑或删除主控形状。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[ProtectMasters_Type](protectmasters_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="ProtectMasters" type="ProtectMasters_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DocumentSettings](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSettings_Type](documentsettings_type-complextypevisio-xml.md) <br/> |包含指定文档设置的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>Attributes

无。
  

