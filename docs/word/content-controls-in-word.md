---
title: Word 中的内容控件
manager: soliver
ms.date: 09/10/2015
ms.audience: Developer
keywords:
- 内容控件 [单词]，内容控件 [单词] 新增功能
localization_priority: Normal
ms.assetid: c0e6dd3b-fae1-453d-a9b4-7f456b5172db
description: 了解 Microsoft Word 2013 内容控件如何实现更大范围的结构化的文档方案。
ms.openlocfilehash: 1b0b88da4bc3347ac6748ab57b99d45edd57558d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781761"
---
# <a name="content-controls-in-word"></a>Word 中的内容控件

了解 Microsoft Word 2013 内容控件如何实现更大范围的结构化的文档方案。

本主题提供有关在 Microsoft Word 2013 和启用这些更改的文档方案中的内容控件的更改的信息。
  
### <a name="structured-documents"></a>结构化文档
<a name="WordCC_StructuredDocs"> </a>

结构化文档是这样一种文档，控制内容可以在文档的何处显示，文档中可以显示的内容类型以及能否编辑此内容。
  
下面是在 Microsoft Word 中的结构化内容的常见方案：
  
- 法律公司需要创建一些文档，其中包含用户不应更改的法律用语。
    
- 企业需要创建用户只可以输入标题、作者和日期的计划书封面。
    
- 企业需要创建一些发票，其中客户数据包含在发票预定义区域中。
    
### <a name="using-content-controls-to-structure-a-document"></a>使用内容控件来构建文档
<a name="WordCC_StructuredDocs"> </a>

内容控件是充当容器的文档中的特定内容的 Microsoft Word 实体。 单个内容控件可以包含格式化文本的日期、列表或段落等内容。 内容控制帮助您创建丰富、 结构化内容块，并设计用于定义完善的块插入文档中，创建结构化的文档的模板。
  
内容控件非常适合创建结构化的文档，因为内容控件可以帮助您修复内容的位置，指定内容类型（例如，日期、图片或文本），限制或启用编辑，以及将语义含义添加到内容中。
  
### <a name="content-controls-in-word-2010"></a>Word 2010 中的内容控件
<a name="WordCC_StructuredDocs"> </a>

以下内容控件是在 Word 2010 中可用：
  
- 格式文本
    
- 纯文本
    
- 图片
    
- 构建基块库
    
- 组合框
    
- 下拉列表
    
- 日期
    
- 复选框
    
- 组
    
Word 2010 内容控件启用各种潜在的结构化的文档解决方案，但内容控件在 Word 2013 中启用更大范围的应用场景。
  
## <a name="content-control-improvements-in-word-2013"></a>Word 2013 中的内容控件改进
<a name="WordCC_WhatsNew"> </a>

内容控件在 Word 2013 中提供了三个重要改进： 改进可视化、 支持的 XML 映射格式文本内容控件和新的内容控件的重复的内容。
  
### <a name="improved-visualization"></a>改进的可视化

Word 2013 允许单个内容控件中三种可能的状态之一：
  
- 边界框
    
- 开始/结束标记
    
- 无
    
> [!NOTE]
> 如果不声明，否则本部分将讨论可视化的内容控件时不在**设计模式中**查看该文档。使用**内容控件属性**对话框中**显示为**下拉列表控件设置内容控件的显示的模式。 
  
**图 1. 内容控件属性对话框**

![内容控件属性对话框](media/DK2_WordCC_Fig01.jpg "内容控件属性对话框")
  
