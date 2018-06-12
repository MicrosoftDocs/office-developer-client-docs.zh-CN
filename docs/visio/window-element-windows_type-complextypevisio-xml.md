---
title: 窗口元素 （Windows_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: da776276-e8c2-085b-9b23-e5b1f5ba64cd
description: 代表 Microsoft Visio 实例中打开的窗口。 此元素包含最初由 Visio 在打开文件时完全重新创建应用程序工作区中的用户界面窗口所需的信息。
ms.openlocfilehash: 762b689d625c7865696a0bf8bb8c4acc25e3d8eb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781664"
---
# <a name="window-element-windowstype-complextype-visio-xml"></a>窗口元素 （Windows_Type 复杂类型） (Visio XML)

代表 Microsoft Visio 实例中打开的窗口。 此元素包含最初由 Visio 在打开文件时完全重新创建应用程序工作区中的用户界面窗口所需的信息。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Window_Type](window_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |windows.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Window" type="Window_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Windows](windows-elementvisio-xml.md) <br/> |[Windows_Type](windows_type-complextypevisio-xml.md) <br/> |包含文档的**窗口**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DynamicGridEnabled](dynamicgridenabled-element-window_type-complextypevisio-xml.md) <br/> |[DynamicGridEnabled_Type](dynamicgridenabled_type-complextypevisio-xml.md) <br/> |指定是否为文档或窗口启用动态网格功能。  <br/> |
|[GlueSettings](gluesettings-element-window_type-complextypevisio-xml.md) <br/> |[GlueSettings_Type](gluesettings_type-complextypevisio-xml.md) <br/> |指定当在文档中启用粘附形状粘附到的对象。  <br/> |
|[ShowConnectionPoints](showconnectionpoints-element-window_type-complextypevisio-xml.md) <br/> |[ShowConnectionPoints_Type](showconnectionpoints_type-complextypevisio-xml.md) <br/> |指定是否在窗口中显示连接点。  <br/> |
|[ShowGrid](showgrid-element-window_type-complextypevisio-xml.md) <br/> |[ShowGrid_Type](showgrid_type-complextypevisio-xml.md) <br/> |指定是否在绘图窗口中显示网格。  <br/> |
|[ShowGuides](showguides-element-window_type-complextypevisio-xml.md) <br/> |[ShowGuides_Type](showguides_type-complextypevisio-xml.md) <br/> |指定是否在绘图窗口中显示参考线。  <br/> |
|[ShowPageBreaks](showpagebreaks-element-window_type-complextypevisio-xml.md) <br/> |[ShowPageBreaks_Type](showpagebreaks_type-complextypevisio-xml.md) <br/> |指定是否在窗口中显示分页符。  <br/> |
|[ShowRulers](showrulers-element-window_type-complextypevisio-xml.md) <br/> |[ShowRulers_Type](showrulers_type-complextypevisio-xml.md) <br/> |指定是否在绘图窗口中显示标尺。  <br/> |
|[SnapAngles](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[SnapAngles_Type](snapangles_type-complextypevisio-xml.md) <br/> |包含**SnapAngle**元素的集合。  <br/> |
|[SnapExtensions](snapextensions-element-window_type-complextypevisio-xml.md) <br/> |[SnapExtensions_Type](snapextensions_type-complextypevisio-xml.md) <br/> |指定是否启用或禁用活动窗口的特定管理单元扩展设置。  <br/> |
|[SnapSettings](snapsettings-element-window_type-complextypevisio-xml.md) <br/> |[SnapSettings_Type](snapsettings_type-complextypevisio-xml.md) <br/> |指定形状对齐时对齐位于活动窗口的对象。  <br/> |
|[StencilGroup](stencilgroup-element-window_type-complextypevisio-xml.md) <br/> |[StencilGroup_Type](stencilgroup_type-complextypevisio-xml.md) <br/> |指定合并的模具窗口的窗口是其成员的组。  <br/> |
|[StencilGroupPos](stencilgrouppos-element-window_type-complextypevisio-xml.md) <br/> |[StencilGroupPos_Type](stencilgrouppos_type-complextypevisio-xml.md) <br/> |包含用于指定窗口中的组中的模具的相对位置的整数。  <br/> |
|[TabSplitterPos](tabsplitterpos-element-window_type-complextypevisio-xml.md) <br/> |[TabSplitterPos_Type](tabsplitterpos_type-complextypevisio-xml.md) <br/> |指定绘图窗口的页面选项卡控件的宽度 （以在绘图窗口的总宽度的分数）。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Container  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |容器的 ID： 页、 工作表或主控形状。 仅相关，如果指定**ContainerType**必要。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ContainerType  <br/> |xsd:token  <br/> |可选  <br/> |可以是下列值之一： 文档、 页或主控形状。 仅当**WindowType**指定为绘图或工作表时才可用。  <br/> |Xsd:token 类型的值。  <br/> |
|文档  <br/> |xsd: string  <br/> |可选  <br/> |在此窗口中显示的文档的文件路径。  <br/> |Xsd: string 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|Master  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |如果此窗口将显示主控形状的主控形状 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|Page  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |如果此窗口将显示页面的页面 ID。 相关仅**WindowType**指定为绘图和**ContainerType**指定为页。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ParentWindow  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |在其中包含此模具窗口的窗口的 ID。 仅当**WindowType**指定为模具时才可用。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ReadOnly  <br/> |化  <br/> |可选  <br/> |只读标志如果该模具不是文档模具。  <br/> |化类型的值。  <br/> |
|工作表  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |容器中的工作表的 ID。 仅当容器被指定为工作表时才可用。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ViewCenterX  <br/> |化  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定的新视图 （窗口） 假定最初打开时页面上的中心点。  <br/> |化类型的值。  <br/> |
|ViewCenterY  <br/> |化  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定的新视图 （窗口） 假定最初打开时页面上的中心点。  <br/> |化类型的值。  <br/> |
|ViewScale  <br/> |化  <br/> |可选  <br/> |要打开页上的新视图 （窗口） 时使用的默认显示比例系数。 例如，1 = 100%。1.5 = 150%，依此类推。  <br/> |化类型的值。  <br/> |
|WindowHeight  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |窗口矩形的高度。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|WindowLeft  <br/> |xsd:short  <br/> |可选  <br/> |窗口矩形左边缘的坐标。  <br/> |Xsd:short 类型的值。  <br/> |
|WindowState  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |整数，指定位标志。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|WindowTop  <br/> |xsd:short  <br/> |可选  <br/> |窗口矩形顶部坐标。  <br/> |Xsd:short 类型的值。  <br/> |
|WindowType  <br/> |xsd:token  <br/> |必需  <br/> |枚举的值可能是以下项之一： 绘图、 工作表、 模具或图标。  <br/> |Xsd:token 类型的值。  <br/> |
|WindowWidth  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |窗口矩形的宽度。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

