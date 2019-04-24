---
title: Trigger 元素 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d897d2d1-25ba-48d7-b87e-d3c533d88c15
description: 提供 Microsoft Visio 的说明, 以重新计算 Visio 文件中的文档部件之间的关系。
ms.openlocfilehash: a590ec1f9c19270f75d4d9e77804c0a7b45157b6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280848"
---
# <a name="trigger-element-visio-xml"></a>Trigger 元素 ("Visio XML")

提供 Microsoft Visio 的说明, 以重新计算 Visio 文件中的文档部件之间的关系。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Trigger_Type](trigger_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |master # .xml、第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="Trigger" type="Trigger_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定为形状定义提供信息的单元格元素。  <br/> |
|[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSheet_Type](documentsheet_type-complextypevisio-xml.md) <br/> |定义 DocumentSheet 结构。  <br/> |
|[单](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[StyleSheet_Type](stylesheets_type-complextypevisio-xml.md) <br/> |表示在文档中定义的样式。  <br/> |
|[PageSheet (Master_Type 复杂类型)](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定与主控形状相关联的绘图页的属性。  <br/> |
|[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定与绘图页相关联的绘图页的属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-trigger_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定绘图中的引用 toa 页面。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|N  <br/> |xsd: string  <br/> |必需  <br/> |激活触发器时要调用的公式的名称。  <br/> 请参阅 "备注" 部分。  <br/> |xsd: string 类型的值。  <br/> |
   
## <a name="remarks"></a>注解

此**Trigger**元素的**N**属性必须是与触发器指令对应的一组有限的值。 请参阅下表, 以确定此**Trigger**元素允许的**N**个属性的值。 
  
|**值**|**父元素**|**Description**|
|:-----|:-----|:-----|
|CategoryChanged  <br/> |[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |当存在使用**HASCATEGORIES**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcBkgPageName  <br/> |[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |当存在使用**BKGPAGENAME**函数的交叉部件引用时, 出现在页面上的触发器  <br/> |
|RecalcColor  <br/> |[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |每当页面或其包含的任何形状使用**RGB**函数时, 都会出现在页面上的触发器。  <br/> |
|RecalcCreateDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用**DOCCREATION**函数的交叉部件引用时, 将在文档中出现的触发器。  <br/> |
|RecalcData1  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**DATA1**函数的跨部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcData2  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**DATA2**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcData3  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**DATA3**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcEditDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用**DOCLASTEDIT**函数的交叉部件引用时, 将在文档中出现的触发器。  <br/> |
|RecalcID  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**ID**函数的交叉部件引用时, 将出现在形状上的触发器。  <br/> |
|RecalcMasterName  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**MASTERNAME**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcName  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**NAME**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcNowAndRand  <br/> |[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |如果页面或其包含的任何形状有**NOW**或**RAND**函数, 则会出现在页面上的触发器。  <br/> |
|RecalcPageCount  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用**PAGECOUNT**函数的交叉部件引用时, 将在文档中出现的触发器。  <br/> |
|RecalcPageName  <br/> |[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> [Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**PAGENAME**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcPageNum  <br/> |[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |当存在使用**PAGENUMBER**函数的交叉部件引用时, 将出现在页面上的触发器。  <br/> |
|RecalcPath  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用**POINTALONGPATH**、 **PATHLENGTH**或**PATHSEGMENT**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RecalcPrintDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用**DOCLASTPRINT**函数的交叉部件引用时, 将在文档中出现的触发器。  <br/> |
|RecalcSaveDT  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当存在使用**DOCLASTSAVE**函数的交叉部件引用时, 将在文档中出现的触发器。  <br/> |
|RecalcSummary  <br/> |[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |当使用**类别**、**创建者**、**说明**、**关键字**、**主题**或**标题**函数时, 在文档中出现的触发器。  <br/> |
|RecalcType  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**类型**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|RelChanged  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**CONTAINERMEMBERCOUNT**函数的交叉部件引用时, 将在形状上出现的触发器。  <br/> |
|ZOrderChanged  <br/> |[PageSheet (Page_Type 复杂类型)](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |当存在使用**CONTAINERSHEETREF**函数的交叉部件引用时, 将出现在页面上的触发器。  <br/> |
|Path  <br/> |[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |当存在使用**POINTALONGPATH**、 **PATHLENGTH**或**PATHSEGMENT**函数的交叉部件引用时, 将出现在页面上的触发器。  <br/> |
   

