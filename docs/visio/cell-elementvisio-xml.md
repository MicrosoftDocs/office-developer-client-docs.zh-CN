---
title: Cell 元素 (Visio XML)
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
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |document .xml、web.xml、.master、.master、master # .xml 和第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell"  type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

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
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |指定对绘图页的引用。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示公式的计算结果为错误。 **E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一:  <br/>  "(某些公式)" 如果该公式在本地存在  <br/>  `No Formula`如果公式为本地删除或被阻止  <br/>  `Inh`如果公式是继承的。  <br/> |一个公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |代表**ShapeSheet**单元格的名称。  <br/> |**ShapeSheet**单元格的名称。  <br/> 请参阅下面的 "备注" 部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |表示一个度量单位, 默认值为 DL。  <br/> |单元格的单位。  <br/> |
|部分  <br/> |xsd: string  <br/> |可选  <br/> |表示单元格的值。  <br/> |**ShapeSheet**单元格的值。  <br/> |
   
## <a name="remarks"></a>备注

此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。 请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。 
  
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
|AvenueSizeX  <br/> |确定使用 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 排放形状时, 绘图页上的形状之间的水平间距量。  <br/> |[AvenueSizeX Cell (Page Layout Section)](avenuesizex-cell-page-layout-section.md) <br/> |
|AvenueSizeY  <br/> |确定使用 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 排放形状时, 绘图页上的形状之间的垂直间距量。 确定使用 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 排放形状时, 绘图页上的形状之间的垂直间距量。  <br/> |[AvenueSizeY Cell (Page Layout Section)](avenuesizey-cell-page-layout-section.md) <br/> |
|AvoidPageBreaks  <br/> |确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。  <br/> |[AvoidPageBreaks 单元格 ("Page Layout" 内容)](avoidpagebreaks-cell-page-layout-section.md) <br/> |
|BeginArrow  <br/> |指明线条的第一个顶点是否有箭头或其他线端格式。 输入介于 0 到 45 之间的数字或带有自定义线端名的 USE 函数，或使用“线条”对话框。  <br/> |[BeginArrow Cell (Line Format Section)](beginarrow-cell-line-format-section.md) <br/> |
|BeginArrowSize  <br/> |确定线条起始处的箭头大小。  <br/> |[BeginArrowSize Cell (Line Format Section)](beginarrowsize-cell-line-format-section.md) <br/> |
|BeginX  <br/> |代表一维形状的起点相对于其父级的原点的 x 坐标。 代表一维形状的起点相对于其父级的原点的 x 坐标。  <br/> |[BeginX Cell (1-D Endpoints Section)](beginx-cell-1-d-endpoints-section.md) <br/> |
|BeginY  <br/> |代表一维形状的起点相对于其父级原点的 y 坐标。  <br/> |[BeginY Cell (1-D Endpoints Section)](beginy-cell-1-d-endpoints-section.md) <br/> |
|BegTrigger  <br/> |包含由应用程序生成的触发器公式，该公式确定是否移动一维形状的起点以便保持其与另一个形状的连接。  <br/> |[BegTrigger Cell (Glue Info Section)](begtrigger-cell-glue-info-section.md) <br/> |
|BevelBottomHeight  <br/> |确定形状的底部棱台的高度 (以磅为单位)。  <br/> |[BevelBottomHeight 单元格 ("棱台属性" 部分)](bevelbottomheight-cell-bevel-properties-section.md) <br/> |
|BevelBottomType  <br/> |指定形状棱台的底部棱台类型。  <br/> |[BevelBottomType 单元格 ("棱台属性" 部分)](bevelbottomtype-cell-bevel-properties-section.md) <br/> |
|BevelBottomWidth  <br/> |确定底部棱台的宽度 (以磅为单位)。  <br/> |[BevelBottomWidth 单元格 ("棱台属性" 部分)](bevelbottomwidth-cell-bevel-properties-section.md) <br/> |
|BevelContourColor  <br/> |确定棱台的颜色的 RGB 值的颜色或由活动主题确定的颜色。  <br/> |[BevelContourColor 单元格 ("棱台属性" 部分)](bevelcontourcolor-cell-bevel-properties-section.md) <br/> |
|BevelContourSize  <br/> |确定斜边等高线的大小 (以磅为单位)。  <br/> |[BevelContourSize 单元格 ("棱台属性" 部分)](bevelcontoursize-cell-bevel-properties-section.md) <br/> |
|BevelDepthColor  <br/> |以 RGB 值或由活动主题确定的方式确定斜面深度的颜色。  <br/> |[BevelDepthColor 单元格 ("棱台属性" 部分)](beveldepthcolor-cell-bevel-properties-section.md) <br/> |
|BevelDepthSize  <br/> |确定斜面的深度 (以磅为单位) 的大小。  <br/> |[BevelDepthSize 单元格 ("棱台属性" 部分)](beveldepthsize-cell-bevel-properties-section.md) <br/> |
|BevelLightingAngle  <br/> |确定闪电相对于斜面的角度 (以度为单位)。  <br/> |[BevelLightingAngle 单元格 ("棱台属性" 部分)](bevellightingangle-cell-bevel-properties-section.md) <br/> |
|BevelLightingType  <br/> |确定凹凸效果使用的光的类型。  <br/> |[BevelLightingType 单元格 ("棱台属性" 部分)](bevellightingtype-cell-bevel-properties-section.md) <br/> |
|BevelMaterialType  <br/> |确定由斜角构成的材料的类型。  <br/> |[BevelMaterialType 单元格 ("棱台属性" 部分)](bevelmaterialtype-cell-bevel-properties-section.md) <br/> |
|BevelTopHeight  <br/> |确定形状的顶部棱台的高度 (以磅为单位)。  <br/> |[BevelTopHeight 单元格 ("棱台属性" 部分)](beveltopheight-cell-bevel-properties-section.md) <br/> |
|BevelTopType  <br/> |确定形状的上边缘的斜面类型。  <br/> |[BevelTopType 单元格 ("棱台属性" 部分)](beveltoptype-cell-bevel-properties-section.md) <br/> |
|BevelTopWidth  <br/> |确定顶部棱台的宽度 (以磅为单位)。  <br/> |[BevelTopWidth 单元格 ("棱台属性" 部分)](beveltopwidth-cell-bevel-properties-section.md) <br/> |
|BlockSizeX  <br/> |确定水平块大小, 当您使用 "配置布局" 对话框排放形状时, 每个形状在绘图页上必须符合的区域。  <br/> |[BlockSizeX Cell (Page Layout Section)](blocksizex-cell-page-layout-section.md) <br/> |
|BlockSizeY  <br/> |确定垂直块大小, 当您使用 "配置布局" 对话框排放形状时, 每个形状在绘图页上必须符合的区域。  <br/> |[BlockSizeY Cell (Page Layout Section)](blocksizey-cell-page-layout-section.md) <br/> |
|Blur  <br/> |虚化或柔化位图图像。 默认值是 0%。  <br/> |[Blur Cell (Image Properties Section)](blur-cell-image-properties-section.md) <br/> |
|BottomMargin  <br/> |确定文本块的下边框和所包含文本的最后一行之间的距离。  <br/> |[BottomMargin Cell (Text Block Format Section)](bottommargin-cell-text-block-format-section.md) <br/> |
|亮度  <br/> |调整位图图像的亮度。  <br/> |[亮度单元格 ("图像属性" 部分](brightness-cell-image-properties-section.md) <br/> |
|日历  <br/> |确定当单元格公式包含日期信息时所使用的日历。  <br/> |[Calendar Cell (Miscellaneous Section)](calendar-cell-miscellaneous-section.md) <br/> |
|日历  <br/> |确定当数据类型为日期时用于形状数据的日历。  <br/> |[Calendar Cell (Shape Data Section)](calendar-cell-shape-data-section.md) <br/> |
|日历  <br/> |确定当数据类型为日期时用于文本字段的日历。  <br/> |[Calendar Cell (Text Fields Section)](calendar-cell-text-fields-section.md) <br/> |
|CenterX  <br/> |确定该绘图页是否在打印纸上水平居中。  <br/> |[CenterX Cell (Print Properties Section)](centerx-cell-print-properties-section.md) <br/> |
|CenterY  <br/> |确定绘图页是否在打印纸上垂直居中。  <br/> |[CenterY Cell (Print Properties Section)](centery-cell-print-properties-section.md) <br/> |
|ClippingPath  <br/> |包含对图像所绑定的路径的几何图形的引用。  <br/> |[ClippingPath 单元格 ("外部图像信息" 部分)](clippingpath-cell-foreign-image-info-section.md) <br/> |
|ColorSchemeIndex  <br/> |确定应用于形状的主题的配色方案, 以整数形式表示。  <br/> |[ColorSchemeIndex 单元格 ("主题属性" 部分)](colorschemeindex-cell-theme-properties-section.md) <br/> |
|Comment  <br/> |包含出现在注释中的文本。  <br/> |[Comment Cell (Annotation Section)](comment-cell-annotation-section.md) <br/> |
|Comment  <br/> |包含形状的字符串格式的注释文本。  <br/> |[Comment Cell (Miscellaneous Section)](comment-cell-miscellaneous-section.md) <br/> |
|CompoundType  <br/> |确定形状的线条的复合类型。  <br/> |[CompoundType 单元格 ("Line Format" 内容)](compoundtype-cell-line-format-section.md) <br/> |
|ConFixedCode  <br/> |确定何时重排连接线。  <br/> |[ConFixedCode Cell (Shape Layout Section)](confixedcode-cell-shape-layout-section.md) <br/> |
|ConLineJumpCode  <br/> |确定连接线何时跨线。  <br/> |[ConLineJumpCode Cell (Shape Layout Section)](conlinejumpcode-cell-shape-layout-section.md) <br/> |
|ConLineJumpDirX  <br/> |确定出现在形状的水平动态连接线上的跨线的方向。  <br/> |[ConLineJumpDirX Cell (Shape Layout Section)](conlinejumpdirx-cell-shape-layout-section.md) <br/> |
|ConLineJumpDirY  <br/> |确定出现在形状的垂直动态连接线上的跨线的跨线方向。  <br/> |[ConLineJumpDirY Cell (Shape Layout Section)](conlinejumpdiry-cell-shape-layout-section.md) <br/> |
|ConLineJumpStyle  <br/> |确定动态连接线上的跨线的跨线样式。  <br/> |[ConLineJumpStyle Cell (Shape Layout Section)](conlinejumpstyle-cell-shape-layout-section.md) <br/> |
|ConLineRouteExt  <br/> |确定连接线的外观。  <br/> |[ConLineRouteExt Cell (Shape Layout Section)](conlinerouteext-cell-shape-layout-section.md) <br/> |
|ConnectorSchemeIndex  <br/> |确定应用于形状的主题的连接器方案, 以整数形式表示。  <br/> |[ConnectorSchemeIndex 单元格 ("主题属性" 部分)](connectorschemeindex-cell-theme-properties-section.md) <br/> |
|对比度  <br/> |调整位图图像的对比度。  <br/> |[Contrast Cell (Image Properties Section)](contrast-cell-image-properties-section.md) <br/> |
|版权  <br/> |包含表示可读版权声明的字符串  <br/> ||
|CtrlAsInput  <br/> |确定使用带有控制手柄的形状时哪个形状是父级。该单元格设置绘图页上所有形状的行为。  <br/> |[CtrlAsInput Cell (Page Layout Section)](ctrlasinput-cell-page-layout-section.md) <br/> |
|DefaultTabStop  <br/> |确定默认制表位在文本块中的间隔。  <br/> |[DefaultTabstop Cell (Text Block Format Section)](defaulttabstop-cell-text-block-format-section.md) <br/> |
|Denoise  <br/> |删除位图图像中的杂色（颜色级别随机分布的像素）。  <br/> |[Denoise Cell (Image Properties Section)](denoise-cell-image-properties-section.md) <br/> |
|DisplayLevel  <br/> |确定形状的显示级别分隔条（Z 顺序分组的相对范围）。  <br/> |[DisplayLevel 单元格 ("Shape Layout" 内容)](displaylevel-cell-shape-layout-section.md) <br/> |
|DisplayMode  <br/> |确定组合形状及其成员的显示方式。  <br/> |[DisplayMode Cell (Group Properties Section)](displaymode-cell-group-properties-section.md) <br/> |
|DisplayMode  <br/> |决定当用户将鼠标指针移到标记上时、选择形状时, 还是在所有时间都显示动作标记。  <br/> |[DisplayMode 单元格（“Smart Tags”内容）](displaymode-cell-action-tags-section.md) <br/> |
|DistanceFromGround  <br/> |确定以磅为单位在三维中旋转时的对象的底边距离。  <br/> |[DistanceFromGround 单元格（“三维旋转属性”）](distancefromground-cell-3-d-rotation-properties.md) <br/> |
|DocLangID  <br/> |指示文档的默认语言。  <br/> |[DocLangID Cell (Document Properties Section)](doclangid-cell-document-properties-section.md) <br/> |
|DocLockDuplicatePage  <br/> |确定是否可以将文档中的页面复制为布尔值。  <br/> |[DocLockDuplicatePage 单元格 ("Document Properties" 内容)](doclockduplicatepage-cell-document-properties-section.md) <br/> |
|DocLockReplace  <br/> |确定是否应为此文档禁用 "替换形状" UI。  <br/> |[DocLockReplace 单元格 ("Document Properties" 内容)](doclockreplace-cell-document-properties-section.md) <br/> |
|DontMoveChildren  <br/> |确定是否可以使用鼠标拖动组合中的形状。  <br/> |[DontMoveChildren Cell (Group Properties Section)](dontmovechildren-cell-group-properties-section.md) <br/> |
|DrawingResizeType  <br/> |确定绘图页是否自动调整大小以放置图表。  <br/> |[DrawingResizeType 单元格 ("Page Properties" 内容)](drawingresizetype-cell-page-properties-section.md) <br/> |
|DrawingScale  <br/> |代表当前绘图比例中绘图单位的值。  <br/> |[DrawingScale Cell (Page Properties Section)](drawingscale-cell-page-properties-section.md) <br/> |
|DrawingScaleType  <br/> |确定在“页面设置”对话框（单击“开始”选项卡上的“页面设置”箭头）中所选的绘图缩放比例。  <br/> |[DrawingScaleType Cell (Page Properties Section)](drawingscaletype-cell-page-properties-section.md) <br/> |
|DrawingSizeType  <br/> |确定绘图的大小。  <br/> |[DrawingSizeType Cell (Page Properties Section)](drawingsizetype-cell-page-properties-section.md) <br/> |
|DropOnPageScale  <br/> |包含形状在绘图页上放下时缩放比例的百分比。  <br/> |[DropOnPageScale Cell (Miscellaneous Section)](droponpagescale-cell-miscellaneous-section.md) <br/> |
|DynamicsOff  <br/> |确定是否移动可放置的形状并让连接线围绕绘图页上的其他形状和连接线重排。  <br/> |[DynamicsOff Cell (Page Layout Section)](dynamicsoff-cell-page-layout-section.md) <br/> |
|DynFeedback  <br/> |更改当用户拖动连接线时所感受到的视觉反馈类型。  <br/> |[DynFeedback Cell (Miscellaneous Section)](dynfeedback-cell-miscellaneous-section.md) <br/> |
|EffectSchemeIndex  <br/> |确定应用于形状的主题的效果方案, 以整数形式。  <br/> |[EffectSchemeIndex 单元格 ("主题属性" 部分)](effectschemeindex-cell-theme-properties-section.md) <br/> |
|EmbellishmentIndex  <br/> |更改标注、容器、时间线和组织结构图形状的外观 (embellishment)。  <br/> |[EmbellishmentIndex 单元格 ("主题属性" 部分)](embellishmentindex-cell-theme-properties-section.md) <br/> |
|EnableFillProps  <br/> |确定样式是否包括填充属性。  <br/> |[EnableFillProps Cell (Style Properties Section)](enablefillprops-cell-style-properties-section.md) <br/> |
|EnableGrid  <br/> |确定在 "配置布局" 对话框中配置布局时, 应用程序是否基于内部不可见的页面网格排放形状。  <br/> |[EnableGrid Cell (Page Layout Section)](enablegrid-cell-page-layout-section.md) <br/> |
|EnableLineProps  <br/> |确定样式是否包括线条属性。  <br/> |[EnableLineProps Cell (Style Properties Section)](enablelineprops-cell-style-properties-section.md) <br/> |
|EnableTextProps  <br/> |确定样式是否包括文本属性。  <br/> |[EnableTextProps Cell (Style Properties Section)](enabletextprops-cell-style-properties-section.md) <br/> |
|EndArrow  <br/> |指出线条末端是箭头还是其他线端格式。  <br/> |[EndArrow Cell (Line Format Section)](endarrow-cell-line-format-section.md) <br/> |
|EndArrowSize  <br/> |确定线条末端的箭头大小。  <br/> |[EndArrowSize Cell (Line Format Section)](endarrowsize-cell-line-format-section.md) <br/> |
|EndTrigger  <br/> |包含由应用程序生成的触发器公式，该公式确定是否移动一维形状的终点以便保持其与另一个形状的连接。  <br/> |[EndTrigger Cell (Glue Info Section)](endtrigger-cell-glue-info-section.md) <br/> |
|EndX  <br/> |代表一维形状的终点相对于其父级原点的 x 坐标。  <br/> |[EndX Cell (1-D Endpoints Section)](endx-cell-1-d-endpoints-section.md) <br/> |
|EndY  <br/> |代表一维形状的终点相对于其父级原点的 y 坐标。  <br/> |[EndY Cell (1-D Endpoints Section)](endy-cell-1-d-endpoints-section.md) <br/> |
|EventDblClick  <br/> |一种事件单元格，双击某个形状后会对其求值。  <br/> |[EventDblClick Cell (Events Section)](eventdblclick-cell-events-section.md) <br/> |
|EventDrop  <br/> |一种事件单元格，在绘图页上放下某个形状时（或者作为实例，或者在复制或粘贴该形状时）会对其求值。  <br/> |[EventDrop Cell (Events Section)](eventdrop-cell-events-section.md) <br/> |
|EventMultiDrop  <br/> |当多个形状作为实例放置在绘图页上或者在复制或粘贴形状时计算的事件单元格。  <br/> |[EventMultiDrop 单元格 ("事件" 部分)](eventmultidrop-cell-events-section.md) <br/> |
|EventXFMod  <br/> |一种事件单元格，当形状的位置或方向在绘图页上发生变化时会对它求值（“XF”）。  <br/> |[EventXFMod Cell (Events Section)](eventxfmod-cell-events-section.md) <br/> |
|FillBkgnd  <br/> |确定用于形状的填充图案的背景（填充）颜色。  <br/> |[FillBkgnd Cell (Fill Format Section)](fillbkgnd-cell-fill-format-section.md) <br/> |
|FillBkgndTrans  <br/> |确定形状的填充图案的背景（填充）颜色的透明度级别。  <br/> |[FillBkgndTrans Cell (Fill Format Section)](fillbkgndtrans-cell-fill-format-section.md) <br/> |
|FillForegnd  <br/> |确定用于形状的填充图案的前景（划线）颜色。  <br/> |[FillForegnd Cell (Fill Format Section)](fillforegnd-cell-fill-format-section.md) <br/> |
|FillForegndTrans  <br/> |确定形状的填充图案的背景（填充）颜色的透明度级别。  <br/> |[FillForegndTrans Cell (Fill Format Section)](fillforegndtrans-cell-fill-format-section.md) <br/> |
|FillGradientAngle  <br/> |确定具有线性方向的渐变的填充渐变角度 (以度为单位)。  <br/> |[FillGradientAngle 单元格 ("渐变属性" 部分)](fillgradientangle-cell-gradient-properties-section.md) <br/> |
|FillGradientDir  <br/> |确定填充渐变的方向。 渐变可以是线形、放射状、矩形或跟随路径。  <br/> |[FillGradientDir 单元格 ("渐变属性" 部分)](fillgradientdir-cell-gradient-properties-section.md) <br/> |
|FillGradientEnabled  <br/> |确定是否为此形状启用填充渐变。  <br/> |[FillGradientEnabled 单元格 ("渐变属性" 部分)](fillgradientenabled-cell-gradient-properties-section.md) <br/> |
|FillPattern  <br/> |确定形状的填充图案。 要指定自定义的填充图案，请使用本单元格中的 USE 函数。  <br/> |[FillPattern Cell (Fill Format Section)](fillpattern-cell-fill-format-section.md) <br/> |
|FlipX  <br/> |指出形状是否已经水平翻转。  <br/> |[FlipX Cell (Shape Transform Section)](flipx-cell-shape-transform-section.md) <br/> |
|FlipY  <br/> |指出形状是否已经垂直翻转。  <br/> |[FlipY Cell (Shape Transform Section)](flipy-cell-shape-transform-section.md) <br/> |
|FontSchemeIndex  <br/> |确定应用于形状的主题的字体方案, 以整数形式表示。  <br/> |[FontSchemeIndex 单元格 ("主题属性" 部分](fontschemeindex-cell-theme-properties-section.md) <br/> |
|Gamma  <br/> |调整或校正图像的亮度，使之适合特定的输出设备，如监视器或扫描仪等。默认值为 1（不校正）。  <br/> |[Gamma Cell (Image Properties Section)](gamma-cell-image-properties-section.md) <br/> |
|GlowColor  <br/> |确定用于将用于形状的外部发光的描边的颜色, 如 RGB 或主题值。  <br/> |[GlowColor 单元格 ("其他效果属性" 部分)](glowcolor-cell-additional-effect-properties-section.md) <br/> |
|GlowColorTrans  <br/> |确定用于形状发光笔划的颜色的透明度级别, 以百分比表示。  <br/> |[GlowColorTrans 单元格 ("其他效果属性" 部分)](glowcolortrans-cell-additional-effect-properties-section.md) <br/> |
|GlowSize  <br/> |确定形状的外部发光的大小 (以磅为单位)。  <br/> |[GlowSize 单元格 ("其他效果属性" 部分)](glowsize-cell-additional-effect-properties-section.md) <br/> |
|GlueType  <br/> |确定将一维形状粘附到另一个形状时是使用静态粘附（点到点）还是动态粘附（形状到形状）。  <br/> |[GlueType Cell (Glue Info Section)](gluetype-cell-glue-info-section.md) <br/> |
|Height  <br/> |确定以绘图单位表示的形状的高度。  <br/> |[Height Cell (Shape Transform Section)](height-cell-shape-transform-section.md) <br/> |
|HelpTopic  <br/> |指定形状的帮助主题 ID。  <br/> ||
|HideForApply  <br/> |确定样式在 Microsoft Visio 用户界面中的显示位置。  <br/> |[HideForApply Cell (Style Properties Section)](hideforapply-cell-style-properties-section.md) <br/> |
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
|KeepTextFlat  <br/> |指示形状的文本是否将忽略三维中形状的旋转。 不应用于二维旋转。  <br/> |[KeepTextFlat 单元格 ("三维旋转属性" 部分)](keeptextflat-cell-3-d-rotation-properties-section.md) <br/> |
|LangID  <br/> |指示输入注释所使用的语言。  <br/> |[LangID Cell (Annotation Section)](langid-cell-annotation-section.md) <br/> |
|LangID  <br/> |指示输入文本所使用的语言。  <br/> |[LangID Cell (Character Section)](langid-cell-character-section.md) <br/> |
|LangID  <br/> |指示创建单元格公式所使用的语言。  <br/> |[LangID Cell (Miscellaneous Section)](langid-cell-miscellaneous-section.md) <br/> |
|LangID  <br/> |指示输入形状数据值所使用的语言。  <br/> |[LangID Cell (Shape Data Section)](langid-cell-shape-data-section.md) <br/> |
|LayerMember  <br/> |根据页面的图层的从零开始的索引, 指定形状的图层成员资格。 如果将一个形状分配给多个图层, 则每个图层索引以分号分隔。  <br/> ||
|LeftMargin  <br/> |确定文本块左边框和它所包含的文本之间的距离。  <br/> |[LeftMargin Cell (Text Block Format Section)](leftmargin-cell-text-block-format-section.md) <br/> |
|LineAdjustFrom  <br/> |确定在出现动态连接线彼此重叠的情况下应用程序将分隔哪些动态连接线。  <br/> |[LineAdjustFrom Cell (Page Layout Section)](lineadjustfrom-cell-page-layout-section.md) <br/> |
|LineAdjustTo  <br/> |确定哪些动态连接线要彼此重叠。  <br/> |[LineAdjustTo Cell (Page Layout Section)](lineadjustto-cell-page-layout-section.md) <br/> |
|LineCap  <br/> |指示线端形状是圆形、方形还是扩展式。  <br/> |[LineCap Cell (Line Format Section)](linecap-cell-line-format-section.md) <br/> |
|LineColor  <br/> |确定形状的线条颜色。  <br/> |[LineColor Cell (Line Format Section)](linecolor-cell-line-format-section.md) <br/> |
|LineColorTrans  <br/> |确定形状的线条颜色的透明度级别。  <br/> |[LineColorTrans Cell (Line Format Section)](linecolortrans-cell-line-format-section.md) <br/> |
|LineGradientAngle  <br/> |确定线性渐变的线条渐变的角度, 以0到359.9 度为单位。  <br/> |[LineGradientAngle 单元格 ("渐变属性" 部分)](linegradientangle-cell-gradient-properties-section.md) <br/> |
|LineGradientDir  <br/> |确定线条渐变的方向。 渐变可以是线形、放射状、矩形或跟随路径。  <br/> |[LineGradientDir 单元格 ("渐变属性" 部分)](linegradientdir-cell-gradient-properties-section.md) <br/> |
|LineGradientEnabled  <br/> |确定是否为形状的线条或边框启用线条渐变。  <br/> |[LineGradientEnabled 单元格 ("渐变属性" 部分)](linegradientenabled-cell-gradient-properties-section.md) <br/> |
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
|LineWeight  <br/> |确定形状的线条粗细。 通过输入具有有效度量单位的数字即可设置线条粗细。  <br/> |[LineWeight Cell (Line Format Section)](lineweight-cell-line-format-section.md) <br/> |
|LocalizeMerge  <br/> |确定在文档间复制时是否本地化形状。  <br/> |[LocalizeMerge Cell (Miscellaneous Section)](localizemerge-cell-miscellaneous-section.md) <br/> |
|LockAspect  <br/> |锁定形状的纵横比，使形状只能按比例调整大小，而不能单维度调整大小。  <br/> |[LockAspect Cell (Protection Section)](lockaspect-cell-protection-section.md) <br/> |
|LockBegin  <br/> |将一维形状的起点 (BeginX, BeginY) 锁定在特定位置上。  <br/> |[LockBegin Cell (Protection Section)](lockbegin-cell-protection-section.md) <br/> |
|LockCalcWH  <br/> |锁定形状的选择矩形，使得在“Geometry”内容中编辑顶点或更改行类型时，不会重新计算选择矩形。  <br/> |[LockCalcWH Cell (Protection Section)](lockcalcwh-cell-protection-section.md) <br/> |
|LockCrop  <br/> |锁定来自其他程序的对象，防止它被“剪裁”工具剪裁。  <br/> |[LockCrop Cell (Protection Section)](lockcrop-cell-protection-section.md) <br/> |
|LockCustProp  <br/> |确定用户是否可以使用“定义形状数据”对话框或“形状数据”窗口的快捷菜单在用户界面 (UI) 中添加、删除或修改形状数据。  <br/> |[LockCustProp Cell (Protection Section)](lockcustprop-cell-protection-section.md) <br/> |
|LockDelete  <br/> |锁定形状，使它不能被删除。  <br/> |[LockDelete Cell (Protection Section)](lockdelete-cell-protection-section.md) <br/> |
|LockEnd  <br/> |将一维形状的终点 (EndX, EndY) 锁定在特定位置上。  <br/> |[LockEnd Cell (Protection Section)](lockend-cell-protection-section.md) <br/> |
|LockFormat  <br/> |锁定形状的格式，使它无法更改。  <br/> |[LockFormat Cell (Protection Section)](lockformat-cell-protection-section.md) <br/> |
|LockFromGroupFormat  <br/> |阻止将组形状的格式更改传播到其子形状, 同时仍允许用户直接设置选定子形状的格式。 LockFromGroupFormat 单元格的值与“保护”对话框中的“阻止应用组格式”复选框设置相对应。  <br/> |[LockFromGroupFormat 单元格 ("Protection" 部分)](lockfromgroupformat-cell-protection-section.md) <br/> |
|LockGroup  <br/> |锁定某组，使该组不能被取消组合。  <br/> |[LockGroup Cell (Protection Section)](lockgroup-cell-protection-section.md) <br/> |
|LockHeight  <br/> |锁定形状的高度，以便在调整该形状的大小时使其高度保持不变。  <br/> |[LockHeight Cell (Protection Section)](lockheight-cell-protection-section.md) <br/> |
|LockMoveX  <br/> |锁定形状的水平位置，使它不能水平移动。  <br/> |[LockMoveX Cell (Protection Section)](lockmovex-cell-protection-section.md) <br/> |
|LockMoveY  <br/> |锁定形状的垂直位置，使它不能垂直移动。  <br/> |[LockMoveY Cell (Protection Section)](lockmovey-cell-protection-section.md) <br/> |
|LockPreview  <br/> |确定每次保存绘图时是否保存预览。  <br/> |[LockPreview Cell (Document Properties Section)](lockpreview-cell-document-properties-section.md) <br/> |
|LockReplace  <br/> |指示形状是否可以参与替换操作 (作为目标或替换形状)。  <br/> |[LockReplace 单元格 ("Protection" 部分)](lockreplace-cell-protection-section.md) <br/> |
|LockRotate  <br/> |锁定二维形状，以免它随旋转手柄或者“向左旋转 90°”或“向右旋转 90°”命令旋转。  <br/> |[LockRotate Cell (Protection Section)](lockrotate-cell-protection-section.md) <br/> |
|LockSelect  <br/> |防止选取某个形状。  <br/> |[LockSelect Cell (Protection Section)](lockselect-cell-protection-section.md) <br/> |
|LockTextEdit  <br/> |锁定形状的文本，使它无法编辑。  <br/> |[LockTextEdit Cell (Protection Section)](locktextedit-cell-protection-section.md) <br/> |
|LockThemeColors  <br/> |阻止将主题颜色应用到形状。 LockThemeColors 单元格的值与“保护”对话框中的“阻止应用主题颜色”复选框设置相对应。  <br/> |[LockThemeColors 单元格 ("Protection" 部分)](lockthemecolors-cell-protection-section.md) <br/> |
|LockThemeConnectors  <br/> |通过应用新主题或选择新的连接器方案, 防止主题属性行中的 ConnectorsSchemeIndex 单元格被更改。 不会阻止用户在 ShapeSheet 中手动编辑此值。  <br/> |[LockThemeConnectors 单元格 ("Protection" 部分)](lockthemeconnectors-cell-protection-section.md) <br/> |
|LockThemeEffects  <br/> |与 "保护" 对话框中的 "阻止主题效果" 复选框设置相对应。  <br/> |[LockThemeEffects 单元格 ("Protection" 部分)](lockthemeeffects-cell-protection-section.md) <br/> |
|LockThemeFonts  <br/> |通过应用新的主题防止更改主题属性行中的 FontIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。  <br/> |[LockThemeFonts 单元格 ("Protection" 部分)](lockthemefonts-cell-protection-section.md) <br/> |
|LockThemeIndex  <br/> |通过应用新主题或选择新的连接器方案, 防止主题属性行中的 ThemeIndex 单元格被更改。 不会阻止用户在 ShapeSheet 中手动编辑此值。  <br/> |[LockThemeIndex 单元格 ("Protection" 部分)](lockthemeindex-cell-protection-section.md) <br/> |
|LockVariation  <br/> |确定应用于页面或形状的主题变体是否可更改为布尔值。  <br/> |[LockVariation 单元格 ("Protection" 部分)](lockvariation-cell-protection-section.md) <br/> |
|LockVtxEdit  <br/> |锁定形状的顶点，以使它们无法编辑。  <br/> |[LockVtxEdit Cell (Protection Section)](lockvtxedit-cell-protection-section.md) <br/> |
|LockWidth  <br/> |锁定形状的宽度，以便在调整该形状的大小时使其宽度保持不变。  <br/> |[LockWidth Cell (Protection Section)](lockwidth-cell-protection-section.md) <br/> |
|LocPinX  <br/> |表示形状的旋转中心点（旋转中心）相对于形状原点的 x 坐标。 用于确定 LocPinX 的默认公式为: = Width \* 0.5。  <br/> |[LocPinX Cell (Shape Transform Section)](locpinx-cell-shape-transform-section.md) <br/> |
|LockPinY  <br/> |表示形状的旋转中心点（旋转中心）相对于形状原点的 y 坐标。 用于确定 LocPinY 的默认公式为: = Height \* 0.5。  <br/> |[LocPinY Cell (Shape Transform Section)](locpiny-cell-shape-transform-section.md) <br/> |
|NoAlignBox  <br/> |切换选中形状的选择矩形的显示状态 - 显示或不显示。  <br/> |[NoAlignBox Cell (Miscellaneous Section)](noalignbox-cell-miscellaneous-section.md) <br/> |
|NoCoauth  <br/> |设置在合著会话中, 多个作者是否可以同时编辑存储在 SharePoint 2013 服务器或 Microsoft OneDrive 上的文档。  <br/> |[NoCoauth 单元格 ("Document Properties" 内容)](nocoauth-cell-document-properties-section.md) <br/> |
|NoCtlHandles  <br/> |防止在选择形状时显示控制手柄。  <br/> |[NoCtlHandles Cell (Miscellaneous Section)](noctlhandles-cell-miscellaneous-section.md) <br/> |
|NoLiveDynamics  <br/> |确定在您操纵一个形状时，该形状是否动态改变大小或旋转。  <br/> |[NoLiveDynamics Cell (Miscellaneous Section)](nolivedynamics-cell-miscellaneous-section.md) <br/> |
|打印  <br/> |切换选中形状的打印状态 - 启用或禁用。  <br/> |[NonPrinting Cell (Miscellaneous Section)](nonprinting-cell-miscellaneous-section.md) <br/> |
|NoObjHandles  <br/> |切换选中形状的选择手柄的显示状态 - 显示或不显示。  <br/> |[NoObjHandles Cell (Miscellaneous Section)](noobjhandles-cell-miscellaneous-section.md) <br/> |
|NoProofing  <br/> |确定是否会自动更正拼写, 并确定是否将显示所选形状的拼写错误。  <br/> ||
|ObjType  <br/> |确定当使用“配置布局”对话框排放形状时对象在图表中是可放置的还是可穿绕的。  <br/> |[ObjType Cell (Miscellaneous Section)](objtype-cell-miscellaneous-section.md) <br/> |
|OnPage  <br/> |指示是否将绘图打印到指定数量的打印纸上。  <br/> |[OnPage Cell (Print Properties Section)](onpage-cell-print-properties-section.md) <br/> |
|OutputFormat  <br/> |确定绘图的输出格式。 绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。  <br/> |[OutputFormat Cell (Document Properties Section)](outputformat-cell-document-properties-section.md) <br/> |
|PageBottomMargin  <br/> |指定打印页底部的边距。  <br/> |[PageBottomMargin Cell (Print Properties Section)](pagebottommargin-cell-print-properties-section.md) <br/> |
|PageHeight  <br/> |包含以绘图单位表示的打印页面的高度。  <br/> |[PageHeight Cell (Page Properties Section)](pageheight-cell-page-properties-section.md) <br/> |
|PageLeftMargin  <br/> |指定打印页左侧的边距。  <br/> |[PageLeftMargin Cell (Print Properties Section)](pageleftmargin-cell-print-properties-section.md) <br/> |
|PageLineJumpDirX  <br/> |确定在尚未应用本地跨线方向的绘图页内水平动态连接线上的跨线方向。  <br/> |[PageLineJumpDirX Cell (Page Layout Section)](pagelinejumpdirx-cell-page-layout-section.md) <br/> |
|PageLineJumpDirY  <br/> |确定在尚未应用本地跨线方向的绘图页内垂直动态连接线上的跨线方向。  <br/> |[PageLineJumpDirY Cell (Page Layout Section)](pagelinejumpdiry-cell-page-layout-section.md) <br/> |
|PageLockDuplicate  <br/> |确定是否可以将页面复制为布尔值。  <br/> |[PageLockDuplicate 单元格 ("Page Properties" 内容)](pagelockduplicate-cell-page-properties-section.md) <br/> |
|PageLockReplace  <br/> |指示是否应对此页面禁用 "替换形状" 按钮。  <br/> |[PageLockReplace 单元格 ("Page Properties" 内容)](pagelockreplace-cell-page-properties-section.md) <br/> |
|PageRightMargin  <br/> |指定打印页右侧的边距。  <br/> |[PageRightMargin Cell (Print Properties Section)](pagerightmargin-cell-print-properties-section.md) <br/> |
|PageScale  <br/> |确定当前绘图比例中页面单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。  <br/> |[PageScale Cell (Page Properties Section)](pagescale-cell-page-properties-section.md) <br/> |
|PageShapeSplit  <br/> |指示是否可以自动拆分页面上的形状。  <br/> |[PageShapeSplit Cell (Page Layout Section)](pageshapesplit-cell-page-layout-section.md) <br/> |
|PagesX  <br/> |确定从横向适合绘图页的打印纸的数目。  <br/> |[PagesX Cell (Print Properties Section)](pagesx-cell-print-properties-section.md) <br/> |
|PagesY  <br/> |确定从纵向适合绘图页的打印纸的数目。  <br/> |[PagesY Cell (Print Properties Section)](pagesy-cell-print-properties-section.md) <br/> |
|PageTopMargin  <br/> |指定打印页顶部的边距。  <br/> |[PageTopMargin Cell (Print Properties Section)](pagetopmargin-cell-print-properties-section.md) <br/> |
|PageWidth  <br/> |确定以绘图单位表示的打印页面的宽度。  <br/> |[PageWidth Cell (Page Properties Section)](pagewidth-cell-page-properties-section.md) <br/> |
|PaperKind  <br/> |指定打印绘图页的纸张类型。  <br/> |[PaperKind Cell (Print Properties Section)](paperkind-cell-print-properties-section.md) <br/> |
|PaperSource  <br/> |确定页面的纸张来源。  <br/> |[PaperSource Cell (PrintProperties Section)](papersource-cell-printproperties-section.md) <br/> |
|Perspective  <br/> |确定透视旋转的角度角度, 以度为单位 (0 到 359.9)。  <br/> |[透视单元格 ("三维旋转属性" 部分)](perspective-cell-3-d-rotation-properties-section.md) <br/> |
|PinX  <br/> |表示形状的旋转中心点（旋转中心）相对于其父级原点的 x 坐标。  <br/> |[PinX Cell (Shape Transform Section)](pinx-cell-shape-transform-section.md) <br/> |
|PinY  <br/> |表示形状的旋转中心点（旋转中心）相对于其父级原点的 y 坐标。  <br/> |[PinY Cell (Shape Transform Section)](piny-cell-shape-transform-section.md) <br/> |
|PlaceDepth  <br/> |确定在创建布局之前分析绘图使用的方法，并确定布局的类型。  <br/> |[PlaceDepth Cell (Page Layout Section)](placedepth-cell-page-layout-section.md) <br/> |
|PlaceFlip  <br/> |确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）时可放置形状在页面上如何翻转和/或旋转。  <br/> |[PlaceFlip Cell (Page Layout Section)](placeflip-cell-page-layout-section.md) <br/> |
|PlaceStyle  <br/> |确定在“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）中排放形状时如何在页面上放置这些形状。  <br/> |[PlaceStyle 单元格 ("Page Layout" 内容)](placestyle-cell-page-layout-section.md) <br/> |
|PlowCode  <br/> |确定在绘图页上将一个可放置形状放到另一个可放置形状旁边时，可放置形状是否移走。  <br/> |[PlowCode Cell (Page Layout Section)](plowcode-cell-page-layout-section.md) <br/> |
|PreviewQuality  <br/> |确定是以草稿质量显示绘图预览还是以详细视图显示绘图预览。  <br/> |[PreviewQuality Cell (Document Properties Section)](previewquality-cell-document-properties-section.md) <br/> |
|PreviewScope  <br/> |确定您的绘图是否包含预览。如果绘图中确实包含预览，则确定该预览是只显示绘图中的第一页还是显示所有页。  <br/> |[PreviewScope Cell (Document Properties Section)](previewscope-cell-document-properties-section.md) <br/> |
|PrintGrid  <br/> |指定在打印文档页面时是否打印网格。  <br/> |[PrintGrid Cell (Print Properties Section)](printgrid-cell-print-properties-section.md) <br/> |
|PrintPageOrientation  <br/> |确定是纵向打印页面还是横向打印页面。  <br/> |[PrintPageOrientation Cell (Print Properties Section)](printpageorientation-cell-print-properties-section.md) <br/> |
|QuickStyleEffectsMatrix  <br/> |确定形状继承自活动主题的快速样式效果 (以0-6 的整数表示)。  <br/> ||
|QuickStyleFillColor  <br/> |确定形状的填充使用的主题颜色, 作为从0到7的整数。  <br/> |[QuickStyleFillColor 单元格 ("快速样式" 部分)](quickstylefillcolor-cell-quick-style-section.md) <br/> |
|QuickStyleFillMatrix  <br/> |确定形状继承自活动主题的快速样式填充样式 (从0-6 的整数)。  <br/> |[QuickStyleFillMatrix 单元格 ("快速样式" 部分)](quickstylefillmatrix-cell-quick-style-section.md) <br/> |
|QuickStyleFontColor  <br/> |确定从活动主题中的形状的文本继承的快速样式中的字体颜色, 以0-1 形式的整数表示。  <br/> |[QuickStyleFontColor 单元格 ("快速样式" 部分)](quickstylefontcolor-cell-quick-style-section.md) <br/> |
|QuickStyleFontMatrix  <br/> |确定每个快速样式的字体样式 (从1到6的整数)。  <br/> |[QuickStyleFontMatrix 单元格 ("快速样式" 部分)](quickstylefontmatrix-cell-quick-style-section.md) <br/> |
|QuickStyleLineColor  <br/> |确定形状的线条使用哪种主题颜色, 例如从0到7的整数。  <br/> |[QuickStyleLineColor 单元格 ("快速样式" 部分)](quickstylelinecolor-cell-quick-style-section.md) <br/> |
|QuickStyleLineMatrix  <br/> |确定形状继承的快速样式线样式, 如0-6 中的整数。  <br/> |[QuickStyleLineMatrix 单元格 ("快速样式" 部分)](quickstylelinematrix-cell-quick-style-section.md) <br/> |
|QuickStyleShadowColor  <br/> |确定形状的阴影使用哪种主题颜色, 例如从0到7的整数。  <br/> |[QuickStyleShadowColor 单元格 ("快速样式" 部分)](quickstyleshadowcolor-cell-quick-style-section.md) <br/> |
|QuickStyleType  <br/> |确定形状继承的快速样式 (二维、1维或连接符) 的类型。  <br/> |[QuickStyleType 单元格 ("快速样式" 部分)](quickstyletype-cell-quick-style-section.md) <br/> |
|QuickStyleVariation  <br/> |确保形状上的文本、线条和/或填充颜色的可见性以主题的图表背景。  <br/> ||
|ReflectionBlur  <br/> |确定形状上的反射的模糊量, 以磅为单位, 介于0.0 和100.0 之间。  <br/> |[ReflectionBlur 单元格 ("其他效果属性" 部分)](reflectionblur-cell-additional-effect-properties-section.md) <br/> |
|ReflectionDist  <br/> |确定反射相对于形状的偏移距离, 以磅为单位, 从0.0 到100.0。  <br/> |[ReflectionDist 单元格 ("其他效果属性" 部分)](reflectiondist-cell-additional-effect-properties-section.md) <br/> |
|ReflectionSize  <br/> |确定相对于形状的反射的大小, 以0.0 到 100.0% 的百分比。 ReflectionSize 单元格中值为 0% 的形状没有反射;100% 的值显示形状的完整镜像。  <br/> |[ReflectionSize 单元格 ("其他效果属性" 部分)](reflectionsize-cell-additional-effect-properties-section.md) <br/> |
|ReflectionTrans  <br/> |确定反射的透明度, 以0到 100% 的百分比表示。  <br/> |[ReflectionTrans 单元格 ("其他效果属性" 部分)](reflectiontrans-cell-additional-effect-properties-section.md) <br/> |
|关系  <br/> |存储容器、列表、标注和形状之间的关系。  <br/> |["关系" 单元格 ("形状布局" 部分)](relationships-cell-shape-layout-section.md) <br/> |
|ReplaceCopyCells  <br/> |指示在形状替换操作过程中从一个旧形状复制到替换形状的 ShapeSheet 中的单元格列表。  <br/> |[ReplaceCopyCells 单元格 ("更改形状行为" 部分)](replacecopycells-cell-change-shape-behavior-section.md) <br/> |
|ReplaceLockFormat  <br/> |指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 如果主控形状的 ReplaceLockFormat 单元格设置为 TRUE (1), 则主控形状的格式值将覆盖主控形状替换的形状的所有相应值。  <br/> |[ReplaceLockFormat 单元格 ("更改形状行为" 部分)](replacelockformat-cell-change-shape-behavior-section.md) <br/> |
|ReplaceLockShapeData  <br/> |指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 ReplaceLockShapeData 确定主控形状的形状数据是否覆盖正在替换的形状的所有形状数据。  <br/> |[ReplaceLockShapeData 单元格 ("更改形状行为" 部分)](replacelockshapedata-cell-change-shape-behavior-section.md) <br/> |
|ReplaceLockText  <br/> |指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 ReplaceLockText 确定主控形状上显示的文本是否覆盖正在替换的形状的文本。  <br/> |[ReplaceLockText 单元格 ("更改形状行为" 部分)](replacelocktext-cell-change-shape-behavior-section.md) <br/> |
|ResizeMode  <br/> |显示形状的当前调整大小行为设置。  <br/> |[ResizeMode Cell (Shape Transform Section)](resizemode-cell-shape-transform-section.md) <br/> |
|ResizePage  <br/> |确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状后是否放大页面以装入绘图。  <br/> |[ResizePage Cell (Page Layout Section)](resizepage-cell-page-layout-section.md) <br/> |
|RightMargin  <br/> |确定文本块的右边框和它所包含的文本之间的距离。 默认值是 0.1 英寸。  <br/> |[RightMargin Cell (Text Block Format Section)](rightmargin-cell-text-block-format-section.md) <br/> |
|RotateGradientWithShape  <br/> |确定是否以布尔值的形式在2D 旋转中将填充渐变旋转。  <br/> |[RotateGradientWithShape 单元格 ("渐变属性" 部分)](rotategradientwithshape-cell-gradient-properties-section.md) <br/> |
|RotationType  <br/> |确定形状是采用平行旋转、透视旋转还是倾斜旋转, 为0到6的整数。  <br/> |[RotationType 单元格 ("三维旋转属性" 部分)](rotationtype-cell-3-d-rotation-properties-section.md) <br/> |
|RotationXAngle  <br/> |确定沿 X 轴旋转的角度 (以度为单位) (0.0-359.9)。  <br/> |[RotationXAngle 单元格 ("三维旋转属性" 部分)](rotationxangle-cell-3-d-rotation-properties-section.md) <br/> |
|RotationYAngle  <br/> |确定沿 Y 轴旋转的角度 (以度为单位) (0.0-359.9)。  <br/> |[RotationYAngle 单元格 ("三维旋转属性" 部分)](rotationyangle-cell-3-d-rotation-properties-section.md) <br/> |
|RotationZAngle  <br/> |确定旋转沿 Z 轴旋转的角度 (以度为单位) (0.0-359.9)。  <br/> |[RotationZAngle 单元格 ("三维旋转属性" 部分)](rotationzangle-cell-3-d-rotation-properties-section.md) <br/> |
|Rounding  <br/> |指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。  <br/> |[Rounding Cell (Line Format Section)](rounding-cell-line-format-section.md) <br/> |
|RouteStyle  <br/> |在没有本地排列样式的绘图页上确定所有连接线的排列样式和方向。  <br/> |[RouteStyle Cell (Page Layout Section)](routestyle-cell-page-layout-section.md) <br/> |
|ScaleX  <br/> |指定绘图页在打印纸上的比例百分比。  <br/> |[ScaleX Cell (Print Properties Section)](scalex-cell-print-properties-section.md) <br/> |
|ScaleY  <br/> |指定绘图页在打印纸上的比例百分比。  <br/> |[ScaleY Cell (Print Properties Section)](scaley-cell-print-properties-section.md) <br/> |
|SelectMode  <br/> |确定如何选择组合形状及其组成部分。  <br/> |[SelectMode Cell (Group Properties Section)](selectmode-cell-group-properties-section.md) <br/> |
|ShapeFixedCode 单元格  <br/> |指定可放置形状的放置行为。  <br/> |[ShapeFixedCode Cell (Shape Layout Section)](shapefixedcode-cell-shape-layout-section.md) <br/> |
|ShapeKeywords  <br/> |包含已分配给主控形状的搜索关键字。  <br/> ||
|ShapePermeablePlace  <br/> |确定在“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）中排放形状时，可放置形状是否可以放置在某个形状的顶部。  <br/> |[ShapePermeablePlace Cell (Shape Layout Section)](shapepermeableplace-cell-shape-layout-section.md) <br/> |
|ShapePermeableX  <br/> |确定连接线是否可以水平穿绕可放置形状。  <br/> |[ShapePermeableX Cell (Shape Layout Section)](shapepermeablex-cell-shape-layout-section.md) <br/> |
|ShapePermeableY  <br/> |确定连接线是否可以垂直穿绕形状。  <br/> |[ShapePermeableY Cell (Shape Layout Section)](shapepermeabley-cell-shape-layout-section.md) <br/> |
|ShapePlaceFlip  <br/> |确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状时，可放置形状在页面上如何翻转、旋转或同时翻转和旋转。  <br/> |[ShapePlaceFlip Cell (Shape Layout Section)](shapeplaceflip-cell-shape-layout-section.md) <br/> |
|ShapePlaceStyle  <br/> |指定在 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 中排放形状时, 形状在页面上的放置方式。 存储 VisCellIndices 中的布局样式和对齐方式值。  <br/> |[ShapePlaceStyle 单元格 ("Shape Layout" 内容)](shapeplacestyle-cell-shape-layout-section.md) <br/> |
|ShapePlowCode  <br/> |确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。  <br/> |[ShapePlowCode Cell (Shape Layout Section)](shapeplowcode-cell-shape-layout-section.md) <br/> |
|ShapeRouteStyle  <br/> |确定绘图页上所选连接线的排列样式和方向。  <br/> |[ShapeRouteStyle Cell (Shape Layout Section)](shaperoutestyle-cell-shape-layout-section.md) <br/> |
|ShapeShdwBlur  <br/> |确定形状的阴影的模糊大小, 以磅为单位 (0.00 到 100.00)。  <br/> |[ShapeShdwBlur 单元格 ("填充格式" 部分)](shapeshdwblur-cell-fill-format-section.md) <br/> |
|ShapeShdwObliqueAngle  <br/> |指定形状阴影倾斜方向的角度。  <br/> |[ShapeShdwObliqueAngle Cell (Fill Format Section)](shapeshdwobliqueangle-cell-fill-format-section.md) <br/> |
|ShapeShdwOffsetX  <br/> |确定形状的阴影与该形状水平偏移的距离（按页面单位）。  <br/> |[ShapeShdwOffsetX Cell (Fill Format Section)](shapeshdwoffsetx-cell-fill-format-section.md) <br/> |
|ShapeShdwOffsetY  <br/> |确定形状的阴影与该形状垂直偏移的距离（按页面单位）。  <br/> |[ShapeShdwOffsetY Cell (Fill Format Section)](shapeshdwoffsety-cell-fill-format-section.md) <br/> |
|ShapeShdwScaleFactor  <br/> |指定形状阴影可放大或缩小的百分比。  <br/> |[ShapeShdwScaleFactor Cell (Fill Format Section)](shapeshdwscalefactor-cell-fill-format-section.md) <br/> |
|ShapeShdwShow  <br/> |确定形状是否显示阴影, 以从0到2的整数。  <br/> |[ShapeShdwShow 单元格 ("填充格式" 部分)](shapeshdwshow-cell-fill-format-section.md) <br/> |
|ShapeShdwType  <br/> |指定形状的阴影类型。  <br/> |[ShapeShdwType Cell (Fill Format Section)](shapeshdwtype-cell-fill-format-section.md) <br/> |
|ShapeSplit  <br/> |指示此形状是否可以拆分其他可拆分的形状。  <br/> |[ShapeSplit Cell (Shape Layout Section)](shapesplit-cell-shape-layout-section.md) <br/> |
|ShapeSplittable  <br/> |指示此一维形状是否可以拆分。  <br/> |[ShapeSplittable Cell (Shape Layout Section)](shapesplittable-cell-shape-layout-section.md) <br/> |
|强化  <br/> |锐化位图图像。 默认值是 0%。 通过增加相邻像素的对比度来锐化图像可以使图像更鲜明。  <br/> |[Sharpen Cell (Image Properties Section)](sharpen-cell-image-properties-section.md) <br/> |
|ShdwForegnd  <br/> |确定用于形状的投影填充图案的前景（划线）的颜色。  <br/> |[ShdwForegnd Cell (Fill Format Section)](shdwforegnd-cell-fill-format-section.md) <br/> |
|ShdwForegndTrans  <br/> |确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。  <br/> |[ShdwForegndTrans Cell (Fill Format Section)](shdwforegndtrans-cell-fill-format-section.md) <br/> |
|ShdwObliqueAngle  <br/> |包含指定应用默认页面阴影类型时的倾斜方向角度的数字。  <br/> |[ShdwObliqueAngle Cell (Page Properties Section)](shdwobliqueangle-cell-page-properties-section.md) <br/> |
|ShdwOffsetX  <br/> |确定形状的投影与该形状水平偏移的距离（按页面单位）。  <br/> |[ShdwOffsetX Cell (Page Properties Section)](shdwoffsetx-cell-page-properties-section.md) <br/> |
|ShdwOffsetY  <br/> |确定形状的投影与该形状垂直偏移的距离（按页面单位）。  <br/> |[ShdwOffsetY Cell (Page Properties Section)](shdwoffsety-cell-page-properties-section.md) <br/> |
|ShdwPattern  <br/> |确定某一形状的阴影的填充图案。  <br/> |[ShdwPattern Cell (Fill Format Section)](shdwpattern-cell-fill-format-section.md) <br/> |
|ShdwScaleFactor  <br/> |指定放大或缩小形状阴影的百分比。  <br/> |[ShdwScaleFactor Cell (Page Properties Section)](shdwscalefactor-cell-page-properties-section.md) <br/> |
|ShdwType  <br/> |指示页面的默认阴影类型。  <br/> |[ShdwType Cell (Page Properties Section)](shdwtype-cell-page-properties-section.md) <br/> |
|SketchAmount  <br/> |确定草图效果的扭曲量, 以0到25之间的整数表示。  <br/> |[SketchAmount 单元格 ("其他效果属性" 部分)](sketchamount-cell-additional-effect-properties-section.md) <br/> |
|SketchEnabled  <br/> |确定是否在形状上显示草图效果, 作为一个布尔值。  <br/> |[SketchEnabled 单元格 ("其他效果属性" 部分)](sketchenabled-cell-additional-effect-properties-section.md) <br/> |
|SketchFillChange  <br/> |根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形的随机填充量。 如果 SketchFillChange 单元格的值设置为 0%, 则形状的填充的边界几何图形与形状的几何图形相匹配。 如果值为 100%, 则该形状的填充的边界几何图形不遵循形状的几何图形。  <br/> |[SketchFillChange 单元格 ("其他效果属性" 部分)](sketchfillchange-cell-additional-effect-properties-section.md) <br/> |
|SketchLineChange  <br/> |根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形中形状的线条的随机量。 如果 SketchLineChange 单元格的值设置为 0%, 则形状的线条的几何图形将与形状的几何图形相匹配。 如果值为 100%, 则形状的线条的几何图形不遵循形状的几何图形。  <br/> |[SketchLineChange 单元格 ("其他效果属性" 部分)](sketchlinechange-cell-additional-effect-properties-section.md) <br/> |
|SketchLineWeight  <br/> |确定作为素描效果的结果添加到线条粗细的额外厚度, 以从0到50的磅为单位。 当 SketchLineWeight 单元格的值增加时, 该形状的线条的粗细将增加。  <br/> |[SketchLineWeight 单元格 ("其他效果属性" 部分)](sketchlineweight-cell-additional-effect-properties-section.md) <br/> |
|SketchSeed  <br/> |表示用于确定草图效果几何图形的随机值, 以正整数表示。 将草图效果应用于形状时, 会随机创建 SketchSeed 单元格的值。  <br/> |[SketchSeed 单元格 ("其他效果属性" 部分)](sketchseed-cell-additional-effect-properties-section.md) <br/> |
|SoftEdgesSize  <br/> |确定柔化边缘效果的大小, 以磅为单位, 以0.00 到100.00。 如果 SoftEdgesSize 单元格的值为 0, 则该形状没有柔化边缘。  <br/> |[SoftEdgesSize 单元格 ("其他效果属性" 部分)](softedgessize-cell-additional-effect-properties-section.md) <br/> |
|TextBkgnd  <br/> |确定一个形状的文本背景色。  <br/> |[TextBkgnd Cell (Text Block Format Section)](textbkgnd-cell-text-block-format-section.md) <br/> |
|TextBkgndTrans  <br/> |确定形状的文本块背景色的透明度级别。  <br/> |[TextBkgndTrans Cell (Text Block Format Section)](textbkgndtrans-cell-text-block-format-section.md) <br/> |
|TextDirection  <br/> |确定文本块中字符的方向。  <br/> |[TextDirection Cell (Text Block Format Section)](textdirection-cell-text-block-format-section.md) <br/> |
|TheData  <br/> |保留供以后使用。  <br/> |[TheData Cell (Events Section)](thedata-cell-events-section.md) <br/> |
|ThemeIndex  <br/> |将应用于文档的内置 Microsoft Visio 主题的枚举存储为一个整数。 为文档选择新主题时, 将使用内置主题的索引更新文档的 ThemeIndex 单元格以及它包含的所有页面和形状。  <br/> |[ThemeIndex 单元格 ("主题属性" 部分)](themeindex-cell-theme-properties-section.md) <br/> |
|TheText  <br/> |当形状文本或文本组成成分改变时进行求值的事件单元格。  <br/> |[TheText Cell (Events Section)](thetext-cell-events-section.md) <br/> |
|TopMargin  <br/> |确定文本块的上边界和它包含的第一行文本之间的距离。默认值是 4.0000 磅。此值与绘图比例无关。即使对绘图比例进行了调整，上边距仍保持不变。  <br/> |[TopMargin Cell (Text Block Format Section)](topmargin-cell-text-block-format-section.md) <br/> |
|Transparency  <br/> |确定形状的某一范围文本颜色的透明度级别。  <br/> |[Transparency Cell (Character Section)](transparency-cell-character-section.md) <br/> |
|Transparency  <br/> |确定图层颜色的透明度级别。  <br/> |[Transparency Cell (Image Properties Section)](transparency-cell-image-properties-section.md) <br/> |
|Transparency  <br/> |确定图层颜色的透明度级别。  <br/> |[Transparency Cell (Layers Section)](transparency-cell-layers-section.md) <br/> |
|TxtAngle  <br/> |确定文本块当前相对于形状的 x 轴坐标的旋转角度。 默认值是 0 度。  <br/> |[TxtAngle Cell (Text Transform Section)](txtangle-cell-text-transform-section.md) <br/> |
|TxtHeight  <br/> |确定文本块的高度。 默认公式为: = Height \* 1  <br/> |[TxtHeight Cell (Text Transform Section)](txtheight-cell-text-transform-section.md) <br/> |
|TxtLocPinX  <br/> |确定文本块的旋转中心相对于文本块原点的 x 坐标。 默认公式为: = TxtWidth \* 0.5。此公式计算为文本块的水平中心。  <br/> |[TxtLocPinX Cell (Text Transform Section)](txtlocpinx-cell-text-transform-section.md) <br/> |
|TxtLocPinY  <br/> |确定文本块的旋转中心相对于文本块原点的 y 坐标。 默认公式为: = TxtHeight \* 0。5  <br/> |[TxtLocPinY Cell (Text Transform Section)](txtlocpiny-cell-text-transform-section.md) <br/> |
|TxtPinX  <br/> |确定文本块的旋转中心相对于形状原点的 x 坐标。 默认公式为: = 宽度\* 0。5  <br/> |[TxtPinX Cell (Text Transform Section)](txtpinx-cell-text-transform-section.md) <br/> |
|TxtPinY  <br/> |确定文本块的旋转中心相对于形状原点的 y 坐标。 默认公式为: = 高度\* 0。5  <br/> |[TxtPinY Cell (Text Transform Section)](txtpiny-cell-text-transform-section.md) <br/> |
|TxtWidth  <br/> |确定文本块的宽度。 默认公式为: = 宽度\* 1  <br/> |[TxtWidth Cell (Text Transform Section)](txtwidth-cell-text-transform-section.md) <br/> |
|UIVisibility  <br/> |确定用户界面 (UI) 中是否显示页名称。  <br/> |[UIVisibility Cell (Page Properties Section)](uivisibility-cell-page-properties-section.md) <br/> |
|UpdateAlignBox  <br/> |只要移动控制手柄，就重新计算选择矩形。  <br/> |[UpdateAlignBox Cell (Miscellaneous Section)](updatealignbox-cell-miscellaneous-section.md) <br/> |
|UseGroupGradient  <br/> |确定形状与其他形状组合在一起时是否采用渐变, 作为布尔值。 UseGroupGradient 单元格的值仅影响形状填充。  <br/> |[UseGroupGradient 单元格 ("渐变属性" 部分)](usegroupgradient-cell-gradient-properties-section.md) <br/> |
|VariationColorIndex  <br/> |以整数形式确定页面上活动主题变体的颜色索引。  <br/> |[VariationColorIndex 单元格 ("主题属性" 部分)](variationcolorindex-cell-theme-properties-section.md) <br/> |
|VariationStyleIndex  <br/> |以整数形式确定页面上活动主题变体的样式索引。  <br/> |[VariationStyleIndex 单元格 ("主题属性" 部分)](variationstyleindex-cell-theme-properties-section.md) <br/> |
|VerticalAlign  <br/> |确定文本块内文本的垂直对齐方式。  <br/> |[VerticalAlign Cell (Text Block Format Section)](verticalalign-cell-text-block-format-section.md) <br/> |
|ViewMarkup  <br/> |确定绘图窗口中是否显示标记。  <br/> |[ViewMarkup Cell (Document Properties Section)](viewmarkup-cell-document-properties-section.md) <br/> |
|WalkPreference  <br/> |确定一维形状的端点是否移到其所粘附的形状的水平或垂直连接点上（当形状移到不明确的位置上时，使用动态粘附）。默认情况下，一维形状的两个端点都移到水平连接点上。  <br/> |[WalkPreference Cell (Glue Info Section)](walkpreference-cell-glue-info-section.md) <br/> |
|Width  <br/> |包含所选形状的宽度（以绘图单位计）。 用于确定一维形状宽度的默认公式为: = SQRT ((EndX-BeginX) ^ 2 + (EndY-BeginY) ^ 2)  <br/> |[Width Cell (Shape Transform Section)](width-cell-shape-transform-section.md) <br/> |
|XGridDensity  <br/> |指定要使用的水平网格的类型。  <br/> |[XGridDensity 单元格 ( &amp; "标尺网格" 部分)](xgriddensity-cell-rulergrid-section.md) <br/> |
|XGridOrigin  <br/> |指定网格原点的水平坐标。  <br/> |[XGridOrigin 单元格 ( &amp; "标尺网格" 部分)](xgridorigin-cell-rulergrid-section.md) <br/> |
|XGridSpacing  <br/> |指定固定网格中水平线条间的距离 (XGridDensity = 0)。  <br/> |[XGridSpacing 单元格 ( &amp; "标尺网格" 部分)](xgridspacing-cell-rulergrid-section.md) <br/> |
|XRulerDensity  <br/> |指定页面标尺上的水平细分线。  <br/> |[XRulerDensity 单元格 ( &amp; "标尺网格" 部分)](xrulerdensity-cell-rulergrid-section.md) <br/> |
|XRulerOrigin  <br/> |指定页面 x 轴标尺上的零点。  <br/> |[XRulerOrigin 单元格 ( &amp; "标尺网格" 部分)](xrulerorigin-cell-rulergrid-section.md) <br/> |
|YGridDensity  <br/> |指定要使用的垂直网格的类型。  <br/> |[YGridDensity 单元格 ( &amp; "标尺网格" 部分)](ygriddensity-cell-rulergrid-section.md) <br/> |
|YGridOrigin  <br/> |指定网格的垂直起点。  <br/> |[YGridOrigin 单元格 ( &amp; "标尺网格" 部分)](ygridorigin-cell-rulergrid-section.md) <br/> |
|YGridSpacing  <br/> |指定固定网格中垂直线条间的距离 (YGridDensity = 0)。  <br/> |[YGridSpacing 单元格 ( &amp; "标尺网格" 部分)](ygridspacing-cell-rulergrid-section.md) <br/> |
|YRulerDensity  <br/> |指定页面标尺上的垂直细分线。  <br/> |[YRulerDensity 单元格 ( &amp; "标尺网格" 部分)](yrulerdensity-cell-rulergrid-section.md) <br/> |
|YRulerOrigin  <br/> |指定页面 y 轴标尺上的零点。  <br/> |[YRulerOrigin 单元格 ( &amp; "标尺网格" 部分)](yrulerorigin-cell-rulergrid-section.md) <br/> |
   

