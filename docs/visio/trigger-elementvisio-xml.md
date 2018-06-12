---
title: Trigger 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d897d2d1-25ba-48d7-b87e-d3c533d88c15
description: 提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。
ms.openlocfilehash: 909fff3ccec176cd3ce327fc208c176a68764fe3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781567"
---
# <a name="trigger-element-visio-xml"></a>Trigger 元素 (Visio XML)

提供对 Microsoft Visio 重新计算 Visio 文件中的文档部件之间的关系的说明。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Trigger_Type](trigger_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |母版页 #.xml、 页面 #.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="Trigger" type="Trigger_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定单元格元素能够提供程序的形状定义的信息。  <br/> |
|[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSheet_Type](documentsheet_type-complextypevisio-xml.md) <br/> |定义的 DocumentSheet 结构。  <br/> |
|[样式表](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[StyleSheet_Type](stylesheets_type-complextypevisio-xml.md) <br/> |表示在文档中定义的样式。  <br/> |
|[PageSheet （Master_Type 复杂类型）](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定绘图页主控形状相关联的属性。  <br/> |
|[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定绘图页在绘图页相关联的属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-trigger_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定绘图中的参考 toa 页。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|N  <br/> |xsd: string  <br/> |必需  <br/> |公式中要触发激活时调用的名称。  <br/> 请参阅备注部分。  <br/> |Xsd: string 类型的值。  <br/> |
   
## <a name="remarks"></a>备注

此**Trigger**元素的**N**属性必须为一组有限的对应于触发器说明的值之一。 请参阅下表为确定允许此**触发器**元素的**N**属性的值。 
  
|**值**|**父元素**|**说明**|
|:-----|:-----|:-----|
|CategoryChanged  <br/> |[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |将出现在形状使用**HASCATEGORIES**函数的跨部件引用时触发存在。  <br/> |
|RecalcBkgPageName  <br/> |[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |当存在使用**BKGPAGENAME**函数的跨部件引用页面上出现触发器  <br/> |
|RecalcColor  <br/> |[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |页面显示的页面或任何及其包含的形状使用**RGB**函数时触发。  <br/> |
|RecalcCreateDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |显示文档时使用**DOCCREATION**函数的跨部件引用触发器存在。  <br/> |
|RecalcData1  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |将出现在形状使用**DATA1**函数的跨部件引用时触发存在。  <br/> |
|RecalcData2  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |将出现在形状使用**DATA2**函数的跨部件引用时触发存在。  <br/> |
|RecalcData3  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |将出现在形状使用**DATA3**函数的跨部件引用时触发存在。  <br/> |
|RecalcEditDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |显示文档时使用**DOCLASTEDIT**函数的跨部件引用触发器存在。  <br/> |
|RecalcID  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |将出现在形状**ID**函数使用的跨部件引用时触发存在。  <br/> |
|RecalcMasterName  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |将出现在形状使用**MASTERNAME**函数的跨部件引用时触发存在。  <br/> |
|RecalcName  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |使用**NAME**函数的跨部件引用存在时将出现在形状触发。  <br/> |
|RecalcNowAndRand  <br/> |[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |如果的页面或任何及其包含的形状有**现在**或**RAND**函数显示在页面触发。  <br/> |
|RecalcPageCount  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |显示文档时使用**PAGECOUNT**函数的跨部件引用触发器存在。  <br/> |
|RecalcPageName  <br/> |[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> [形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |将出现在形状使用**PAGENAME**函数的跨部件引用时触发存在。  <br/> |
|RecalcPageNum  <br/> |[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |显示在页，使用**PAGENUMBER**函数的跨部件引用存在时触发。  <br/> |
|RecalcPath  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |将出现在形状使用**POINTALONGPATH**、 **PATHLENGTH**或**PATHSEGMENT**函数的跨部件引用时触发存在。  <br/> |
|RecalcPrintDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |显示文档时使用**DOCLASTPRINT**函数的跨部件引用触发器存在。  <br/> |
|RecalcSaveDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |显示文档时使用**DOCLASTSAVE**函数的跨部件引用触发器存在。  <br/> |
|RecalcSummary  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |显示文档时使用的**类别**、 **CREATOR**、**说明**、**关键字**、**主题**或**标题**函数的跨部件引用触发器存在。  <br/> |
|RecalcType  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |使用**类型**函数的跨部件引用存在时将出现在形状触发。  <br/> |
|RelChanged  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |将出现在形状使用**CONTAINERMEMBERCOUNT**函数的跨部件引用时触发存在。  <br/> |
|ZOrderChanged  <br/> |[PageSheet （Page_Type 复杂类型）](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |显示在页，使用**CONTAINERSHEETREF**函数的跨部件引用存在时触发。  <br/> |
|路径  <br/> |[形状](shape-element-shapes_type-complextypevisio-xml.md) <br/> |出现在页上，使用**POINTALONGPATH**、 **PATHLENGTH**或**PATHSEGMENT**函数的跨部件引用时触发存在。  <br/> |
   

