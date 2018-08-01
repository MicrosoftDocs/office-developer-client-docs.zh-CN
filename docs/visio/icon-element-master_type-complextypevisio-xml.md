---
title: 图标元素 （Master_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 80061e7d-dbcb-f7a1-b63a-052eee4ec7d7
description: 指定的 MIME （多用途 Internet 邮件扩展） 编码为主控形状的二进制图标 （.ico 格式） 文档中的元素。
ms.openlocfilehash: 0c3d13db9c0f712067619e953441f2ebdfadf4c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780445"
---
# <a name="icon-element-mastertype-complextype-visio-xml"></a>图标元素 （Master_Type 复杂类型） (Visio XML)

指定的 MIME （多用途 Internet 邮件扩展） 编码为主控形状的二进制图标 （.ico 格式） 文档中的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Icon_Type](icon_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Icon" type="Icon_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Master](master-element-masters_type-complextypevisio-xml.md) <br/> |[Master_Type](master_type-complextypevisio-xml.md) <br/> |指定与绘图中的主控形状。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

无。
  

