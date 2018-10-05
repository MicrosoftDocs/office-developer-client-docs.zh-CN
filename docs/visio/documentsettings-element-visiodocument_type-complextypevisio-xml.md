---
title: DocumentSettings 元素 （VisioDocument_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46712e1f-4e02-974f-c224-85db47666ae1
description: 包含指定文档设置的元素。
ms.openlocfilehash: e86dc5a0875006cb8bd1bbaffd36037a07fd5c0f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396465"
---
# <a name="documentsettings-element-visiodocumenttype-complextype-visio-xml"></a>DocumentSettings 元素 （VisioDocument_Type 复杂类型） (Visio XML)

包含指定文档设置的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DocumentSettings_Type](documentsettings_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DocumentSettings" type="DocumentSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
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
|[AttachedToolbars](attachedtoolbars-element-documentsettings_type-complextypevisio-xml.md) <br/> |[AttachedToolbars_Type](attachedtoolbars_type-complextypevisio-xml.md) <br/> |MIME （多用途 Internet 邮件扩展） 编码表示自定义工具栏的 Microsoft Visio 用户界面 (VSU) 文件。  <br/> |
|[CustomMenusFile](custommenusfile-element-documentsettings_type-complextypevisio-xml.md) <br/> |[CustomMenusFile_Type](custommenusfile_type-complextypevisio-xml.md) <br/> |包含定义自定义菜单和加速键的文档的 Microsoft Visio 用户界面 (.vsu) 文件的名称。  <br/> |
|[CustomToolbarsFile](customtoolbarsfile-element-documentsettings_type-complextypevisio-xml.md) <br/> |[CustomToolbarsFile_Type](customtoolbarsfile_type-complextypevisio-xml.md) <br/> |包含定义自定义工具栏和状态栏文档的 Microsoft Visio 用户界面 (.vsu) 文件的名称。  <br/> |
|[DynamicGridEnabled](dynamicgridenabled-element-documentsettings_type-complextypevisio-xml.md) <br/> |[DynamicGridEnabled_Type](dynamicgridenabled_type-complextypevisio-xml.md) <br/> |指定是否为文档或窗口启用动态网格功能。  <br/> |
|[GlueSettings](gluesettings-element-documentsettings_type-complextypevisio-xml.md) <br/> |[GlueSettings_Type](gluesettings_type-complextypevisio-xml.md) <br/> |指定当在文档中启用粘附形状粘附到的对象。  <br/> |
|[ProtectBkgnds](protectbkgnds-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectBkgnds_Type](protectbkgnds_type-complextypevisio-xml.md) <br/> |指定是否禁止用户删除或编辑背景页。  <br/> |
|[ProtectMasters](protectmasters-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectMasters_Type](protectmasters_type-complextypevisio-xml.md) <br/> |指定是否禁止用户创建、 编辑或删除主控形状。 此设置，无论用户仍可以创建主控形状的实例。  <br/> |
|[ProtectShapes](protectshapes-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectShapes_Type](protectshapes_type-complextypevisio-xml.md) <br/> |指定是否禁止用户选择已设置为 1 其**LockSelect**元素的形状。  <br/> |
|[ProtectStyles](protectstyles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectStyles_Type](protectstyles_type-complextypevisio-xml.md) <br/> |指定是否禁止用户创建或编辑样式。  <br/> |
|[SnapAngles](snapangles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[SnapAngles_Type](snapangles_type-complextypevisio-xml.md) <br/> |包含**SnapAngle**元素的集合。  <br/> |
|[SnapExtensions](snapextensions-element-documentsettings_type-complextypevisio-xml.md) <br/> |[SnapExtensions_Type](snapextensions_type-complextypevisio-xml.md) <br/> |指定是否启用或禁用活动窗口的特定管理单元扩展设置。  <br/> |
|[SnapSettings](snapsettings-element-documentsettings_type-complextypevisio-xml.md) <br/> |[SnapSettings_Type](snapsettings_type-complextypevisio-xml.md) <br/> |指定形状对齐时对齐位于活动窗口的对象。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|DefaultFillStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定**样式表**元素的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|DefaultGuideStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定**样式表**元素的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|DefaultLineStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定**样式表**元素的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|DefaultTextStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定**样式表**元素的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|TopPage  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定由 Microsoft Visio 在打开文档时应显示的页面的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

