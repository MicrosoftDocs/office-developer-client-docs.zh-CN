---
title: 'DocumentSettings 元素 (VisioDocument_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46712e1f-4e02-974f-c224-85db47666ae1
description: 包含指定文档设置的元素。
ms.openlocfilehash: 0d8e0809afae7b3de059166343577bb58f0eb01b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540068"
---
# <a name="documentsettings-element-visiodocument_type-complextype-visio-xml"></a>DocumentSettings 元素 (VisioDocument_Type COMPLEXType)  (Visio XML) 

包含指定文档设置的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DocumentSettings_Type](documentsettings_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DocumentSettings" type="DocumentSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[VisioDocument](visiodocument-elementvisio-xml.md) <br/> |[VisioDocument_Type](visiodocument_type-complextypevisio-xml.md) <br/> |Microsoft 文档库Visio元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[AttachedToolbars](attachedtoolbars-element-documentsettings_type-complextypevisio-xml.md) <br/> |[AttachedToolbars_Type](attachedtoolbars_type-complextypevisio-xml.md) <br/> |MIME (VSU) 文件（) 自定义工具栏的 VSU Visio用户界面 (MIME) 多用途 Internet 邮件扩展）。  <br/> |
|[CustomMenusFile](custommenusfile-element-documentsettings_type-complextypevisio-xml.md) <br/> |[CustomMenusFile_Type](custommenusfile_type-complextypevisio-xml.md) <br/> |包含定义文档的自定义菜单Visio快捷方式的 Microsoft Visio (.vsu) 文件的名称。  <br/> |
|[CustomToolbarsFile](customtoolbarsfile-element-documentsettings_type-complextypevisio-xml.md) <br/> |[CustomToolbarsFile_Type](customtoolbarsfile_type-complextypevisio-xml.md) <br/> |包含 Microsoft Visio用户界面 (.vsu) 文件的名称，该文件定义文档的自定义工具栏和状态栏。  <br/> |
|[DynamicGridEnabled](dynamicgridenabled-element-documentsettings_type-complextypevisio-xml.md) <br/> |[DynamicGridEnabled_Type](dynamicgridenabled_type-complextypevisio-xml.md) <br/> |指定是否对文档或窗口启用动态网格功能。  <br/> |
|[GlueSettings](gluesettings-element-documentsettings_type-complextypevisio-xml.md) <br/> |[GlueSettings_Type](gluesettings_type-complextypevisio-xml.md) <br/> |指定在文档中启用粘附时形状粘附到的对象。  <br/> |
|[ProtectBkgnds](protectbkgnds-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectBkgnds_Type](protectbkgnds_type-complextypevisio-xml.md) <br/> |指定是否阻止用户删除或编辑背景页。  <br/> |
|[ProtectMasters](protectmasters-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectMasters_Type](protectmasters_type-complextypevisio-xml.md) <br/> |指定是否阻止用户创建、编辑或删除主文件。 无论此设置如何，用户仍可以创建主对象的实例。  <br/> |
|[ProtectShapes](protectshapes-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectShapes_Type](protectshapes_type-complextypevisio-xml.md) <br/> |指定是否阻止用户选择其 **LockSelect** 元素设置为 1 的形状。  <br/> |
|[ProtectStyles](protectstyles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[ProtectStyles_Type](protectstyles_type-complextypevisio-xml.md) <br/> |指定是否阻止用户创建或编辑样式。  <br/> |
|[SnapAngles](snapangles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[SnapAngles_Type](snapangles_type-complextypevisio-xml.md) <br/> |包含 **SnapAngle 元素** 的集合。  <br/> |
|[SnapExtensions](snapextensions-element-documentsettings_type-complextypevisio-xml.md) <br/> |[SnapExtensions_Type](snapextensions_type-complextypevisio-xml.md) <br/> |指定是启用还是禁用活动窗口的特定对齐扩展设置。  <br/> |
|[SnapSettings](snapsettings-element-documentsettings_type-complextypevisio-xml.md) <br/> |[SnapSettings_Type](snapsettings_type-complextypevisio-xml.md) <br/> |指定当窗口中的对齐处于活动状态时形状所对齐的对象。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|DefaultFillStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定 **StyleSheet** 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|DefaultGuideStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定 **StyleSheet** 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|DefaultLineStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定 **StyleSheet** 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|DefaultTextStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定 **StyleSheet** 元素的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|TopPage  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定 Microsoft 文档打开时应显示的页面的 ID Visio。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
   