您还可以通过使用 Word 2013 对象模型 （在下文中[新的 Word 2013 内容控件对象模型成员](#WordCC_NewOM)讨论） 设置内容控件的显示的模式。
  
### <a name="bounding-box"></a>边界框
<a name="WordCC_DefaultRendering"> </a>

Word 2013 中的内容控件的默认呈现是按它们出现在 Word 2007 和 Word 2010; 保留内容控件的外观即边界框。 如果内容控件设置为显示**边界框**中，具体取决于以下的用户交互的显示更改为：
  
- 在内容控件没有焦点时，无可视化效果
    
- 鼠标悬停在内容控件上时，显示为阴影矩形
    
**图 2. 鼠标悬停在内容控件上**

![通过内容鼠标上的控件](media/DK2_WordCC_Fig02.jpg "通过内容鼠标上的控件")
  
- 在内容控件有焦点时（在用户选择此内容控件时），该控件显示为“边界框”（如果设置了标题，则围绕着内容和标题显示一行）
    
**图 3. 具有焦点的内容控件**

![内容具有焦点的控件](media/DK2_WordCC_Fig03.jpg "内容具有焦点的控件")
  
### <a name="startend-tags"></a>开始/结束标记
<a name="WordCC_StartEndTags"> </a>

当内容控件设置为显示为**开始/结束标记**时，无论用户交互，显示标记，然后标题永远不会显示;但位于通过鼠标按钮，如**下拉列表**按钮。 
  
**图 4. 设置内容控件显示为开始/结束标记**

![内容控件设置为显示开始和结束标记](media/DK2_WordCC_Fig04.jpg "内容控件设置为显示开始和结束标记")
  
### <a name="none"></a>无
<a name="WordCC_Invisible"> </a>

当内容控件设置为显示为**无**时，不显示的内容控件。
  
### <a name="content-control-colorization"></a>内容控件着色
<a name="WordCC_CCColorization"> </a>

除了启用不同种类的内容控件的显示，Word 2013 还有助于您设置单个内容控件的颜色。 在**内容控件属性**对话框中，使用**颜色**按钮设置内容控件的颜色。 
  
您还可以通过使用 Word 2013 对象模型 （在下文中[新的 Word 2013 内容控件对象模型成员](#WordCC_NewOM)讨论） 设置内容控件的颜色。
  
**图 5. 内容控件属性对话框**

![内容控件属性对话框](media/DK2_WordCC_Fig05.jpg "内容控件属性对话框")
  
### <a name="support-for-xml-mapping-for-rich-text-content-controls"></a>支持格式文本内容控件的 XML 映射
<a name="WordCC_XMLMapping"> </a>

Word 2013 可帮助您将使用格式文本内容控件和文档构建基块内容控件的内容映射到 XML 数据存储区。 若要执行此操作，则设置内容控件的*XML 映射*。 您可以使用对象模型中的现有**XMLMapping.SetMapping**方法设置此属性。 自定义 XML 存储中的自定义 XML 部件，如下平面 Open XML 标记转换为字符串 （通过使用标准的 XML 编码），因此，它可以存储为自定义 XML 部件中的文本节点。 但是，映射用户都继续拥有可以仅成功映射到叶节点或属性的限制。 
  
> [!NOTE]
> 格式文本内容控件不能包含其他格式文本内容控件。如果一个格式文本内容控件位于另一个格式文本内容控件之中（例如，由于文件格式操作、复制和粘贴等），则它处于未链接的状态，直到它不再包含在一个映射的格式文本控件之中。 
  
有关如何设置 XML 映射的详细信息，请参阅本主题后面的[新的 Word 2013 内容控件对象模型成员](#WordCC_NewOM)一节。 
  
### <a name="supporting-repeating-content"></a>支持重复内容
<a name="WordCC_SupportingRepeating"> </a>

除了可视化增强功能和支持的 XML 映射到格式文本内容控件，Word 2013 也添加新的内容控件，使您能够重复内容。 重复节内容控件重复所包含的内容，包括其他内容控件。
  
您可以围绕整个段落或表行插入重复的节内容控件。一旦此控件包围一节，您可以在所包含的节的上方或下方插入该节的副本。
  
**图 6. 重复节内容控件上下文菜单**

![重复节内容控件上下文](media/DK2_WordCC_Fig06.jpg "重复节内容控件上下文")
  
图 6 中所示，可以通过使用一端 （显示为带加号 （![+ 号](media/DK2_WordCC_Fig06A.jpg "加号")） 按钮） 的内容控件的控件或选择上下文菜单中，在命令重复插入部分。 重复的内容将成为一个单独的节，这样就可以分配一个标题，使用**内容控件属性**对话框中的控件。 
  
**图 7. 在内容控件属性对话框中指定节标题**

![内容控件属性对话框](media/DK2_WordCC_Fig07.jpg "内容控件属性对话框")
  
一旦已授予部分中一个标题，如果在**内容控件属性**对话框中选择**允许用户添加和删除节**，用户可以通过添加或删除部分名称。 
  
**图 8. 使用重复节内容控件上下文菜单来删除节**

![重复节内容控件上下文](media/DK2_WordCC_Fig08.jpg "重复节内容控件上下文")
  
当重复节内容控件包围其他内容控件时，封装的内容控件在每个新项中重复；但是任何此类内容控件都将其内容重置为占位符文本。有两个保留了子控件内容的例外情况： 
  
- 当子控件为重复节控件时。
    
- 当子控件为 XML 映射到的重复节内容控件外部的节点时。
    
**图 9. 重复节内容控件在重复前包含子控件**

![重复节内容控件之前重复](media/DK2_WordCC_Fig09.jpg "重复节内容控件之前重复")
  
**图 10. 重复节内容控件在重复后包含子控件**

![重复节内容控件后重复](media/DK2_WordCC_Fig10.jpg "重复节内容控件后重复")
  
### <a name="repeating-section-content-controls-around-xml-mapped-controls"></a>围绕 XML 映射的控件的重复节内容控件
<a name="WordCC_RepeatingSectionCCs"> </a>

重复节中包含的 XML 映射，Word 2013 将它们映射，如下所示。
  
如果与中的节点集作为其父链的一部分的项不相交映射，绑定是"绝对绑定"，并显示相同的内容中所有重复节项目。
  
如果映射执行相交与项目中的节点集作为其父链的一部分，绑定是一个"相对绑定"，并重新映射，如下所示：
  
- 确定节点的绝对绑定（延展任何查询表达式）─ 这应该在初始映射时发生
    
- 删除与节点集交叉的绑定轴
    
- 相对于 XPath 的重复节内容项评估 XPath 的其余部分
    
例如，可能发生以下映射：
  
- 重复节映射到 \root\next\path
    
- 示例项中的控件映射到 \root\next\path[2]\baz
    
- Word 将 \root\next\path[2] 匹配到节点集中的某个项
    
因此，将此绑定作为 .\baz 进行评估，其中的基础是重复内容项的节点。
  
使用重复内容控件的以下建议可以帮助您防止数据丢失，并避免产生挫折感。
  
### <a name="working-with-repeating-section-content-controls-that-are-mapped-to-xml-data"></a>使用映射到 XML 数据的重复节内容控件
<a name="WordCC_RepeatingSectionCCs"> </a>

如果插入重复节内容控件映射到 XML 数据，每次用户重新打开文档时，Word 将重新创建基于数据存储中的信息的重复节项。 即使保存文档时，用户在重复节项目文档中还不是映射到数据存储区进行任何更改都将丢失。
  
若要有助于防止这种情况发生，请锁定重复节内容控件，并允许用户只在映射到 XML 的未锁定子内容控件中进行编辑。
  
### <a name="binding-a-repeating-section-content-control-to-a-table"></a>将重复节内容控件绑定到表
<a name="WordCC_RepeatingSectionCCs"> </a>

如果您想要重复节内容控件绑定到表，插入表*然后*插入重复节内容控件，并不是其他方法周围。 （否则，您将无法选择仅的表）。 
  
### <a name="nesting-repeating-section-content-controls-within-a-table"></a>在表中嵌套重复节内容控件
<a name="WordCC_RepeatingSectionCCs"> </a>

当添加或删除内部节的一个项时，在表中紧密地嵌套重复节内容控件（例如，当父和子的重复节内容控件的末尾位于同一单元格时）会导致删除外部重复节。
  
如果不希望发生，可以添加一个重复节内容控件的末尾和下一行文本之间的段落标记。 若要隐藏段落标记，取消选中功能区的**主页**选项卡上的**显示/隐藏**选项。 
  
### <a name="open-xml-file-format-schema-additions"></a>Open XML 文件格式架构的添加项
<a name="WordCC"> </a>

以下元素添加到 WordprocessingML Open XML 文件格式架构中。
  
**表 1. 适用于内容控件的 WordprocessingML Open XML 文件格式架构中的新元素**

|**元素**|**说明**|
|:-----|:-----|
|\<w:appearance\>  <br/> |\<w:appearance\>是子元素的\<w:sdtPr\>。  <br/> 以下值对 val 属性有效：  <br/> \<w:appearance val = boundingBox|标记前添加的标记|隐藏。  <br/> 默认值为 boundingBox。  <br/> |
|\<w:color\>  <br/> |\<w:color\>是子元素的\<w:sdtPr\>。  <br/> 此内容模型与现有的 CT_Color 复杂类型相匹配。默认值是 Word 2010 中所使用的颜色。  <br/> |
   
## <a name="new-word-2013-content-control-object-model-members"></a>新的 Word 2013 内容控件对象模型成员
<a name="WordCC_NewOM"> </a>

新的增强功能和内容控件在 Word 2013 中的新增功能，已更新 Word 对象模型，以允许的新功能集编程操作。 此外，还进行了更改为字处理文档的基础 Open XML 文件格式。
  
以下几节提供与每个内容控件增强功能相关的特定对象模型更改的详细信息。
  
### <a name="visualization-enhancements"></a>可视化增强功能
<a name="WordCC_VisEnhancements"> </a>

Word 2013 中的内容控件可视化增强功能包括几个对象模型新增内容。 下表列出可视化的**ContentControl**对象的新成员。 
  
**表 2. 新 ContentControl 对象成员**

|**成员**|**说明**|
|:-----|:-----|
|. 作为**WdContentControlAppearance**的**外观** <br/> |获取或设置内容控件的可视化。  <br/> |
|. **颜色**为**WdColor** <br/> |获取或设置内容控件的颜色。  <br/> |
   
下表列出了新 **WdContentControlAppearance** 枚举中的常量。 
  
**表 3. 新 WdContentControlAppearance 枚举的常量**

|**常量**|**说明**|
|:-----|:-----|
|**wdContentControlBoundingBox** <br/> |表示显示为阴影矩形/边界框（带可选标题）的内容控件。  <br/> |
|**wdContentControlTags** <br/> |表示显示为开始/结束标记的内容控件。  <br/> |
|**wdContentControlHidden** <br/> |表示未显示的内容控件。  <br/> |
   
### <a name="code-sample"></a>代码示例
<a name="WordCC_VisEnhancements"> </a>

以下代码示例说明如何创建格式文本内容控件以及如何以编程方式设置可视化。
  
```vb
Sub testVisualization()
   Dim objcc As ContentControl
   Dim objRange As Range
   
   ' Get the first paragraph as a range object.
   Set objRange = ActiveDocument.Paragraphs(1).Range
   ' Create a rich text content control around the first paragraph.
   Set objcc = ActiveDocument.ContentControls.Add(wdContentControlRichText, objRange)
   objcc.Title = "Default Bounding Box"
   ' Set visualization to the default.
   objcc.Appearance = wdContentControlBoundingBox
   
   ' Create a new paragraph.
   objRange.InsertParagraphAfter
   Set objRange = ActiveDocument.Paragraphs(2).Range
   ' Create a rich text content control around the second paragraph.
   Set objcc = ActiveDocument.ContentControls.Add(wdContentControlRichText, objRange)
   objcc.Title = "Non Bounding"
   ' Set visualization to invisible.
   objcc.Appearance = wdContentControlHidden
   
   ' Create a new paragraph.
   objRange.InsertParagraphAfter
   Set objRange = ActiveDocument.Paragraphs(3).Range
   ' Create a rich text content control around the third paragraph.
   Set objcc = ActiveDocument.ContentControls.Add(wdContentControlRichText, objRange)
   objcc.Title = "Tags Only with Pink color"
   ' Set visualization to Start/End tags with pink color.
   objcc.Appearance = wdContentControlTags
   objcc.Color = wdColorPink
End Sub
```

### <a name="xml-mapping"></a>XML 映射
<a name="WordCC_XMLMappingOM"> </a>

Word 2013 对象模型不进行任何添加以适应格式文本映射到文档数据存储中的 XML 节点。 而是使用现有的对象模型将格式文本内容控件映射到文档数据存储区中的 XML 节点。 此外，对新包括格式文本内容控件支持专门针对 XML 映射的一部分的基础 Open XML 文件格式 WordprocessingML 架构未不进行任何更改。
  
#### <a name="code-sample"></a>代码示例

以下代码示例说明如何以编程方式将格式文本内容控件映射到 XML 节点。
  
```vb
Sub testRichBinding()
   Dim objRange As Range
   Dim objcc As ContentControl
   Dim objCustomPart As CustomXMLPart
   Dim blnMap As Boolean
   
   ' Add a custom XML part to the data store.
   Set objCustomPart = ActiveDocument.CustomXMLParts.Add
   ' Load XML fragment into the custom XML part.
   objCustomPart.LoadXML ("<x>Rich Text Databinding</x>")
   ' Get the first paragraph as a range object.
   Set objRange = ActiveDocument.Paragraphs(1).Range
   ' Create a rich text content control around the first paragraph.
   Set objcc = ActiveDocument.ContentControls.Add(wdContentControlRichText, objRange)
   ' Bind the XML node to the rich text content control.
   blnMap = objcc.XMLMapping.SetMapping("/x")
   ' Return whether mapping worked.
   MsgBox objcc.XMLMapping.IsMapped
End Sub
```

### <a name="repeating-section-content-controls-represented-in-the-object-model"></a>在对象模型中表示的重复节内容控件
<a name="WordCC_RepeatingSection"> </a>

通过使用 **ContentControl** 对象和新 **RepeatingSectionItem** 和 **RepeatingSectionItemColl** 对象的以下添加项，重复节内容控件在对象模型中可用。表 4 列出了 **ContentControl** 对象中针对重复节内容控件的最重要新成员。 
  
**表 4. ContentControl 对象成员**

|**成员**|**说明**|
|:-----|:-----|
|**AllowInsertDeleteSection** 为 **Boolean** <br/> |获取或设置是否用户可以添加或删除节内容控件中使用用户界面。 如果不是类型重复节内容控件调用此属性，则调用将失败并显示以下错误消息:"此属性仅可与重复节内容控件。"  <br/> |
|**RepeatingSectionItemTitle** 为 **String** <br/> |获取或设置的重复节项目上下文菜单中使用的名称。 如果不是类型重复节内容控件调用此属性，则调用将失败并:"此属性仅可与重复节内容控件。"  <br/> |
|**InsertRepeatingSectionItemBefore** 为 **ContentControl** <br/> |添加在当前项之前的重复节项并返回新的重复节项。 如果不是重复部分项目的类型的内容控件调用此方法，则调用将失败并:"此属性仅可与重复节项内容控件。"  <br/> |
|**InsertRepeatingSectionItemAfter** 为 **ContentControl** <br/> |当前项之后添加重复部分项目并返回新的重复节项。 如果不是重复部分项目的类型的内容控件调用此方法，则调用将失败并:"此属性仅可与重复节项内容控件。"  <br/> |
   
表 5 列出了 **RepeatingSectionItem** 对象的最重要成员。 
  
**表 5. RepeatingSectionItem 对象成员**

|**成员**|**说明**|
|:-----|:-----|
|**Range** 为 **Range** <br/> |返回指定重复节项，但不包括开始和结束标记的区域。  <br/> |
|**删除** <br/> |删除指定的重复节项。  <br/> |
|**InsertItemAfter** 为 **RepeatingSectionItem** <br/> |在指定项后面添加一个重复节项，并返回新项。  <br/> |
|**InsertItemBefore** 为 **RepeatingSectionItem** <br/> |在指定项前面添加一个重复节项，并返回新项。  <br/> |
   
表 6 列出了 **RepeatingSectionItemColl** 对象最重要的成员。 
  
**表 6. RepeatingSectionItemColl 对象成员**

|**成员**|**说明**|
|:-----|:-----|
|**Item** 为 **RepeatingSectionItem** <br/> |返回一个单独的重复节项。  <br/> |
   
表 7 显示重复节内容控件 **WdContentControlType** 枚举的新成员。 
  
**表 7. WdContentControlType 枚举添加项**

|**常量**|**说明**|
|:-----|:-----|
|**wdContentControlRepeatingSection** <br/> |表示包含重复节中单个项的内容控件  <br/> |
   
### <a name="code-sample"></a>代码示例
<a name="WordCC_RepeatingSection"> </a>

以下代码示例说明如何以编程方式使用重复节内容控件。
  
```vb
Sub testRepeatingSectionControl()
   Dim objRange As Range
   Dim objTable As Table
   Dim objCustomPart As CustomXMLPart
   Dim objCC As ContentControl
   Dim objCustomNode As CustomXMLNode
   
   Set objCustomPart = ActiveDocument.CustomXMLParts.Add
   objCustomPart.LoadXML ("<books>" & _
       "<book><title>Everyday Italian</title>" & _
       "<author>Giada De Laurentiis</author></book>" & _
       "<book><title>Harry Potter</title>" & _
       "<author>J K. Rowling</author></book>" & _
       "<book><title>Learning XML</title>" & _
       "<author>Erik T. Ray</author></book></books>")
   
   Set objRange = ActiveDocument.Paragraphs(1).Range
   Set objTable = ActiveDocument.Tables.Add(objRange, 2, 2)
   With objTable.Borders
       .InsideLineStyle = wdLineStyleSingle
       .OutsideLineStyle = wdLineStyleDouble
   End With
   Set objRange = objTable.Cell(1, 1).Range
   Set objCustomNode = objCustomPart.SelectSingleNode("/books[1]/book[1]/title[1]")
   Set objCC = ActiveDocument.ContentControls.Add(wdContentControlText, objRange)
   objCC.XMLMapping.SetMappingByNode objCustomNode
   Set objRange = objTable.Cell(1, 2).Range
   Set objCustomNode = objCustomPart.SelectSingleNode("/books[1]/book[1]/author[1]")
   Set objCC = ActiveDocument.ContentControls.Add(wdContentControlText, objRange)
   objCC.XMLMapping.SetMappingByNode objCustomNode
   Set objRange = objTable.Rows(1).Range
   Set objCC = ActiveDocument.ContentControls.Add(wdContentControlRepeatingSection, objRange)
   objCC.XMLMapping.SetMapping ("/books[1]/book")
End Sub
```

### <a name="open-xml-file-format-changes-for-repeating-section-content-controls"></a>Open XML 文件格式因重复节内容控件而异
<a name="WordCC_RepeatingSection"> </a>

重复节内容控件的文件格式表示法通常使用相同的元素名称，值等作为现有的 XML 标记;但是， \<sdt\>元素表示外部重复部分容器中存在的 Word 2013 命名空间，以确保与早期版本的 Word 的兼容性。
  
使用现有的 WordprocessingML 表示形式将重复节内容控件（即包围每个单独项）中的单个重复项保存为格式文本内容控件。表 8 列出了 WordprocessingML 架构中针对重复节内容控件的新元素。
  
**表 8. WordprocessingML 架构中针对重复节内容控件的新元素**

|**元素**|**说明**|
|:-----|:-----|
|\<w15:repeatingSection\>  <br/> |指定一个重复节内容控件。此元素与所有其他控件类型相互排斥，且没有子元素或属性。  <br/> |
|\<w15:repeatingSectionItem\>  <br/> |指定一个重复节项内容控件。此元素与所有其他控件类型相互排斥，且没有子元素或属性。  <br/> |
|\<w15:doNotAllowInsertDeleteSection\>  <br/> |指定用户不能添加或删除使用 Word 2013 中的用户界面的各节。  <br/> |
|\<w15:sectionTitle\>  <br/> |指定重复节项（当选定此控件时，在上下文菜单中使用此重复节项）的名称。  <br/> |
   

  

