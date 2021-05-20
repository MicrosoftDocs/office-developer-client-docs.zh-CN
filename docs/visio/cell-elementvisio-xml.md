---
title: 'Cell 元素 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3131bfbb-9bf6-d15d-c6ca-2f15bd038f39
description: 指定可包含在 DocumentSheet、StyleSheet、PageSheet 或 ShapeSheet 中的单元格元素。
ms.openlocfilehash: 2b76abeb83fb7251bf492e92d8dd1a81feeab092
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542308"
---
# <a name="cell-element-visio-xml"></a>Cell 元素 (Visio XML) 

指定可包含在 DocumentSheet、StyleSheet、PageSheet 或 ShapeSheet 中的单元格元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml、pages.xml、masters.xml、master#.xml、page#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell"  type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定单元格元素，这些元素为形状的定义提供信息。  <br/> |
|[DocumentSheet](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSheet_Type](documentsheet_type-complextypevisio-xml.md) <br/> |定义 DocumentSheet 结构。  <br/> |
|[StyleSheet](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[StyleSheet_Type](stylesheets_type-complextypevisio-xml.md) <br/> |表示在文档中定义的样式。  <br/> |
|[PageSheet (Master_Type complexType) ](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定与主控板关联的绘图页的属性。  <br/> |
|[PageSheet (Page_Type complexType) ](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |指定与绘图页关联的绘图页的属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对绘图页的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd：string  <br/> |可选  <br/> |指示公式计算结果为错误。 **E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd：string  <br/> |可选  <br/> | 表示元素的公式。 此属性可以包含以下字符串之一：  <br/>  如果 (存在) ，则"设置一些公式"。  <br/>  `No Formula` 如果公式在本地删除或阻止  <br/>  `Inh` 如果公式是继承的。  <br/> |公式。  <br/> |
|N  <br/> |xsd：string  <br/> |必需  <br/> |代表 **ShapeSheet 单元格** 的名称。  <br/> |**ShapeSheet 单元格** 的名称。  <br/> 请参阅下面的"备注"部分。  <br/> |
|U  <br/> |xsd：string  <br/> |可选  <br/> |表示度量单位 默认值为 DL。  <br/> |单元格的单位。  <br/> |
|V  <br/> |xsd：string  <br/> |可选  <br/> |表示单元格的值。  <br/> |**ShapeSheet 单元格** 的值。  <br/> |
   
## <a name="remarks"></a>备注

此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。 请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|AddMarkup  <br/> |指示是否正对文档进行审阅以便加标记。  <br/> |[AddMarkup Cell (Document Properties Section)](addmarkup-cell-document-properties-section.md) <br/> |
|AlignBottom  <br/> |确定垂直位置，该位置是相对于其父级的原点、形状的下边框依其对齐的水平参考线或辅助点的原点而言的。  <br/> |[AlignBottom Cell (Alignment Section)](alignbottom-cell-alignment-section.md) <br/> |
|AlignCenter  <br/> |确定形状的水平中心依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。  <br/> |[AlignCenter Cell (Alignment Section)](aligncenter-cell-alignment-section.md) <br/> |
|AlignLeft  <br/> |确定形状的左边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。  <br/> |[AlignLeft Cell (Alignment Section)](alignleft-cell-alignment-section.md) <br/> |
|AlignMiddle  <br/> |确定形状的垂直中心依其对齐的水平参考线或辅助点的垂直位置（该位置是相对于其父级的原点而言的）。  <br/> |[AlignMiddle Cell (Alignment Section)](alignmiddle-cell-alignment-section.md) <br/> |
|AlignRight  <br/> |确定形状的右边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。  <br/> |[AlignRight Cell (Alignment Section)](alignright-cell-alignment-section.md) <br/> |
|AlignTop  <br/> |确定形状的上边框依其对齐的水平参考线或辅助点的垂直位置（该位置是相对于其父级的原点而言的）。  <br/> |[AlignTop Cell (Alignment Section)](aligntop-cell-alignment-section.md) <br/> |
|角  <br/> |代表某一形状相对于其父级的当前旋转角度。确定一维形状的旋转角度的默认公式为：=ATAN2(EndY-BeginY,EndX-BeginX)。  <br/> |[Angle Cell (Shape Transform Section)](angle-cell-shape-transform-section.md) <br/> |
|AvenueSizeX  <br/> |确定当您使用"设计"选项卡上的"配置布局"对话框 (在"布局"组中单击"Re-Layout 页面"，然后单击"其他布局选项") 来布置形状时，绘图页上的形状之间的水平空间量。  <br/> |[AvenueSizeX Cell (Page Layout Section)](avenuesizex-cell-page-layout-section.md) <br/> |
|AvenueSizeY  <br/> |确定当您使用"设计"选项卡上的"配置布局"对话框 (在"布局"组中单击"Re-Layout 页面"，然后单击"其他布局选项") 来布置形状时，绘图页上的形状之间的垂直空间量。 确定当您使用"设计"选项卡上的"配置布局"对话框 (在"布局"组中单击"Re-Layout 页面"，然后单击"其他布局选项") 来布置形状时，绘图页上的形状之间的垂直空间量。  <br/> |[AvenueSizeY Cell (Page Layout Section)](avenuesizey-cell-page-layout-section.md) <br/> |
|AvoidPageBreaks  <br/> |确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。  <br/> |[AvoidPageBreaks Cell (Page Layout Section) ](avoidpagebreaks-cell-page-layout-section.md) <br/> |
|BeginArrow  <br/> |指明线条的第一个顶点是否有箭头或其他线端格式。输入介于 0 到 45 之间的数字或带有自定义线端名的 USE 函数，或使用“线条”对话框。  <br/> |[BeginArrow Cell (Line Format Section)](beginarrow-cell-line-format-section.md) <br/> |
|BeginArrowSize  <br/> |确定线条起始处的箭头大小。  <br/> |[BeginArrowSize Cell (Line Format Section)](beginarrowsize-cell-line-format-section.md) <br/> |
|BeginX  <br/> |代表一维形状的起点相对于其父级的原点的 x 坐标。 代表一维形状的起点相对于其父级的原点的 x 坐标。  <br/> |[BeginX Cell (1-D Endpoints Section)](beginx-cell-1-d-endpoints-section.md) <br/> |
|BeginY  <br/> |代表一维形状的起点相对于其父级原点的 y 坐标。  <br/> |[BeginY Cell (1-D Endpoints Section)](beginy-cell-1-d-endpoints-section.md) <br/> |
|BegTrigger  <br/> |包含由应用程序生成的触发器公式，该公式确定是否移动一维形状的起点以便保持其与另一个形状的连接。  <br/> |[BegTrigger Cell (Glue Info Section)](begtrigger-cell-glue-info-section.md) <br/> |
|BevelBottomHeight  <br/> |确定形状的底部斜面的高度（以点表示）。  <br/> |[BevelBottomHeight Cell (Bevel Properties Section) ](bevelbottomheight-cell-bevel-properties-section.md) <br/> |
|BevelBottomType  <br/> |指定形状的斜面的底部斜面类型。  <br/> |[BevelBottomType Cell (Bevel Properties Section) ](bevelbottomtype-cell-bevel-properties-section.md) <br/> |
|BevelBottomWidth  <br/> |确定底部斜面的宽度（以点表示）。  <br/> |[BevelBottomWidth Cell (Bevel Properties Section) ](bevelbottomwidth-cell-bevel-properties-section.md) <br/> |
|BevelContourColor  <br/> |确定斜面轮廓线的颜色（以 RGB 值表示或由活动主题确定）。  <br/> |[BevelContourColor Cell (Bevel Properties Section) ](bevelcontourcolor-cell-bevel-properties-section.md) <br/> |
|BevelContourSize  <br/> |确定斜面的轮廓线的大小（以点表示）。  <br/> |[BevelContourSize Cell (Bevel Properties Section) ](bevelcontoursize-cell-bevel-properties-section.md) <br/> |
|BevelDepthColor  <br/> |确定作为 RGB 值或由活动主题确定的斜面深度的颜色。  <br/> |[BevelDepthColor Cell (Bevel Properties Section) ](beveldepthcolor-cell-bevel-properties-section.md) <br/> |
|BevelDepthSize  <br/> |确定斜面深度的大小（以点表示）。  <br/> |[BevelDepthSize Cell (Bevel Properties Section) ](beveldepthsize-cell-bevel-properties-section.md) <br/> |
|BevelLightingAngle  <br/> |确定闪电相对于斜面的角度（以度表示）。  <br/> |[BevelLightingAngle Cell (Bevel Properties Section) ](bevellightingangle-cell-bevel-properties-section.md) <br/> |
|BevelLightingType  <br/> |确定斜面效果使用的照明类型。  <br/> |[BevelLightingType Cell (Bevel Properties Section) ](bevellightingtype-cell-bevel-properties-section.md) <br/> |
|BevelMaterialType  <br/> |确定斜面所组成的材料类型。  <br/> |[BevelMaterialType Cell (Bevel Properties Section) ](bevelmaterialtype-cell-bevel-properties-section.md) <br/> |
|BevelTopHeight  <br/> |确定形状的顶部斜面的高度（以点表示）。  <br/> |[BevelTopHeight Cell (Bevel Properties Section) ](beveltopheight-cell-bevel-properties-section.md) <br/> |
|BevelTopType  <br/> |确定形状的上边缘上的斜面类型。  <br/> |[BevelTopType Cell (Bevel Properties Section) ](beveltoptype-cell-bevel-properties-section.md) <br/> |
|BevelTopWidth  <br/> |确定顶部斜面的宽度（以点表示）。  <br/> |[BevelTopWidth Cell (Bevel Properties Section) ](beveltopwidth-cell-bevel-properties-section.md) <br/> |
|BlockSizeX  <br/> |确定水平块大小，在使用"配置布局"对话框布局形状时，绘图页上每个形状都必须适合的区域。  <br/> |[BlockSizeX Cell (Page Layout Section)](blocksizex-cell-page-layout-section.md) <br/> |
|BlockSizeY  <br/> |确定垂直块大小，使用"配置布局"对话框布局形状时，绘图页上每个形状都必须适合的区域。  <br/> |[BlockSizeY Cell (Page Layout Section)](blocksizey-cell-page-layout-section.md) <br/> |
|Blur  <br/> |虚化或柔化位图图像。默认值是 0%。  <br/> |[Blur Cell (Image Properties Section)](blur-cell-image-properties-section.md) <br/> |
|BottomMargin  <br/> |确定文本块的下边框和所包含文本的最后一行之间的距离。  <br/> |[BottomMargin Cell (Text Block Format Section)](bottommargin-cell-text-block-format-section.md) <br/> |
|亮度  <br/> |调整位图图像的亮度。  <br/> |[Brightness Cell (Image Properties Section](brightness-cell-image-properties-section.md) <br/> |
|日历  <br/> |确定当单元格公式包含日期信息时所使用的日历。  <br/> |[Calendar Cell (Miscellaneous Section)](calendar-cell-miscellaneous-section.md) <br/> |
|日历  <br/> |确定当形状数据为 Date 时数据类型日历。  <br/> |[Calendar Cell (Shape Data Section)](calendar-cell-shape-data-section.md) <br/> |
|日历  <br/> |确定当文本字段为 Date 时用于数据类型日历。  <br/> |[Calendar Cell (Text Fields Section)](calendar-cell-text-fields-section.md) <br/> |
|CenterX  <br/> |确定该绘图页是否在打印纸上水平居中。  <br/> |[CenterX Cell (Print Properties Section)](centerx-cell-print-properties-section.md) <br/> |
|CenterY  <br/> |确定绘图页是否在打印纸上垂直居中。  <br/> |[CenterY Cell (Print Properties Section)](centery-cell-print-properties-section.md) <br/> |
|ClippingPath  <br/> |包含对图像所绑定路径的几何图形的引用。  <br/> |[ClippingPath Cell (Foreign Image Info Section) ](clippingpath-cell-foreign-image-info-section.md) <br/> |
|ColorSchemeIndex  <br/> |确定作为整数应用于形状的主题的配色方案。  <br/> |[ColorSchemeIndex Cell (Theme Properties Section) ](colorschemeindex-cell-theme-properties-section.md) <br/> |
|评论  <br/> |包含出现在注释中的文本。  <br/> |[Comment Cell (Annotation Section)](comment-cell-annotation-section.md) <br/> |
|评论  <br/> |包含形状的字符串格式的注释文本。  <br/> |[Comment Cell (Miscellaneous Section)](comment-cell-miscellaneous-section.md) <br/> |
|CompoundType  <br/> |确定形状线条的复合类型。  <br/> |[CompoundType Cell (Line Format Section) ](compoundtype-cell-line-format-section.md) <br/> |
|ConFixedCode  <br/> |确定何时重排连接线。  <br/> |[ConFixedCode Cell (Shape Layout Section)](confixedcode-cell-shape-layout-section.md) <br/> |
|ConLineJumpCode  <br/> |确定连接线何时跨线。  <br/> |[ConLineJumpCode Cell (Shape Layout Section)](conlinejumpcode-cell-shape-layout-section.md) <br/> |
|ConLineJumpDirX  <br/> |确定出现在形状的水平动态连接线上的跨线的方向。  <br/> |[ConLineJumpDirX Cell (Shape Layout Section)](conlinejumpdirx-cell-shape-layout-section.md) <br/> |
|ConLineJumpDirY  <br/> |确定出现在形状的垂直动态连接线上的跨线的跨线方向。  <br/> |[ConLineJumpDirY Cell (Shape Layout Section)](conlinejumpdiry-cell-shape-layout-section.md) <br/> |
|ConLineJumpStyle  <br/> |确定动态连接线上的跨线的跨线样式。  <br/> |[ConLineJumpStyle Cell (Shape Layout Section)](conlinejumpstyle-cell-shape-layout-section.md) <br/> |
|ConLineRouteExt  <br/> |确定连接线的外观。  <br/> |[ConLineRouteExt Cell (Shape Layout Section)](conlinerouteext-cell-shape-layout-section.md) <br/> |
|ConnectorSchemeIndex  <br/> |确定作为整数应用于形状的主题的连接线方案。  <br/> |[ConnectorSchemeIndex Cell (Theme Properties Section) ](connectorschemeindex-cell-theme-properties-section.md) <br/> |
|对比度  <br/> |调整位图图像的对比度。  <br/> |[Contrast Cell (Image Properties Section)](contrast-cell-image-properties-section.md) <br/> |
|版权  <br/> |包含表示可读版权声明的字符串  <br/> ||
|CtrlAsInput  <br/> |确定使用带有控制手柄的形状时哪个形状是父级。该单元格设置绘图页上所有形状的行为。  <br/> |[CtrlAsInput Cell (Page Layout Section)](ctrlasinput-cell-page-layout-section.md) <br/> |
|DefaultTabStop  <br/> |确定默认制表位在文本块中的间隔。  <br/> |[DefaultTabstop Cell (Text Block Format Section)](defaulttabstop-cell-text-block-format-section.md) <br/> |
|Denoise  <br/> |删除位图图像中的杂色（颜色级别随机分布的像素）。  <br/> |[Denoise Cell (Image Properties Section)](denoise-cell-image-properties-section.md) <br/> |
|DisplayLevel  <br/> |确定形状的显示级别分隔条（Z 顺序分组的相对范围）。  <br/> |[DisplayLevel Cell (Shape Layout Section) ](displaylevel-cell-shape-layout-section.md) <br/> |
|DisplayMode  <br/> |确定组合形状及其成员的显示方式。  <br/> |[DisplayMode Cell (Group Properties Section)](displaymode-cell-group-properties-section.md) <br/> |
|DisplayMode  <br/> |确定当用户将指针移动到标记上时、选择形状时还是所有时间都显示动作标记。  <br/> |[DisplayMode 单元格（“Smart Tags”内容）](displaymode-cell-action-tags-section.md) <br/> |
|DistanceFromGround  <br/> |确定在三维旋转时从地面引发对象的距离（以点表示）。  <br/> |[DistanceFromGround 单元格（“三维旋转属性”）](distancefromground-cell-3-d-rotation-properties.md) <br/> |
|DocLangID  <br/> |指示文档的默认语言。  <br/> |[DocLangID Cell (Document Properties Section)](doclangid-cell-document-properties-section.md) <br/> |
|DocLockDuplicatePage  <br/> |确定文档中的页面是否可复制，作为布尔值。  <br/> |[DocLockDuplicatePage Cell (Document Properties Section) ](doclockduplicatepage-cell-document-properties-section.md) <br/> |
|DocLockReplace  <br/> |确定是否应禁用此文档的替换形状 UI。  <br/> |[DocLockReplace Cell (Document Properties Section) ](doclockreplace-cell-document-properties-section.md) <br/> |
|DontMoveChildren  <br/> |确定是否可以使用鼠标拖动组合中的形状。  <br/> |[DontMoveChildren Cell (Group Properties Section)](dontmovechildren-cell-group-properties-section.md) <br/> |
|DrawingResizeType  <br/> |确定绘图页是否自动调整大小以适应图表。  <br/> |[DrawingResizeType Cell (Page Properties Section) ](drawingresizetype-cell-page-properties-section.md) <br/> |
|DrawingScale  <br/> |代表当前绘图比例中绘图单位的值。  <br/> |[DrawingScale Cell (Page Properties Section)](drawingscale-cell-page-properties-section.md) <br/> |
|DrawingScaleType  <br/> |确定在“页面设置”对话框（单击“开始”选项卡上的“页面设置”箭头）中所选的绘图缩放比例。  <br/> |[DrawingScaleType Cell (Page Properties Section)](drawingscaletype-cell-page-properties-section.md) <br/> |
|DrawingSizeType  <br/> |确定绘图的大小。  <br/> |[DrawingSizeType Cell (Page Properties Section)](drawingsizetype-cell-page-properties-section.md) <br/> |
|DropOnPageScale  <br/> |包含形状在绘图页上放下时缩放比例的百分比。  <br/> |[DropOnPageScale Cell (Miscellaneous Section)](droponpagescale-cell-miscellaneous-section.md) <br/> |
|DynamicsOff  <br/> |确定是否移动可放置的形状并让连接线围绕绘图页上的其他形状和连接线重排。  <br/> |[DynamicsOff Cell (Page Layout Section)](dynamicsoff-cell-page-layout-section.md) <br/> |
|DynFeedback  <br/> |更改当用户拖动连接线时所感受到的视觉反馈类型。  <br/> |[DynFeedback Cell (Miscellaneous Section)](dynfeedback-cell-miscellaneous-section.md) <br/> |
|EffectSchemeIndex  <br/> |确定作为整数应用于形状的主题的效果方案。  <br/> |[EffectSchemeIndex Cell (Theme Properties Section) ](effectschemeindex-cell-theme-properties-section.md) <br/> |
|EmbellishmentIndex  <br/> |更改标注 (、) 、日程表和组织结构图形状的修饰外观。  <br/> |[EmbellishmentIndex Cell (Theme Properties Section) ](embellishmentindex-cell-theme-properties-section.md) <br/> |
|EnableFillProps  <br/> |确定样式是否包括填充属性。  <br/> |[EnableFillProps Cell (Style Properties Section)](enablefillprops-cell-style-properties-section.md) <br/> |
|EnableGrid  <br/> |确定在"配置布局"对话框中配置布局时，应用程序是否基于内部不可见的页面网格布局形状。  <br/> |[EnableGrid Cell (Page Layout Section)](enablegrid-cell-page-layout-section.md) <br/> |
|EnableLineProps  <br/> |确定样式是否包括线条属性。  <br/> |[EnableLineProps Cell (Style Properties Section)](enablelineprops-cell-style-properties-section.md) <br/> |
|EnableTextProps  <br/> |确定样式是否包括文本属性。  <br/> |[EnableTextProps Cell (Style Properties Section)](enabletextprops-cell-style-properties-section.md) <br/> |
|EndArrow  <br/> |指出线条末端是箭头还是其他线端格式。  <br/> |[EndArrow Cell (Line Format Section)](endarrow-cell-line-format-section.md) <br/> |
|EndArrowSize  <br/> |确定线条末端的箭头大小。  <br/> |[EndArrowSize Cell (Line Format Section)](endarrowsize-cell-line-format-section.md) <br/> |
|EndTrigger  <br/> |包含由应用程序生成的触发器公式，该公式确定是否移动一维形状的终点以便保持其与另一个形状的连接。  <br/> |[EndTrigger Cell (Glue Info Section)](endtrigger-cell-glue-info-section.md) <br/> |
|EndX  <br/> |代表一维形状的终点相对于其父级原点的 x 坐标。  <br/> |[EndX Cell (1-D Endpoints Section)](endx-cell-1-d-endpoints-section.md) <br/> |
|EndY  <br/> |代表一维形状的终点相对于其父级原点的 y 坐标。  <br/> |[EndY Cell (1-D Endpoints Section)](endy-cell-1-d-endpoints-section.md) <br/> |
|EventDblClick  <br/> |一种事件单元格，双击某个形状后会对其求值。  <br/> |[EventDblClick Cell (Events Section)](eventdblclick-cell-events-section.md) <br/> |
|EventDrop  <br/> |一种事件单元格，在绘图页上放下某个形状时（或者作为实例，或者在复制或粘贴该形状时）会对其求值。  <br/> |[EventDrop Cell (Events Section)](eventdrop-cell-events-section.md) <br/> |
|EventMultiDrop  <br/> |一个事件单元格，当在绘图页上将多个形状丢弃时（作为实例，或者当复制或粘贴形状时）将计算该单元格。  <br/> |[EventMultiDrop Cell (Events Section) ](eventmultidrop-cell-events-section.md) <br/> |
|EventXFMod  <br/> |一种事件单元格，当形状的位置或方向在绘图页上发生变化时会对它求值（“XF”）。  <br/> |[EventXFMod Cell (Events Section)](eventxfmod-cell-events-section.md) <br/> |
|FillBkgnd  <br/> |确定用于形状的填充图案的背景（填充）颜色。  <br/> |[FillBkgnd Cell (Fill Format Section)](fillbkgnd-cell-fill-format-section.md) <br/> |
|FillBkgndTrans  <br/> |确定形状的填充图案的背景（填充）颜色的透明度级别。  <br/> |[FillBkgndTrans Cell (Fill Format Section)](fillbkgndtrans-cell-fill-format-section.md) <br/> |
|FillForegnd  <br/> |确定用于形状的填充图案的前景（划线）颜色。  <br/> |[FillForegnd Cell (Fill Format Section)](fillforegnd-cell-fill-format-section.md) <br/> |
|FillForegndTrans  <br/> |确定形状的填充图案的背景（填充）颜色的透明度级别。  <br/> |[FillForegndTrans Cell (Fill Format Section)](fillforegndtrans-cell-fill-format-section.md) <br/> |
|FillGradientAngle  <br/> |确定采用线性方向的渐变的填充渐变角度（以度表示）。  <br/> |[FillGradientAngle Cell (Gradient Properties Section) ](fillgradientangle-cell-gradient-properties-section.md) <br/> |
|FillGradientDir  <br/> |确定填充渐变的方向。 渐变可以是线性、径向、矩形或遵循路径。  <br/> |[FillGradientDir Cell (Gradient Properties Section) ](fillgradientdir-cell-gradient-properties-section.md) <br/> |
|FillGradientEnabled  <br/> |确定是否为此形状启用填充渐变。  <br/> |[FillGradientEnabled Cell (Gradient Properties Section) ](fillgradientenabled-cell-gradient-properties-section.md) <br/> |
|FillPattern  <br/> |确定形状的填充图案。要指定自定义的填充图案，请使用本单元格中的 USE 函数。  <br/> |[FillPattern Cell (Fill Format Section)](fillpattern-cell-fill-format-section.md) <br/> |
|FlipX  <br/> |指出形状是否已经水平翻转。  <br/> |[FlipX Cell (Shape Transform Section)](flipx-cell-shape-transform-section.md) <br/> |
|FlipY  <br/> |指出形状是否已经垂直翻转。  <br/> |[FlipY Cell (Shape Transform Section)](flipy-cell-shape-transform-section.md) <br/> |
|FontSchemeIndex  <br/> |确定作为整数应用于形状的主题的字体方案。  <br/> |[FontSchemeIndex Cell (Theme Properties Section](fontschemeindex-cell-theme-properties-section.md) <br/> |
|Gamma  <br/> |调整或校正图像的亮度，使之适合特定的输出设备，如监视器或扫描仪等。默认值为 1（不校正）。  <br/> |[Gamma Cell (Image Properties Section)](gamma-cell-image-properties-section.md) <br/> |
|GlowColor  <br/> |确定用于应用于形状的外部发光笔划的颜色，以 RGB 或主题值表示。  <br/> |[GlowColor Cell (Additional Effect Properties Section) ](glowcolor-cell-additional-effect-properties-section.md) <br/> |
|GlowColorTrans  <br/> |确定用于形状发光笔划的颜色的透明度级别（以百分比表示）。  <br/> |[GlowColorTrans Cell (Additional Effect Properties Section) ](glowcolortrans-cell-additional-effect-properties-section.md) <br/> |
|GlowSize  <br/> |确定形状的外部发光的大小（以点表示）。  <br/> |[GlowSize Cell (Additional Effect Properties Section) ](glowsize-cell-additional-effect-properties-section.md) <br/> |
|GlueType  <br/> |确定将一维形状粘附到另一个形状时是使用静态粘附（点到点）还是动态粘附（形状到形状）。  <br/> |[GlueType Cell (Glue Info Section)](gluetype-cell-glue-info-section.md) <br/> |
|Height  <br/> |确定以绘图单位表示的形状的高度。  <br/> |[Height Cell (Shape Transform Section)](height-cell-shape-transform-section.md) <br/> |
|HelpTopic  <br/> |指定形状的帮助主题 ID。  <br/> ||
|HideForApply  <br/> |确定样式在 Microsoft 用户界面中的Visio位置。  <br/> |[HideForApply Cell (Style Properties Section)](hideforapply-cell-style-properties-section.md) <br/> |
|HideText  <br/> |隐藏形状的文本。  <br/> |[HideText Cell (Miscellaneous Section)](hidetext-cell-miscellaneous-section.md) <br/> |
|ImgHeight  <br/> |确定对象的图像在其边框内的高度。  <br/> |[ImgHeight Cell (Foreign Image Info Section)](imgheight-cell-foreign-image-info-section.md) <br/> |
|ImgOffsetX  <br/> |确定对象水平偏离对象边框的原点的距离。  <br/> |[ImgOffsetX Cell (Foreign Image Info Section)](imgoffsetx-cell-foreign-image-info-section.md) <br/> |
|ImgOffsetY  <br/> |确定对象垂直偏离对象边框的原点的距离。  <br/> |[ImgOffsetY Cell (Foreign Image Info Section)](imgoffsety-cell-foreign-image-info-section.md) <br/> |
|ImgWidth  <br/> |确定对象的图像在其边框内的宽度。  <br/> |[ImgWidth Cell (Foreign Image Info Section)](imgwidth-cell-foreign-image-info-section.md) <br/> |
|InhibitSnap  <br/> |确定前景页中的形状是否与该页中的其他对象和背景页中的形状对齐。  <br/> |[InhibitSnap Cell (Page Properties Section)](inhibitsnap-cell-page-properties-section.md) <br/> |
|IsDropSource  <br/> |确定是否能通过将一个形状拖放到组合中的方法将形状添加到组合中。  <br/> |[IsDropSource Cell (Miscellaneous Section)](isdropsource-cell-miscellaneous-section.md) <br/> |
|IsDropTarget  <br/> |确定组合是否允许您通过将形状放在该组合上来添加形状。  <br/> |[IsDropTarget Cell (Group Properties Section)](isdroptarget-cell-group-properties-section.md) <br/> |
|IsSnapTarget  <br/> |确定是对齐组合还是对齐该组合内的形状。  <br/> |[IsSnapTarget Cell (Group Properties Section)](issnaptarget-cell-group-properties-section.md) <br/> |
|IsTextEditTarget  <br/> |确定组合的文本分配。  <br/> |[IsTextEditTarget Cell (Group Properties Section)](istextedittarget-cell-group-properties-section.md) <br/> |
|KeepTextFlat  <br/> |指示形状的文本是否忽略该形状在三维中的旋转。 不适用于二维旋转。  <br/> |[KeepTextFlat Cell (3-D Rotation Properties Section) ](keeptextflat-cell-3-d-rotation-properties-section.md) <br/> |
|LangID  <br/> |指示输入注释所使用的语言。  <br/> |[LangID Cell (Annotation Section)](langid-cell-annotation-section.md) <br/> |
|LangID  <br/> |指示输入文本所使用的语言。  <br/> |[LangID Cell (Character Section)](langid-cell-character-section.md) <br/> |
|LangID  <br/> |指示创建单元格公式所使用的语言。  <br/> |[LangID Cell (Miscellaneous Section)](langid-cell-miscellaneous-section.md) <br/> |
|LangID  <br/> |指示输入形状数据值所使用的语言。  <br/> |[LangID Cell (Shape Data Section)](langid-cell-shape-data-section.md) <br/> |
|LayerMember  <br/> |根据页面图层的从零开始索引指定形状的图层成员身份。 如果将一个形状分配给多个图层，则每个图层索引都显示为用分号分隔。  <br/> ||
|LeftMargin  <br/> |确定文本块左边框和它所包含的文本之间的距离。  <br/> |[LeftMargin Cell (Text Block Format Section)](leftmargin-cell-text-block-format-section.md) <br/> |
|LineAdjustFrom  <br/> |确定在出现动态连接线彼此重叠的情况下应用程序将分隔哪些动态连接线。  <br/> |[LineAdjustFrom Cell (Page Layout Section)](lineadjustfrom-cell-page-layout-section.md) <br/> |
|LineAdjustTo  <br/> |确定哪些动态连接线要彼此重叠。  <br/> |[LineAdjustTo Cell (Page Layout Section)](lineadjustto-cell-page-layout-section.md) <br/> |
|LineCap  <br/> |指示线端形状是圆形、方形还是扩展式。  <br/> |[LineCap Cell (Line Format Section)](linecap-cell-line-format-section.md) <br/> |
|LineColor  <br/> |确定形状的线条颜色。  <br/> |[LineColor Cell (Line Format Section)](linecolor-cell-line-format-section.md) <br/> |
|LineColorTrans  <br/> |确定形状的线条颜色的透明度级别。  <br/> |[LineColorTrans Cell (Line Format Section)](linecolortrans-cell-line-format-section.md) <br/> |
|LineGradientAngle  <br/> |确定线性渐变的线条渐变角度，从 0 到 359.9 度。  <br/> |[LineGradientAngle Cell (Gradient Properties Section) ](linegradientangle-cell-gradient-properties-section.md) <br/> |
|LineGradientDir  <br/> |确定线条渐变的方向。 渐变可以是线性、径向、矩形或遵循路径。  <br/> |[LineGradientDir Cell (Gradient Properties Section) ](linegradientdir-cell-gradient-properties-section.md) <br/> |
|LineGradientEnabled  <br/> |确定是否为形状的线条或边框启用线条渐变。  <br/> |[LineGradientEnabled Cell (Gradient Properties Section) ](linegradientenabled-cell-gradient-properties-section.md) <br/> |
|LineJumpCode  <br/> |确定要向其添加跨线的连接线。  <br/> ||
|LineJumpFactorX  <br/> |确定页中水平动态连接线上跨线的大小（相对于 LineToLineX 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。  <br/> |[LineJumpFactorX Cell (Page Layout Section)](linejumpfactorx-cell-page-layout-section.md) <br/> |
|LineJumpFactorY  <br/> |确定页中垂直动态连接线上的跨线的大小（相对于 LineToLineY 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。  <br/> |[LineJumpFactorY Cell (Page Layout Section)](linejumpfactory-cell-page-layout-section.md) <br/> |
|LineJumpStyle  <br/> |确定在没有本地跨线样式的绘图页上，所有连接线的跨线样式。  <br/> |[LineJumpStyle Cell (Page Layout Section)](linejumpstyle-cell-page-layout-section.md) <br/> |
|LinePattern  <br/> |确定形状的线型。在 LinePattern 单元格中输入的值是一个数字，此数字是线型集合中的索引。  <br/> |[LinePattern Cell (Line Format Section)](linepattern-cell-line-format-section.md) <br/> |
|LineRouteExt  <br/> |确定绘图页上所有连接线的默认外观。  <br/> |[LineRouteExt Cell (Page Layout Section)](linerouteext-cell-page-layout-section.md) <br/> |
|LineToLineX  <br/> |确定在绘图页上所有连接线之间的水平间距。  <br/> |[LineToLineX Cell (Page Layout Section)](linetolinex-cell-page-layout-section.md) <br/> |
|LineToLineY  <br/> |确定在绘图页上所有连接线之间的垂直间距。  <br/> |[LineToLineY Cell (Page Layout Section)](linetoliney-cell-page-layout-section.md) <br/> |
|LineToNodeX  <br/> |确定在绘图页上所有连接线和形状之间的水平间距。  <br/> |[LineToNodeX Cell (Page Layout Section)](linetonodex-cell-page-layout-section.md) <br/> |
|LineToNodeY  <br/> |确定在绘图页上所有连接线和形状之间的垂直间距。  <br/> |[LineToNodeY Cell (Page Layout Section)](linetonodey-cell-page-layout-section.md) <br/> |
|LineWeight  <br/> |确定形状的线条粗细。通过输入具有有效度量单位的数字即可设置线条粗细。  <br/> |[LineWeight Cell (Line Format Section)](lineweight-cell-line-format-section.md) <br/> |
|LocalizeMerge  <br/> |确定在文档间复制时是否本地化形状。  <br/> |[LocalizeMerge Cell (Miscellaneous Section)](localizemerge-cell-miscellaneous-section.md) <br/> |
|LockAspect  <br/> |锁定形状的纵横比，使形状只能按比例调整大小，而不能单维度调整大小。  <br/> |[LockAspect Cell (Protection Section)](lockaspect-cell-protection-section.md) <br/> |
|LockBegin  <br/> |将一维形状的起点 (BeginX, BeginY) 锁定在特定位置上。  <br/> |[LockBegin Cell (Protection Section)](lockbegin-cell-protection-section.md) <br/> |
|LockCalcWH  <br/> |锁定形状的选择矩形，使得在“Geometry”内容中编辑顶点或更改行类型时，不会重新计算选择矩形。  <br/> |[LockCalcWH Cell (Protection Section)](lockcalcwh-cell-protection-section.md) <br/> |
|LockCrop  <br/> |锁定来自其他程序的对象，防止它被“剪裁”工具剪裁。  <br/> |[LockCrop Cell (Protection Section)](lockcrop-cell-protection-section.md) <br/> |
|LockCustProp  <br/> |确定用户是否可以使用“定义形状数据”对话框或“形状数据”窗口的快捷菜单在用户界面 (UI) 中添加、删除或修改形状数据。  <br/> |[LockCustProp Cell (Protection Section)](lockcustprop-cell-protection-section.md) <br/> |
|LockDelete  <br/> |锁定形状，使它不能被删除。  <br/> |[LockDelete Cell (Protection Section)](lockdelete-cell-protection-section.md) <br/> |
|LockEnd  <br/> |将一维形状的终点 (EndX, EndY) 锁定在特定位置上。  <br/> |[LockEnd Cell (Protection Section)](lockend-cell-protection-section.md) <br/> |
|LockFormat  <br/> |锁定形状的格式，使它无法更改。  <br/> |[LockFormat Cell (Protection Section)](lockformat-cell-protection-section.md) <br/> |
|LockFromGroupFormat  <br/> |阻止将组合形状的格式更改传播到其子形状，同时仍允许用户直接设置所选子形状的格式。 LockFromGroupFormat 单元格的值与“保护”对话框中的“阻止应用组格式”复选框设置相对应。  <br/> |[LockFromGroupFormat Cell (Protection Section) ](lockfromgroupformat-cell-protection-section.md) <br/> |
|LockGroup  <br/> |锁定某组，使该组不能被取消组合。  <br/> |[LockGroup Cell (Protection Section)](lockgroup-cell-protection-section.md) <br/> |
|LockHeight  <br/> |锁定形状的高度，以便在调整该形状的大小时使其高度保持不变。  <br/> |[LockHeight Cell (Protection Section)](lockheight-cell-protection-section.md) <br/> |
|LockMoveX  <br/> |锁定形状的水平位置，使它不能水平移动。  <br/> |[LockMoveX Cell (Protection Section)](lockmovex-cell-protection-section.md) <br/> |
|LockMoveY  <br/> |锁定形状的垂直位置，使它不能垂直移动。  <br/> |[LockMoveY Cell (Protection Section)](lockmovey-cell-protection-section.md) <br/> |
|LockPreview  <br/> |确定每次保存绘图时是否保存预览。  <br/> |[LockPreview Cell (Document Properties Section)](lockpreview-cell-document-properties-section.md) <br/> |
|LockReplace  <br/> |指示形状是否可以参与替换操作 (作为目标或替换形状) 。  <br/> |[LockReplace Cell (Protection Section) ](lockreplace-cell-protection-section.md) <br/> |
|LockRotate  <br/> |锁定二维形状，以免它随旋转手柄或者“向左旋转 90°”或“向右旋转 90°”命令旋转。  <br/> |[LockRotate Cell (Protection Section)](lockrotate-cell-protection-section.md) <br/> |
|LockSelect  <br/> |防止选取某个形状。  <br/> |[LockSelect Cell (Protection Section)](lockselect-cell-protection-section.md) <br/> |
|LockTextEdit  <br/> |锁定形状的文本，使它无法编辑。  <br/> |[LockTextEdit Cell (Protection Section)](locktextedit-cell-protection-section.md) <br/> |
|LockThemeColors  <br/> |阻止向形状应用主题颜色。 LockThemeColors 单元格的值与“保护”对话框中的“阻止应用主题颜色”复选框设置相对应。  <br/> |[LockThemeColors Cell (Protection Section) ](lockthemecolors-cell-protection-section.md) <br/> |
|LockThemeConnectors  <br/> |通过应用新主题或选择新的连接器方案，防止更改"主题属性"行中的 ConnectorsSchemeIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。  <br/> |[LockThemeConnectors Cell (Protection Section) ](lockthemeconnectors-cell-protection-section.md) <br/> |
|LockThemeEffects  <br/> |对应于"保护"对话框中的"自主题效果"复选框设置。  <br/> |[LockThemeEffects Cell (Protection Section) ](lockthemeeffects-cell-protection-section.md) <br/> |
|LockThemeFonts  <br/> |通过应用新主题防止更改"主题属性"行中的 FontIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。  <br/> |[LockThemeFonts Cell (Protection Section) ](lockthemefonts-cell-protection-section.md) <br/> |
|LockThemeIndex  <br/> |通过应用新主题或选择新连接线方案来阻止更改"主题属性"行中的 ThemeIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。  <br/> |[LockThemeIndex Cell (Protection Section) ](lockthemeindex-cell-protection-section.md) <br/> |
|LockVariation  <br/> |确定是否可以将应用于页面或形状的主题变体作为布尔值进行更改。  <br/> |[LockVariation Cell (Protection Section) ](lockvariation-cell-protection-section.md) <br/> |
|LockVtxEdit  <br/> |锁定形状的顶点，以使它们无法编辑。  <br/> |[LockVtxEdit Cell (Protection Section)](lockvtxedit-cell-protection-section.md) <br/> |
|LockWidth  <br/> |锁定形状的宽度，以便在调整该形状的大小时使其宽度保持不变。  <br/> |[LockWidth Cell (Protection Section)](lockwidth-cell-protection-section.md) <br/> |
|LocPinX  <br/> |表示形状的旋转中心点（旋转中心）相对于形状原点的 x 坐标。 用于确定 LocPinX 的默认公式为：= Width \* 0.5。  <br/> |[LocPinX Cell (Shape Transform Section)](locpinx-cell-shape-transform-section.md) <br/> |
|LockPinY  <br/> |表示形状的旋转中心点（旋转中心）相对于形状原点的 y 坐标。 用于确定 LocPinY 的默认公式为： = 高度 \* 0.5。  <br/> |[LocPinY Cell (Shape Transform Section)](locpiny-cell-shape-transform-section.md) <br/> |
|NoAlignBox  <br/> |切换选中形状的选择矩形的显示状态 - 显示或不显示。  <br/> |[NoAlignBox Cell (Miscellaneous Section)](noalignbox-cell-miscellaneous-section.md) <br/> |
|NoCoauth  <br/> |设置存储在 SharePoint 2013 服务器或 Microsoft OneDrive 上的文档是否可以由多个作者在共同创作会话中同时编辑。  <br/> |[NoCoauth Cell (Document Properties Section) ](nocoauth-cell-document-properties-section.md) <br/> |
|NoCtlHandles  <br/> |防止在选择形状时显示控制手柄。  <br/> |[NoCtlHandles Cell (Miscellaneous Section)](noctlhandles-cell-miscellaneous-section.md) <br/> |
|NoLiveDynamics  <br/> |确定在您操纵一个形状时，该形状是否动态改变大小或旋转。  <br/> |[NoLiveDynamics Cell (Miscellaneous Section)](nolivedynamics-cell-miscellaneous-section.md) <br/> |
|NonPrinting  <br/> |切换选中形状的打印状态 - 启用或禁用。  <br/> |[NonPrinting Cell (Miscellaneous Section)](nonprinting-cell-miscellaneous-section.md) <br/> |
|NoObjHandles  <br/> |切换选中形状的选择手柄的显示状态 - 显示或不显示。  <br/> |[NoObjHandles Cell (Miscellaneous Section)](noobjhandles-cell-miscellaneous-section.md) <br/> |
|NoProofing  <br/> |确定是否将自动更正拼写，以及是否显示所选形状的拼写错误。  <br/> ||
|ObjType  <br/> |确定当使用“配置布局”对话框排放形状时对象在图表中是可放置的还是可穿绕的。  <br/> |[ObjType Cell (Miscellaneous Section)](objtype-cell-miscellaneous-section.md) <br/> |
|OnPage  <br/> |指示是否将绘图打印到指定数量的打印纸上。  <br/> |[OnPage Cell (Print Properties Section)](onpage-cell-print-properties-section.md) <br/> |
|OutputFormat  <br/> |确定绘图的输出格式。绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。  <br/> |[OutputFormat Cell (Document Properties Section)](outputformat-cell-document-properties-section.md) <br/> |
|PageBottomMargin  <br/> |指定打印页底部的边距。  <br/> |[PageBottomMargin Cell (Print Properties Section)](pagebottommargin-cell-print-properties-section.md) <br/> |
|PageHeight  <br/> |包含以绘图单位表示的打印页面的高度。  <br/> |[PageHeight Cell (Page Properties Section)](pageheight-cell-page-properties-section.md) <br/> |
|PageLeftMargin  <br/> |指定打印页左侧的边距。  <br/> |[PageLeftMargin Cell (Print Properties Section)](pageleftmargin-cell-print-properties-section.md) <br/> |
|PageLineJumpDirX  <br/> |确定在尚未应用本地跨线方向的绘图页内水平动态连接线上的跨线方向。  <br/> |[PageLineJumpDirX Cell (Page Layout Section)](pagelinejumpdirx-cell-page-layout-section.md) <br/> |
|PageLineJumpDirY  <br/> |确定在尚未应用本地跨线方向的绘图页内垂直动态连接线上的跨线方向。  <br/> |[PageLineJumpDirY Cell (Page Layout Section)](pagelinejumpdiry-cell-page-layout-section.md) <br/> |
|PageLockDuplicate  <br/> |确定页面是否可复制，作为布尔值。  <br/> |[PageLockDuplicate Cell (Page Properties Section) ](pagelockduplicate-cell-page-properties-section.md) <br/> |
|PageLockReplace  <br/> |指示是否应该为此页禁用"替换形状"按钮。  <br/> |[PageLockReplace Cell (Page Properties Section) ](pagelockreplace-cell-page-properties-section.md) <br/> |
|PageRightMargin  <br/> |指定打印页右侧的边距。  <br/> |[PageRightMargin Cell (Print Properties Section)](pagerightmargin-cell-print-properties-section.md) <br/> |
|PageScale  <br/> |确定当前绘图比例中页面单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。  <br/> |[PageScale Cell (Page Properties Section)](pagescale-cell-page-properties-section.md) <br/> |
|PageShapeSplit  <br/> |指示是否可以自动拆分页面上的形状。  <br/> |[PageShapeSplit Cell (Page Layout Section)](pageshapesplit-cell-page-layout-section.md) <br/> |
|PagesX  <br/> |确定从横向适合绘图页的打印纸的数目。  <br/> |[PagesX Cell (Print Properties Section)](pagesx-cell-print-properties-section.md) <br/> |
|PagesY  <br/> |确定从纵向适合绘图页的打印纸的数目。  <br/> |[PagesY Cell (Print Properties Section)](pagesy-cell-print-properties-section.md) <br/> |
|PageTopMargin  <br/> |指定打印页顶部的边距。  <br/> |[PageTopMargin Cell (Print Properties Section)](pagetopmargin-cell-print-properties-section.md) <br/> |
|PageWidth  <br/> |确定以绘图单位表示的打印页面的宽度。  <br/> |[PageWidth Cell (Page Properties Section)](pagewidth-cell-page-properties-section.md) <br/> |
|PaperKind  <br/> |指定打印绘图页的纸张类型。  <br/> |[PaperKind Cell (Print Properties Section)](paperkind-cell-print-properties-section.md) <br/> |
|PaperSource  <br/> |确定页面的纸张来源。  <br/> |[PaperSource Cell (PrintProperties Section)](papersource-cell-printproperties-section.md) <br/> |
|Perspective  <br/> |确定透视旋转的角度，以 0 到 359.9 (0 到 359.9) 。  <br/> |[Perspective Cell (3-D Rotation Properties Section) ](perspective-cell-3-d-rotation-properties-section.md) <br/> |
|PinX  <br/> |表示形状的旋转中心点（旋转中心）相对于其父级原点的 x 坐标。  <br/> |[PinX Cell (Shape Transform Section)](pinx-cell-shape-transform-section.md) <br/> |
|PinY  <br/> |表示形状的旋转中心点（旋转中心）相对于其父级原点的 y 坐标。  <br/> |[PinY Cell (Shape Transform Section)](piny-cell-shape-transform-section.md) <br/> |
|PlaceDepth  <br/> |确定在创建布局之前分析绘图使用的方法，并确定布局的类型。  <br/> |[PlaceDepth Cell (Page Layout Section)](placedepth-cell-page-layout-section.md) <br/> |
|PlaceFlip  <br/> |确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）时可放置形状在页面上如何翻转和/或旋转。  <br/> |[PlaceFlip Cell (Page Layout Section)](placeflip-cell-page-layout-section.md) <br/> |
|PlaceStyle  <br/> |确定在“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）中排放形状时如何在页面上放置这些形状。  <br/> |[PlaceStyle Cell (Page Layout Section) ](placestyle-cell-page-layout-section.md) <br/> |
|PlowCode  <br/> |确定在绘图页上将一个可放置形状放到另一个可放置形状旁边时，可放置形状是否移走。  <br/> |[PlowCode Cell (Page Layout Section)](plowcode-cell-page-layout-section.md) <br/> |
|PreviewQuality  <br/> |确定是以草稿质量显示绘图预览还是以详细视图显示绘图预览。  <br/> |[PreviewQuality Cell (Document Properties Section)](previewquality-cell-document-properties-section.md) <br/> |
|PreviewScope  <br/> |确定您的绘图是否包含预览。如果绘图中确实包含预览，则确定该预览是只显示绘图中的第一页还是显示所有页。  <br/> |[PreviewScope Cell (Document Properties Section)](previewscope-cell-document-properties-section.md) <br/> |
|PrintGrid  <br/> |指定在打印文档页面时是否打印网格。  <br/> |[PrintGrid Cell (Print Properties Section)](printgrid-cell-print-properties-section.md) <br/> |
|PrintPageOrientation  <br/> |确定是纵向打印页面还是横向打印页面。  <br/> |[PrintPageOrientation Cell (Print Properties Section)](printpageorientation-cell-print-properties-section.md) <br/> |
|QuickStyleEffectsMatrix  <br/> |确定形状从活动主题继承的快速样式效果，作为 0-6 的整数。  <br/> ||
|QuickStyleFillColor  <br/> |确定形状的填充使用的主题颜色，作为 0 到 7 的整数。  <br/> |[QuickStyleFillColor Cell (Quick Style Section) ](quickstylefillcolor-cell-quick-style-section.md) <br/> |
|QuickStyleFillMatrix  <br/> |确定形状从活动主题继承的快速样式填充样式，作为 0-6 的整数。  <br/> |[QuickStyleFillMatrix Cell (Quick Style Section) ](quickstylefillmatrix-cell-quick-style-section.md) <br/> |
|QuickStyleFontColor  <br/> |确定形状的文本从活动主题继承的快速样式中的字体颜色，作为 0-1 的整数。  <br/> |[QuickStyleFontColor Cell (Quick Style Section) ](quickstylefontcolor-cell-quick-style-section.md) <br/> |
|QuickStyleFontMatrix  <br/> |确定每个快速样式的字体样式，作为 1 到 6 的整数。  <br/> |[QuickStyleFontMatrix Cell (Quick Style Section) ](quickstylefontmatrix-cell-quick-style-section.md) <br/> |
|QuickStyleLineColor  <br/> |确定形状线条使用的主题颜色，作为 0 到 7 的整数。  <br/> |[QuickStyleLineColor Cell (Quick Style Section) ](quickstylelinecolor-cell-quick-style-section.md) <br/> |
|QuickStyleLineMatrix  <br/> |确定形状继承的快速样式样式，作为 0-6 的整数。  <br/> |[QuickStyleLineMatrix Cell (Quick Style Section) ](quickstylelinematrix-cell-quick-style-section.md) <br/> |
|QuickStyleShadowColor  <br/> |确定形状的阴影使用的主题颜色，作为从 0 到 7 的整数。  <br/> |[QuickStyleShadowColor Cell (Quick Style Section) ](quickstyleshadowcolor-cell-quick-style-section.md) <br/> |
|QuickStyleType  <br/> |确定形状继承 (二维、一维或) 快速样式类型。  <br/> |[QuickStyleType Cell (Quick Style Section) ](quickstyletype-cell-quick-style-section.md) <br/> |
|QuickStyleVariation  <br/> |确保形状上的文本、线条和/或填充颜色可见性针对有色图表背景。  <br/> ||
|ReflectionBlur  <br/> |确定形状上的反射的模糊程度，以 0.0 到 100.0 之间的点表示。  <br/> |[ReflectionBlur Cell (Additional Effect Properties Section) ](reflectionblur-cell-additional-effect-properties-section.md) <br/> |
|ReflectionDist  <br/> |确定反射与形状的偏移距离，以 0.0 到 100.0 的点表示。  <br/> |[ReflectionDist Cell (Additional Effect Properties Section) ](reflectiondist-cell-additional-effect-properties-section.md) <br/> |
|ReflectionSize  <br/> |确定相对于形状的反射大小，以 0.0% 到 100.0% 的百分比表示。 ReflectionSize 单元格中值为 0% 的形状没有反射;值 100% 显示形状的完整镜像。  <br/> |[ReflectionSize Cell (Additional Effect Properties Section) ](reflectionsize-cell-additional-effect-properties-section.md) <br/> |
|ReflectionTrans  <br/> |确定反射的透明度，以 0% 到 100% 的百分比表示。  <br/> |[ReflectionTrans Cell (Additional Effect Properties Section) ](reflectiontrans-cell-additional-effect-properties-section.md) <br/> |
|关系  <br/> |存储容器、列表、标注和形状之间的关系。  <br/> |[Relationships Cell (Shape Layout Section) ](relationships-cell-shape-layout-section.md) <br/> |
|ReplaceCopyCells  <br/> |指示 ShapeSheet 中的单元格列表，这些单元格在形状替换操作过程中从旧形状复制到替换形状。  <br/> |[ReplaceCopyCells Cell (Change Shape Behavior Section) ](replacecopycells-cell-change-shape-behavior-section.md) <br/> |
|ReplaceLockFormat  <br/> |指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 如果主控形状的 ReplaceLockFormat 单元格设置为 TRUE (1) ，则主控形状的格式值将覆盖要由主控形状替换的形状的所有相应值。  <br/> |[ReplaceLockFormat Cell (Change Shape Behavior Section) ](replacelockformat-cell-change-shape-behavior-section.md) <br/> |
|ReplaceLockShapeData  <br/> |指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 ReplaceLockShapeData 确定主形状的形状数据是否覆盖要替换的形状的所有形状数据。  <br/> |[ReplaceLockShapeData Cell (Change Shape Behavior Section) ](replacelockshapedata-cell-change-shape-behavior-section.md) <br/> |
|ReplaceLockText  <br/> |指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 ReplaceLockText 确定主控形状上显示的文本是否覆盖要替换的形状的文本。  <br/> |[ReplaceLockText Cell (Change Shape Behavior Section) ](replacelocktext-cell-change-shape-behavior-section.md) <br/> |
|ResizeMode  <br/> |显示形状的当前调整大小行为设置。  <br/> |[ResizeMode Cell (Shape Transform Section)](resizemode-cell-shape-transform-section.md) <br/> |
|ResizePage  <br/> |确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状后是否放大页面以装入绘图。  <br/> |[ResizePage Cell (Page Layout Section)](resizepage-cell-page-layout-section.md) <br/> |
|RightMargin  <br/> |确定文本块的右边框和它所包含的文本之间的距离。默认值是 0.1 英寸。  <br/> |[RightMargin Cell (Text Block Format Section)](rightmargin-cell-text-block-format-section.md) <br/> |
|RotateGradientWithShape  <br/> |确定填充渐变是否随形状在 2D 旋转中作为布尔值旋转。  <br/> |[RotateGradientWithShape Cell (Gradient Properties Section) ](rotategradientwithshape-cell-gradient-properties-section.md) <br/> |
|RotationType  <br/> |确定形状是按照从 0 到 6 的整数进行平行旋转、透视旋转还是倾斜旋转。  <br/> |[RotationType Cell (3-D Rotation Properties Section) ](rotationtype-cell-3-d-rotation-properties-section.md) <br/> |
|RotationXAngle  <br/> |确定沿 X 轴旋转的角度，以 0.0 - 359.9 (度) 。  <br/> |[RotationXAngle Cell (3-D Rotation Properties Section) ](rotationxangle-cell-3-d-rotation-properties-section.md) <br/> |
|RotationYAngle  <br/> |确定沿 Y 轴的旋转角度，以 0.0 - 359.9 (度) 。  <br/> |[RotationYAngle Cell (3-D Rotation Properties Section) ](rotationyangle-cell-3-d-rotation-properties-section.md) <br/> |
|RotationZAngle  <br/> |确定沿 Z 轴的旋转角度，以 0.0 - 359.9 (度) 。  <br/> |[RotationZAngle Cell (3-D Rotation Properties Section) ](rotationzangle-cell-3-d-rotation-properties-section.md) <br/> |
|Rounding  <br/> |指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。  <br/> |[Rounding Cell (Line Format Section)](rounding-cell-line-format-section.md) <br/> |
|RouteStyle  <br/> |在没有本地排列样式的绘图页上确定所有连接线的排列样式和方向。  <br/> |[RouteStyle Cell (Page Layout Section)](routestyle-cell-page-layout-section.md) <br/> |
|ScaleX  <br/> |指定打印机页面上绘图页的缩放百分比。  <br/> |[ScaleX Cell (Print Properties Section)](scalex-cell-print-properties-section.md) <br/> |
|ScaleY  <br/> |指定打印机页面上绘图页的缩放百分比。  <br/> |[ScaleY Cell (Print Properties Section)](scaley-cell-print-properties-section.md) <br/> |
|SelectMode  <br/> |确定如何选择组合形状及其组成部分。  <br/> |[SelectMode Cell (Group Properties Section)](selectmode-cell-group-properties-section.md) <br/> |
|ShapeFixedCode 单元格  <br/> |指定可放置形状的放置行为。  <br/> |[ShapeFixedCode Cell (Shape Layout Section)](shapefixedcode-cell-shape-layout-section.md) <br/> |
|ShapeKeywords  <br/> |包含已分配给主控形状的搜索关键字。  <br/> ||
|ShapePermeablePlace  <br/> |确定在“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）中排放形状时，可放置形状是否可以放置在某个形状的顶部。  <br/> |[ShapePermeablePlace Cell (Shape Layout Section)](shapepermeableplace-cell-shape-layout-section.md) <br/> |
|ShapePermeableX  <br/> |确定连接线是否可以水平穿绕可放置形状。  <br/> |[ShapePermeableX Cell (Shape Layout Section)](shapepermeablex-cell-shape-layout-section.md) <br/> |
|ShapePermeableY  <br/> |确定连接线是否可以垂直穿绕形状。  <br/> |[ShapePermeableY Cell (Shape Layout Section)](shapepermeabley-cell-shape-layout-section.md) <br/> |
|ShapePlaceFlip  <br/> |确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状时，可放置形状在页面上如何翻转、旋转或同时翻转和旋转。  <br/> |[ShapePlaceFlip Cell (Shape Layout Section)](shapeplaceflip-cell-shape-layout-section.md) <br/> |
|ShapePlaceStyle  <br/> |指定当形状在"设计"选项卡上的"配置布局"对话框 (中布局时如何在页面上放置形状，单击"Re-Layout 页面"，然后单击"其他布局选项") 。 存储 VisCellIndices 中的布局样式和对齐方式值。  <br/> |[ShapePlaceStyle Cell (Shape Layout Section) ](shapeplacestyle-cell-shape-layout-section.md) <br/> |
|ShapePlowCode  <br/> |确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。  <br/> |[ShapePlowCode Cell (Shape Layout Section)](shapeplowcode-cell-shape-layout-section.md) <br/> |
|ShapeRouteStyle  <br/> |确定绘图页上所选连接线的排列样式和方向。  <br/> |[ShapeRouteStyle Cell (Shape Layout Section)](shaperoutestyle-cell-shape-layout-section.md) <br/> |
|ShapeShdwBlur  <br/> |确定形状阴影的模糊大小，以 0.00 到 100.00 (100.00) 。  <br/> |[ShapeShdwBlur Cell (Fill Format Section) ](shapeshdwblur-cell-fill-format-section.md) <br/> |
|ShapeShdwObliqueAngle  <br/> |指定形状阴影倾斜方向的角度。  <br/> |[ShapeShdwObliqueAngle Cell (Fill Format Section)](shapeshdwobliqueangle-cell-fill-format-section.md) <br/> |
|ShapeShdwOffsetX  <br/> |确定形状的阴影与该形状水平偏移的距离（按页面单位）。  <br/> |[ShapeShdwOffsetX Cell (Fill Format Section)](shapeshdwoffsetx-cell-fill-format-section.md) <br/> |
|ShapeShdwOffsetY  <br/> |确定形状的阴影与该形状垂直偏移的距离（按页面单位）。  <br/> |[ShapeShdwOffsetY Cell (Fill Format Section)](shapeshdwoffsety-cell-fill-format-section.md) <br/> |
|ShapeShdwScaleFactor  <br/> |指定形状阴影可放大或缩小的百分比。  <br/> |[ShapeShdwScaleFactor Cell (Fill Format Section)](shapeshdwscalefactor-cell-fill-format-section.md) <br/> |
|ShapeShdwShow  <br/> |确定形状是否以 0 到 2 的整数显示阴影。  <br/> |[ShapeShdwShow Cell (Fill Format Section) ](shapeshdwshow-cell-fill-format-section.md) <br/> |
|ShapeShdwType  <br/> |指定形状的阴影类型。  <br/> |[ShapeShdwType Cell (Fill Format Section)](shapeshdwtype-cell-fill-format-section.md) <br/> |
|ShapeSplit  <br/> |指示此形状是否可以拆分其他可拆分的形状。  <br/> |[ShapeSplit Cell (Shape Layout Section)](shapesplit-cell-shape-layout-section.md) <br/> |
|ShapeSplittable  <br/> |指示此一维形状是否可以拆分。  <br/> |[ShapeSplittable Cell (Shape Layout Section)](shapesplittable-cell-shape-layout-section.md) <br/> |
|Sharpen  <br/> |锐化位图图像。默认值是 0%。通过增加相邻像素的对比度来锐化图像可以使图像更鲜明。  <br/> |[Sharpen Cell (Image Properties Section)](sharpen-cell-image-properties-section.md) <br/> |
|ShdwForegnd  <br/> |确定用于形状的投影填充图案的前景（划线）的颜色。  <br/> |[ShdwForegnd Cell (Fill Format Section)](shdwforegnd-cell-fill-format-section.md) <br/> |
|ShdwForegndTrans  <br/> |确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。  <br/> |[ShdwForegndTrans Cell (Fill Format Section)](shdwforegndtrans-cell-fill-format-section.md) <br/> |
|ShdwObliqueAngle  <br/> |包含指定应用默认页面阴影类型时的倾斜方向角度的数字。  <br/> |[ShdwObliqueAngle Cell (Page Properties Section)](shdwobliqueangle-cell-page-properties-section.md) <br/> |
|ShdwOffsetX  <br/> |确定形状的投影与该形状水平偏移的距离（按页面单位）。  <br/> |[ShdwOffsetX Cell (Page Properties Section)](shdwoffsetx-cell-page-properties-section.md) <br/> |
|ShdwOffsetY  <br/> |确定形状的投影与该形状垂直偏移的距离（按页面单位）。  <br/> |[ShdwOffsetY Cell (Page Properties Section)](shdwoffsety-cell-page-properties-section.md) <br/> |
|ShdwPattern  <br/> |确定某一形状的阴影的填充图案。  <br/> |[ShdwPattern Cell (Fill Format Section)](shdwpattern-cell-fill-format-section.md) <br/> |
|ShdwScaleFactor  <br/> |指定放大或缩小形状阴影的百分比。  <br/> |[ShdwScaleFactor Cell (Page Properties Section)](shdwscalefactor-cell-page-properties-section.md) <br/> |
|ShdwType  <br/> |指示页面的默认阴影类型。  <br/> |[ShdwType Cell (Page Properties Section)](shdwtype-cell-page-properties-section.md) <br/> |
|SketchAmount  <br/> |确定草图效果的失真量，以 0 到 25 之间的整数表示。  <br/> |[SketchAmount Cell (Additional Effect Properties Section) ](sketchamount-cell-additional-effect-properties-section.md) <br/> |
|SketchEnabled  <br/> |确定草图效果是否以布尔值显示于形状上。  <br/> |[SketchEnabled Cell (Additional Effect Properties Section) ](sketchenabled-cell-additional-effect-properties-section.md) <br/> |
|SketchFillChange  <br/> |确定使用草图效果时形状的几何图形填充的随机化量，以部分长度的百分比表示。 如果 SketchFillChange 单元格的值设置为 0%，则形状填充的边界几何图形与形状的几何图形匹配。 如果值为 100%，则形状填充的边界几何图形不遵循形状的几何图形。  <br/> |[SketchFillChange Cell (Additional Effect Properties Section) ](sketchfillchange-cell-additional-effect-properties-section.md) <br/> |
|SketchLineChange  <br/> |确定使用草图效果时形状的几何图形线条的随机化量，以部分长度的百分比表示。 如果 SketchLineChange 单元格的值设置为 0%，则形状线条的几何图形与形状的几何图形匹配。 如果值为 100%，则形状线条的几何图形不遵循形状的几何图形。  <br/> |[SketchLineChange Cell (Additional Effect Properties Section) ](sketchlinechange-cell-additional-effect-properties-section.md) <br/> |
|SketchLineWeight  <br/> |确定作为草图效果的结果添加到线条粗细的额外粗细（以 0 到 50 磅）。 随着 SketchLineWeight 单元格值的增加，形状线条的粗细增加。  <br/> |[SketchLineWeight Cell (Additional Effect Properties Section) ](sketchlineweight-cell-additional-effect-properties-section.md) <br/> |
|SketchSeed  <br/> |表示用于确定草图效果的几何图形的随机化值，为正整数。 当将草图效果应用于形状时，将随机创建 SketchSeed 单元格的值。  <br/> |[SketchSeed Cell (Additional Effect Properties Section) ](sketchseed-cell-additional-effect-properties-section.md) <br/> |
|SoftEdgesSize  <br/> |确定柔化边缘效果的大小，以 0.00 到 100.00 的点表示。 如果 SoftEdgesSize 单元格的值为 0，则形状没有柔化边缘。  <br/> |[SoftEdgesSize Cell (Additional Effect Properties Section) ](softedgessize-cell-additional-effect-properties-section.md) <br/> |
|TextBkgnd  <br/> |确定一个形状的文本背景色。  <br/> |[TextBkgnd Cell (Text Block Format Section)](textbkgnd-cell-text-block-format-section.md) <br/> |
|TextBkgndTrans  <br/> |确定形状的文本块背景色的透明度级别。  <br/> |[TextBkgndTrans Cell (Text Block Format Section)](textbkgndtrans-cell-text-block-format-section.md) <br/> |
|TextDirection  <br/> |确定文本块中字符的方向。  <br/> |[TextDirection Cell (Text Block Format Section)](textdirection-cell-text-block-format-section.md) <br/> |
|TheData  <br/> |保留供以后使用。  <br/> |[TheData Cell (Events Section)](thedata-cell-events-section.md) <br/> |
|ThemeIndex  <br/> |将应用于文档的内置 Microsoft Visio主题的枚举存储为整数。 为文档选择新主题后，文档及其包含的所有页面和形状的 ThemeIndex 单元格将更新为内置主题的索引。  <br/> |[ThemeIndex Cell (Theme Properties Section) ](themeindex-cell-theme-properties-section.md) <br/> |
|TheText  <br/> |当形状文本或文本组成成分改变时进行求值的事件单元格。  <br/> |[TheText Cell (Events Section)](thetext-cell-events-section.md) <br/> |
|TopMargin  <br/> |确定文本块的上边界和它包含的第一行文本之间的距离。默认值是 4.0000 磅。此值与绘图比例无关。即使对绘图比例进行了调整，上边距仍保持不变。  <br/> |[TopMargin Cell (Text Block Format Section)](topmargin-cell-text-block-format-section.md) <br/> |
|透明度  <br/> |确定形状的某一范围文本颜色的透明度级别。  <br/> |[Transparency Cell (Character Section)](transparency-cell-character-section.md) <br/> |
|透明度  <br/> |确定图层颜色的透明度级别。  <br/> |[Transparency Cell (Image Properties Section)](transparency-cell-image-properties-section.md) <br/> |
|透明度  <br/> |确定图层颜色的透明度级别。  <br/> |[Transparency Cell (Layers Section)](transparency-cell-layers-section.md) <br/> |
|TxtAngle  <br/> |确定文本块当前相对于形状的 x 轴坐标的旋转角度。默认值是 0 度。  <br/> |[TxtAngle Cell (Text Transform Section)](txtangle-cell-text-transform-section.md) <br/> |
|TxtHeight  <br/> |确定文本块的高度。 默认公式为：= Height \* 1  <br/> |[TxtHeight Cell (Text Transform Section)](txtheight-cell-text-transform-section.md) <br/> |
|TxtLocPinX  <br/> |确定文本块的旋转中心相对于文本块原点的 x 坐标。 默认公式为：= TxtWidth \* 0.5此公式计算为文本块的水平中心。  <br/> |[TxtLocPinX Cell (Text Transform Section)](txtlocpinx-cell-text-transform-section.md) <br/> |
|TxtLocPinY  <br/> |确定文本块的旋转中心相对于文本块原点的 y 坐标。 默认公式为：= TxtHeight \* 0.5  <br/> |[TxtLocPinY Cell (Text Transform Section)](txtlocpiny-cell-text-transform-section.md) <br/> |
|TxtPinX  <br/> |确定文本块的旋转中心相对于形状原点的 x 坐标。 默认公式为：= Width \* 0.5  <br/> |[TxtPinX Cell (Text Transform Section)](txtpinx-cell-text-transform-section.md) <br/> |
|TxtPinY  <br/> |确定文本块的旋转中心相对于形状原点的 y 坐标。 默认公式为：= Height \* 0.5  <br/> |[TxtPinY Cell (Text Transform Section)](txtpiny-cell-text-transform-section.md) <br/> |
|TxtWidth  <br/> |确定文本块的宽度。 默认公式为：= 宽度 \* 1  <br/> |[TxtWidth Cell (Text Transform Section)](txtwidth-cell-text-transform-section.md) <br/> |
|UIVisibility  <br/> |确定用户界面 (UI) 中是否显示页名称。  <br/> |[UIVisibility Cell (Page Properties Section)](uivisibility-cell-page-properties-section.md) <br/> |
|UpdateAlignBox  <br/> |只要移动控制手柄，就重新计算选择矩形。  <br/> |[UpdateAlignBox Cell (Miscellaneous Section)](updatealignbox-cell-miscellaneous-section.md) <br/> |
|UseGroupGradient  <br/> |确定形状与其他形状组合在一起时是否采用渐变，作为布尔值。 UseGroupGradient 单元格的值仅影响形状填充。  <br/> |[UseGroupGradient Cell (Gradient Properties Section) ](usegroupgradient-cell-gradient-properties-section.md) <br/> |
|VariationColorIndex  <br/> |确定页面上活动主题变体的颜色索引（以整数表示）。  <br/> |[VariationColorIndex Cell (Theme Properties Section) ](variationcolorindex-cell-theme-properties-section.md) <br/> |
|VariationStyleIndex  <br/> |确定页面上活动主题变体的样式索引，作为整数。  <br/> |[VariationStyleIndex Cell (Theme Properties Section) ](variationstyleindex-cell-theme-properties-section.md) <br/> |
|VerticalAlign  <br/> |确定文本块内文本的垂直对齐方式。  <br/> |[VerticalAlign Cell (Text Block Format Section)](verticalalign-cell-text-block-format-section.md) <br/> |
|ViewMarkup  <br/> |确定绘图窗口中是否显示标记。  <br/> |[ViewMarkup Cell (Document Properties Section)](viewmarkup-cell-document-properties-section.md) <br/> |
|WalkPreference  <br/> |确定一维形状的端点是否移到其所粘附的形状的水平或垂直连接点上（当形状移到不明确的位置上时，使用动态粘附）。默认情况下，一维形状的两个端点都移到水平连接点上。  <br/> |[WalkPreference Cell (Glue Info Section)](walkpreference-cell-glue-info-section.md) <br/> |
|Width  <br/> |包含所选形状的宽度（以绘图单位计）。 用于确定一维形状的宽度的默认公式为：= SQRT ( (EndX - BeginX) ^ 2 + (EndY - BeginY) ^ 2)   <br/> |[Width Cell (Shape Transform Section)](width-cell-shape-transform-section.md) <br/> |
|XGridDensity  <br/> |指定要使用的水平网格的类型。  <br/> |[XGridDensity Cell (Ruler &amp; Grid Section) ](xgriddensity-cell-rulergrid-section.md) <br/> |
|XGridOrigin  <br/> |指定网格原点的水平坐标。  <br/> |[XGridOrigin Cell (Ruler &amp; Grid Section) ](xgridorigin-cell-rulergrid-section.md) <br/> |
|XGridSpacing  <br/> |指定固定网格中水平线条间的距离 (XGridDensity = 0)。  <br/> |[XGridSpacing Cell (Ruler &amp; Grid Section) ](xgridspacing-cell-rulergrid-section.md) <br/> |
|XRulerDensity  <br/> |指定页面标尺上的水平细分线。  <br/> |[XRulerDensity Cell (Ruler &amp; Grid Section) ](xrulerdensity-cell-rulergrid-section.md) <br/> |
|XRulerOrigin  <br/> |指定页面 x 轴标尺上的零点。  <br/> |[XRulerOrigin Cell (Ruler &amp; Grid Section) ](xrulerorigin-cell-rulergrid-section.md) <br/> |
|YGridDensity  <br/> |指定要使用的垂直网格的类型。  <br/> |[YGridDensity Cell (Ruler &amp; Grid Section) ](ygriddensity-cell-rulergrid-section.md) <br/> |
|YGridOrigin  <br/> |指定网格的垂直起点。  <br/> |["YGridOrigin 单元格 (&amp; Ruler Grid"内容) ](ygridorigin-cell-rulergrid-section.md) <br/> |
|YGridSpacing  <br/> |指定固定网格中垂直线条间的距离 (YGridDensity = 0)。  <br/> |[YGridSpacing Cell (Ruler &amp; Grid Section) ](ygridspacing-cell-rulergrid-section.md) <br/> |
|YRulerDensity  <br/> |指定页面标尺上的垂直细分线。  <br/> |[YRulerDensity Cell (Ruler &amp; Grid Section) ](yrulerdensity-cell-rulergrid-section.md) <br/> |
|YRulerOrigin  <br/> |指定页面 y 轴标尺上的零点。  <br/> |[YRulerOrigin Cell (Ruler &amp; Grid Section) ](yrulerorigin-cell-rulergrid-section.md) <br/> |
   

