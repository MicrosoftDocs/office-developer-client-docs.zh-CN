---
title: 'Master 元素 (Masters_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c102fd71-c621-2bde-9fbb-8e9203fdf31e
description: 包含定义文档主控文档的元素。
ms.openlocfilehash: 83727b89eaf44aae5dddecacff1f05f369ee0bf0
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538044"
---
# <a name="master-element-masters_type-complextype-visio-xml"></a>Master 元素 (Masters_Type COMPLEXType)  (Visio XML) 

包含定义文档主控文档的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Master_Type](master_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Master" type="Master_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Masters](masters-elementvisio-xml.md) <br/> |[Masters_Type](masters_type-complextypevisio-xml.md) <br/> |包含 **文档的 Master** 元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Connects](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Connects_Type](connects_type-complextypevisio-xml.md) <br/> |包含一 **连接** 图形中两个形状之间的每个连接的一个属性元素。  <br/> |
|[Icon](icon-element-master_type-complextypevisio-xml.md) <br/> |[Icon_Type](icon_type-complextypevisio-xml.md) <br/> |指定 MIME (Master 或 **MasterShortcut** 元素的 MIME) 编码的二进制图标 (，格式为 .ico ) 。  <br/> |
|[PageSheet](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |包含定义 Page 或 Master 元素的页面 **工作表****的元素。**  <br/> |
|形状  <br/> |Shapes_Type  <br/> |包含 Shape **元素的集合** 。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlignName  <br/> |xsd：unsignedShort  <br/> |可选  <br/> |指定模具窗口中主控图形的文本是左对齐、右对齐还是居中对齐。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|BaseID  <br/> |xsd：string  <br/> |可选  <br/> |GUID (标识文档) 全局唯一标识符。  <br/> |xsd：string 类型的值。  <br/> |
|Hidden  <br/> |xsd：boolean  <br/> |可选  <br/> |指定主控母版是否在用户界面中隐藏。  <br/> |xsd：boolean 类型的值。  <br/> |
|IconSize  <br/> |xsd：unsignedShort  <br/> |可选  <br/> |元素图标的大小。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|IconUpdate  <br/> |xsd：boolean  <br/> |可选  <br/> |指定是否从主控母版本身自动生成图标。  <br/> |xsd：boolean 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|MatchByName  <br/> |xsd：boolean  <br/> |可选  <br/> |确定 Microsoft Visio在绘图页上删除主控母版的实例时，如何决定文档主控文档是否已经存在。  <br/> |xsd：boolean 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd：string 类型的值。  <br/> |
|NameU  <br/> |xsd：string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd：string 类型的值。  <br/> |
|PatternFlags  <br/> |xsd：unsignedShort  <br/> |可选  <br/> |确定主控形状是否表现为自定义图案。  <br/> |xsd：unsignedShort 类型的值。  <br/> |
|Prompt  <br/> |xsd：string  <br/> |可选  <br/> |元素的状态栏和工具提示提示。  <br/> |xsd：string 类型的值。  <br/> |
|UniqueID  <br/> |xsd：string  <br/> |可选  <br/> |标识文档中主控母版的 GUID。  <br/> |xsd：string 类型的值。  <br/> |
   

