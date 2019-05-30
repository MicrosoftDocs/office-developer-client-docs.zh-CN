---
title: Window 元素 (Windows_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: da776276-e8c2-085b-9b23-e5b1f5ba64cd
description: 代表 Microsoft Visio 实例中打开的窗口。 此元素包含必要的信息, 以便在 Visio 最初打开文件时, 在应用程序工作区中完全重新创建一个用户界面窗口。
ms.openlocfilehash: 2700ee7a9a17460f6ac707f5b1a8f35d622e33e3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538457"
---
# <a name="window-element-windowstype-complextype-visio-xml"></a>Window 元素 (Windows_Type 复杂类型) (Visio XML)

代表 Microsoft Visio 实例中打开的窗口。 此元素包含必要的信息, 以便在 Visio 最初打开文件时, 在应用程序工作区中完全重新创建一个用户界面窗口。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Window_Type](window_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |windows .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Window" type="Window_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Windows](windows-elementvisio-xml.md) <br/> |[Windows_Type](windows_type-complextypevisio-xml.md) <br/> |包含文档的**Window**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DynamicGridEnabled](dynamicgridenabled-element-window_type-complextypevisio-xml.md) <br/> |[DynamicGridEnabled_Type](dynamicgridenabled_type-complextypevisio-xml.md) <br/> |指定是否对文档或窗口启用动态网格功能。  <br/> |
|[GlueSettings](gluesettings-element-window_type-complextypevisio-xml.md) <br/> |[GlueSettings_Type](gluesettings_type-complextypevisio-xml.md) <br/> |指定在文档中启用粘附时形状粘附到的对象。  <br/> |
|[ShowConnectionPoints](showconnectionpoints-element-window_type-complextypevisio-xml.md) <br/> |[ShowConnectionPoints_Type](showconnectionpoints_type-complextypevisio-xml.md) <br/> |指定是否在窗口中显示连接点。  <br/> |
|[ShowGrid](showgrid-element-window_type-complextypevisio-xml.md) <br/> |[ShowGrid_Type](showgrid_type-complextypevisio-xml.md) <br/> |指定是否在绘图窗口中显示网格。  <br/> |
|[ShowGuides](showguides-element-window_type-complextypevisio-xml.md) <br/> |[ShowGuides_Type](showguides_type-complextypevisio-xml.md) <br/> |指定是否在绘图窗口中显示参考线。  <br/> |
|[ShowPageBreaks](showpagebreaks-element-window_type-complextypevisio-xml.md) <br/> |[ShowPageBreaks_Type](showpagebreaks_type-complextypevisio-xml.md) <br/> |指定是否在窗口中显示分页符。  <br/> |
|[ShowRulers](showrulers-element-window_type-complextypevisio-xml.md) <br/> |[ShowRulers_Type](showrulers_type-complextypevisio-xml.md) <br/> |指定是否在绘图窗口中显示标尺。  <br/> |
|[SnapAngles](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[SnapAngles_Type](snapangles_type-complextypevisio-xml.md) <br/> |包含**SnapAngle**元素的集合。  <br/> |
|[SnapExtensions](snapextensions-element-window_type-complextypevisio-xml.md) <br/> |[SnapExtensions_Type](snapextensions_type-complextypevisio-xml.md) <br/> |指定是否为活动窗口启用或禁用特定的快照扩展设置。  <br/> |
|[SnapSettings](snapsettings-element-window_type-complextypevisio-xml.md) <br/> |[SnapSettings_Type](snapsettings_type-complextypevisio-xml.md) <br/> |指定在窗口中的 "对齐" 处于活动状态时, 形状将对齐到的对象。  <br/> |
|[StencilGroup](stencilgroup-element-window_type-complextypevisio-xml.md) <br/> |[StencilGroup_Type](stencilgroup_type-complextypevisio-xml.md) <br/> |指定窗口所属的合并模具窗口的组。  <br/> |
|[StencilGroupPos](stencilgrouppos-element-window_type-complextypevisio-xml.md) <br/> |[StencilGroupPos_Type](stencilgrouppos_type-complextypevisio-xml.md) <br/> |包含一个 integer 类型的值, 该值指定模具在窗口中的组内的相对位置。  <br/> |
|[TabSplitterPos](tabsplitterpos-element-window_type-complextypevisio-xml.md) <br/> |[TabSplitterPos_Type](tabsplitterpos_type-complextypevisio-xml.md) <br/> |指定绘图窗口的页面选项卡控件的宽度 (作为绘图窗口总宽度的一小部分)。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Container  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |容器: 页、工作表或主控形状的 ID。 仅当指定**ContainerType**时才相关且必要。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|ContainerType  <br/> |xsd: token  <br/> |可选  <br/> |可以是下列值之一: 文档、页面或主控形状。 仅在将**WindowType**指定为绘图或工作表时相关。  <br/> |Xsd: 令牌类型的值。  <br/> |
|Document  <br/> |xsd: string  <br/> |可选  <br/> |此窗口中显示的文档的文件路径。  <br/> |Xsd: string 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|Master  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |主 ID (如果此窗口显示母版)。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|Page  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |如果此窗口显示页面, 则为页面 ID。 仅当将**WindowType**指定为绘图, 并将**ContainerType**指定为页面时, 才会出现相关的情况。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|ParentWindow  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |包含此模具窗口的窗口的 ID。 仅在将**WindowType**指定为模具时相关。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|ReadOnly  <br/> |xsd: boolean  <br/> |可选  <br/> |只读标志 (如果此模具不是文档模具)。  <br/> |Xsd: boolean 类型的值。  <br/> |
|Sheet  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |容器中工作表的 ID。 仅在将容器指定为工作表时相关。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|ViewCenterX  <br/> |xsd: double  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定在最初打开时, 新视图 (窗口) 假定在页面上的中心点。  <br/> |Xsd: double 类型的值。  <br/> |
|ViewCenterY  <br/> |xsd: double  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定在最初打开时, 新视图 (窗口) 假定在页面上的中心点。  <br/> |Xsd: double 类型的值。  <br/> |
|ViewScale  <br/> |xsd: double  <br/> |可选  <br/> |打开页面的新视图 (窗口) 时使用的默认放大因子。 例如, 1 = 100%;1.5 = 150%, 依此类推。  <br/> |Xsd: double 类型的值。  <br/> |
|WindowHeight  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |窗口矩形的高度。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|WindowLeft  <br/> |xsd: short  <br/> |可选  <br/> |窗口矩形的左坐标。  <br/> |Xsd: short 类型的值。  <br/> |
|WindowState  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |一个指定位标志的整数。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|WindowTop  <br/> |xsd: short  <br/> |可选  <br/> |窗口矩形的上坐标。  <br/> |Xsd: short 类型的值。  <br/> |
|WindowType  <br/> |xsd: token  <br/> |必需  <br/> |可以是下列值之一的枚举值: 绘图、工作表、模具或图标。  <br/> |Xsd: 令牌类型的值。  <br/> |
|WindowWidth  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |窗口矩形的宽度。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
   

