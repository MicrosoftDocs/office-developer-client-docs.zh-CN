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
# <a name="content-controls-in-word"></a><span data-ttu-id="cc330-104">Word 中的内容控件</span><span class="sxs-lookup"><span data-stu-id="cc330-104">Content controls in Word</span></span>

<span data-ttu-id="cc330-105">了解 Microsoft Word 2013 内容控件如何实现更大范围的结构化的文档方案。</span><span class="sxs-lookup"><span data-stu-id="cc330-105">Learn how Microsoft Word 2013 content controls enable a larger range of structured document scenarios.</span></span>

<span data-ttu-id="cc330-106">本主题提供有关在 Microsoft Word 2013 和启用这些更改的文档方案中的内容控件的更改的信息。</span><span class="sxs-lookup"><span data-stu-id="cc330-106">This topic provides information about changes to content controls in Microsoft Word 2013 and the document scenarios that those changes enable.</span></span>
  
### <a name="structured-documents"></a><span data-ttu-id="cc330-107">结构化文档</span><span class="sxs-lookup"><span data-stu-id="cc330-107">Structured documents</span></span>
<span data-ttu-id="cc330-108"><a name="WordCC_StructuredDocs"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-108"></span></span>

<span data-ttu-id="cc330-109">结构化文档是这样一种文档，控制内容可以在文档的何处显示，文档中可以显示的内容类型以及能否编辑此内容。</span><span class="sxs-lookup"><span data-stu-id="cc330-109">Structured documents are documents that control where content can appear on a document, what kind of content can appear in the document, and whether that content can be edited.</span></span>
  
<span data-ttu-id="cc330-110">下面是在 Microsoft Word 中的结构化内容的常见方案：</span><span class="sxs-lookup"><span data-stu-id="cc330-110">Here are some common scenarios for structured content in Microsoft Word:</span></span>
  
- <span data-ttu-id="cc330-111">法律公司需要创建一些文档，其中包含用户不应更改的法律用语。</span><span class="sxs-lookup"><span data-stu-id="cc330-111">A legal firm needs to create documents that contain legal language that should not be changed by the user.</span></span>
    
- <span data-ttu-id="cc330-112">企业需要创建用户只可以输入标题、作者和日期的计划书封面。</span><span class="sxs-lookup"><span data-stu-id="cc330-112">A business needs to create a proposal cover page where only the title, author, and date are entered by the user.</span></span>
    
- <span data-ttu-id="cc330-113">企业需要创建一些发票，其中客户数据包含在发票预定义区域中。</span><span class="sxs-lookup"><span data-stu-id="cc330-113">A business needs to create invoices where the customer data is included in the invoice at predefined regions.</span></span>
    
### <a name="using-content-controls-to-structure-a-document"></a><span data-ttu-id="cc330-114">使用内容控件来构建文档</span><span class="sxs-lookup"><span data-stu-id="cc330-114">Using content controls to structure a document</span></span>
<span data-ttu-id="cc330-115"><a name="WordCC_StructuredDocs"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-115"></span></span>

<span data-ttu-id="cc330-116">内容控件是充当容器的文档中的特定内容的 Microsoft Word 实体。</span><span class="sxs-lookup"><span data-stu-id="cc330-116">Content controls are Microsoft Word entities that act as containers for specific content in a document.</span></span> <span data-ttu-id="cc330-117">单个内容控件可以包含格式化文本的日期、列表或段落等内容。</span><span class="sxs-lookup"><span data-stu-id="cc330-117">Individual content controls can contain content such as dates, lists, or paragraphs of formatted text.</span></span> <span data-ttu-id="cc330-118">内容控制帮助您创建丰富、 结构化内容块，并设计用于定义完善的块插入文档中，创建结构化的文档的模板。</span><span class="sxs-lookup"><span data-stu-id="cc330-118">Content controls help you to create rich, structured blocks of content and are designed for use in templates that insert well-defined blocks into your documents, creating structured documents.</span></span>
  
<span data-ttu-id="cc330-119">内容控件非常适合创建结构化的文档，因为内容控件可以帮助您修复内容的位置，指定内容类型（例如，日期、图片或文本），限制或启用编辑，以及将语义含义添加到内容中。</span><span class="sxs-lookup"><span data-stu-id="cc330-119">Content controls are ideal for creating structured documents because content controls help you fix the position of content, specify the kind of content (for example, a date, a picture, or text), restrict or enable editing, and add semantic meaning to content.</span></span>
  
### <a name="content-controls-in-word-2010"></a><span data-ttu-id="cc330-120">Word 2010 中的内容控件</span><span class="sxs-lookup"><span data-stu-id="cc330-120">Content controls in Word 2010</span></span>
<span data-ttu-id="cc330-121"><a name="WordCC_StructuredDocs"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-121"></span></span>

<span data-ttu-id="cc330-122">以下内容控件是在 Word 2010 中可用：</span><span class="sxs-lookup"><span data-stu-id="cc330-122">The following content controls are available in Word 2010:</span></span>
  
- <span data-ttu-id="cc330-123">格式文本</span><span class="sxs-lookup"><span data-stu-id="cc330-123">Rich Text</span></span>
    
- <span data-ttu-id="cc330-124">纯文本</span><span class="sxs-lookup"><span data-stu-id="cc330-124">Plain Text</span></span>
    
- <span data-ttu-id="cc330-125">图片</span><span class="sxs-lookup"><span data-stu-id="cc330-125">Picture</span></span>
    
- <span data-ttu-id="cc330-126">构建基块库</span><span class="sxs-lookup"><span data-stu-id="cc330-126">Building Block Gallery</span></span>
    
- <span data-ttu-id="cc330-127">组合框</span><span class="sxs-lookup"><span data-stu-id="cc330-127">Combo Box</span></span>
    
- <span data-ttu-id="cc330-128">下拉列表</span><span class="sxs-lookup"><span data-stu-id="cc330-128">Drop-Down List</span></span>
    
- <span data-ttu-id="cc330-129">日期</span><span class="sxs-lookup"><span data-stu-id="cc330-129">Date</span></span>
    
- <span data-ttu-id="cc330-130">复选框</span><span class="sxs-lookup"><span data-stu-id="cc330-130">Checkbox</span></span>
    
- <span data-ttu-id="cc330-131">组</span><span class="sxs-lookup"><span data-stu-id="cc330-131">Group</span></span>
    
<span data-ttu-id="cc330-132">Word 2010 内容控件启用各种潜在的结构化的文档解决方案，但内容控件在 Word 2013 中启用更大范围的应用场景。</span><span class="sxs-lookup"><span data-stu-id="cc330-132">Word 2010 content controls enable various potential structured document solutions, but in Word 2013 content controls enable a greater range of scenarios.</span></span>
  
## <a name="content-control-improvements-in-word-2013"></a><span data-ttu-id="cc330-133">Word 2013 中的内容控件改进</span><span class="sxs-lookup"><span data-stu-id="cc330-133">Content control improvements in Word 2013</span></span>
<span data-ttu-id="cc330-134"><a name="WordCC_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-134"></span></span>

<span data-ttu-id="cc330-135">内容控件在 Word 2013 中提供了三个重要改进： 改进可视化、 支持的 XML 映射格式文本内容控件和新的内容控件的重复的内容。</span><span class="sxs-lookup"><span data-stu-id="cc330-135">In Word 2013, content controls provide three key improvements: improved visualization, support for XML Mapping for Rich Text content controls, and a new content control for repeating content.</span></span>
  
### <a name="improved-visualization"></a><span data-ttu-id="cc330-136">改进的可视化</span><span class="sxs-lookup"><span data-stu-id="cc330-136">Improved visualization</span></span>

<span data-ttu-id="cc330-137">Word 2013 允许单个内容控件中三种可能的状态之一：</span><span class="sxs-lookup"><span data-stu-id="cc330-137">Word 2013 allows an individual content control to appear in one of three possible states:</span></span>
  
- <span data-ttu-id="cc330-138">边界框</span><span class="sxs-lookup"><span data-stu-id="cc330-138">Bounding box</span></span>
    
- <span data-ttu-id="cc330-139">开始/结束标记</span><span class="sxs-lookup"><span data-stu-id="cc330-139">Start/End tags</span></span>
    
- <span data-ttu-id="cc330-140">无</span><span class="sxs-lookup"><span data-stu-id="cc330-140">None</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc330-141">如果不声明，否则本部分将讨论可视化的内容控件时不在**设计模式中**查看该文档。使用**内容控件属性**对话框中**显示为**下拉列表控件设置内容控件的显示的模式。</span><span class="sxs-lookup"><span data-stu-id="cc330-141">If not stated otherwise, this section discusses the visualization of content controls when the document is not viewed in **Design Mode**.You set the display mode for a content control by using the **Show as** drop-down list control in the **Content Control Properties** dialog box.</span></span> 
  
<span data-ttu-id="cc330-142">**图 1. 内容控件属性对话框**</span><span class="sxs-lookup"><span data-stu-id="cc330-142">**Figure 1. Content Control Properties dialog box**</span></span>

<span data-ttu-id="cc330-143">![内容控件属性对话框](media/DK2_WordCC_Fig01.jpg "内容控件属性对话框")</span><span class="sxs-lookup"><span data-stu-id="cc330-143">![Content control properties dialog box](media/DK2_WordCC_Fig01.jpg "Content control properties dialog box")</span></span>
  
<span data-ttu-id="cc330-144">您还可以通过使用 Word 2013 对象模型 （在下文中[新的 Word 2013 内容控件对象模型成员](#WordCC_NewOM)讨论） 设置内容控件的显示的模式。</span><span class="sxs-lookup"><span data-stu-id="cc330-144">You can also set the display mode for a content control by using the Word 2013 object model (discussed later in [New Word 2013 content control object model members](#WordCC_NewOM)).</span></span>
  
### <a name="bounding-box"></a><span data-ttu-id="cc330-145">边界框</span><span class="sxs-lookup"><span data-stu-id="cc330-145">Bounding box</span></span>
<span data-ttu-id="cc330-146"><a name="WordCC_DefaultRendering"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-146"></span></span>

<span data-ttu-id="cc330-147">Word 2013 中的内容控件的默认呈现是按它们出现在 Word 2007 和 Word 2010; 保留内容控件的外观即边界框。</span><span class="sxs-lookup"><span data-stu-id="cc330-147">The default rendering for content controls in Word 2013 is to preserve the look of content controls as they appear in Word 2007 and Word 2010; that is, as a bounding box.</span></span> <span data-ttu-id="cc330-148">如果内容控件设置为显示**边界框**中，具体取决于以下的用户交互的显示更改为：</span><span class="sxs-lookup"><span data-stu-id="cc330-148">When a content control is set to show as **Bounding Box**, the display changes depending upon the following user interaction:</span></span>
  
- <span data-ttu-id="cc330-149">在内容控件没有焦点时，无可视化效果</span><span class="sxs-lookup"><span data-stu-id="cc330-149">When the content control does not have the focus, no visualization occurs</span></span>
    
- <span data-ttu-id="cc330-150">鼠标悬停在内容控件上时，显示为阴影矩形</span><span class="sxs-lookup"><span data-stu-id="cc330-150">On mouse-over, the content control appears as a shaded rectangle</span></span>
    
<span data-ttu-id="cc330-151">**图 2. 鼠标悬停在内容控件上**</span><span class="sxs-lookup"><span data-stu-id="cc330-151">**Figure 2. Content control on mouse-over**</span></span>

<span data-ttu-id="cc330-152">![通过内容鼠标上的控件](media/DK2_WordCC_Fig02.jpg "通过内容鼠标上的控件")</span><span class="sxs-lookup"><span data-stu-id="cc330-152">![Content control on mouse over](media/DK2_WordCC_Fig02.jpg "Content control on mouse over")</span></span>
  
- <span data-ttu-id="cc330-153">在内容控件有焦点时（在用户选择此内容控件时），该控件显示为“边界框”（如果设置了标题，则围绕着内容和标题显示一行）</span><span class="sxs-lookup"><span data-stu-id="cc330-153">When the content control has the focus (when the user chooses the content control), the control appears as a "bounding box" (with a line around the content and the title showing, if a title has been set)</span></span>
    
<span data-ttu-id="cc330-154">**图 3. 具有焦点的内容控件**</span><span class="sxs-lookup"><span data-stu-id="cc330-154">**Figure 3. Content control with focus**</span></span>

<span data-ttu-id="cc330-155">![内容具有焦点的控件](media/DK2_WordCC_Fig03.jpg "内容具有焦点的控件")</span><span class="sxs-lookup"><span data-stu-id="cc330-155">![Content control with focus](media/DK2_WordCC_Fig03.jpg "Content control with focus")</span></span>
  
### <a name="startend-tags"></a><span data-ttu-id="cc330-156">开始/结束标记</span><span class="sxs-lookup"><span data-stu-id="cc330-156">Start/End tags</span></span>
<span data-ttu-id="cc330-157"><a name="WordCC_StartEndTags"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-157"></span></span>

<span data-ttu-id="cc330-158">当内容控件设置为显示为**开始/结束标记**时，无论用户交互，显示标记，然后标题永远不会显示;但位于通过鼠标按钮，如**下拉列表**按钮。</span><span class="sxs-lookup"><span data-stu-id="cc330-158">When the content control is set to show as **Start/End tag**, the tags are displayed regardless of user interaction, and the title never appears; but buttons, such as the **Drop-Down List** button, appear on mouse over.</span></span> 
  
<span data-ttu-id="cc330-159">**图 4. 设置内容控件显示为开始/结束标记**</span><span class="sxs-lookup"><span data-stu-id="cc330-159">**Figure 4. Content control set to show as start/end tags**</span></span>

<span data-ttu-id="cc330-160">![内容控件设置为显示开始和结束标记](media/DK2_WordCC_Fig04.jpg "内容控件设置为显示开始和结束标记")</span><span class="sxs-lookup"><span data-stu-id="cc330-160">![Content control set to show as start and end tags](media/DK2_WordCC_Fig04.jpg "Content control set to show as start and end tags")</span></span>
  
### <a name="none"></a><span data-ttu-id="cc330-161">无</span><span class="sxs-lookup"><span data-stu-id="cc330-161">None</span></span>
<span data-ttu-id="cc330-162"><a name="WordCC_Invisible"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-162"></span></span>

<span data-ttu-id="cc330-163">当内容控件设置为显示为**无**时，不显示的内容控件。</span><span class="sxs-lookup"><span data-stu-id="cc330-163">When the content control is set to show as **None**, the content control is not displayed.</span></span>
  
### <a name="content-control-colorization"></a><span data-ttu-id="cc330-164">内容控件着色</span><span class="sxs-lookup"><span data-stu-id="cc330-164">Content control colorization</span></span>
<span data-ttu-id="cc330-165"><a name="WordCC_CCColorization"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-165"></span></span>

<span data-ttu-id="cc330-166">除了启用不同种类的内容控件的显示，Word 2013 还有助于您设置单个内容控件的颜色。</span><span class="sxs-lookup"><span data-stu-id="cc330-166">In addition to enabling a different kind of display for a content control, Word 2013 also helps you to set the color for an individual content control.</span></span> <span data-ttu-id="cc330-167">在**内容控件属性**对话框中，使用**颜色**按钮设置内容控件的颜色。</span><span class="sxs-lookup"><span data-stu-id="cc330-167">You set the color of a content control by using the **Color** button in the **Content Control Properties** dialog box.</span></span> 
  
<span data-ttu-id="cc330-168">您还可以通过使用 Word 2013 对象模型 （在下文中[新的 Word 2013 内容控件对象模型成员](#WordCC_NewOM)讨论） 设置内容控件的颜色。</span><span class="sxs-lookup"><span data-stu-id="cc330-168">You can also set the color of a content control by using the Word 2013 object model (discussed later in [New Word 2013 content control object model members](#WordCC_NewOM)).</span></span>
  
<span data-ttu-id="cc330-169">**图 5. 内容控件属性对话框**</span><span class="sxs-lookup"><span data-stu-id="cc330-169">**Figure 5. Content Control Properties dialog box**</span></span>

<span data-ttu-id="cc330-170">![内容控件属性对话框](media/DK2_WordCC_Fig05.jpg "内容控件属性对话框")</span><span class="sxs-lookup"><span data-stu-id="cc330-170">![Content control properties dialog box](media/DK2_WordCC_Fig05.jpg "Content control properties dialog box")</span></span>
  
### <a name="support-for-xml-mapping-for-rich-text-content-controls"></a><span data-ttu-id="cc330-171">支持格式文本内容控件的 XML 映射</span><span class="sxs-lookup"><span data-stu-id="cc330-171">Support for XML mapping for rich text content controls</span></span>
<span data-ttu-id="cc330-172"><a name="WordCC_XMLMapping"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-172"></span></span>

<span data-ttu-id="cc330-173">Word 2013 可帮助您将使用格式文本内容控件和文档构建基块内容控件的内容映射到 XML 数据存储区。</span><span class="sxs-lookup"><span data-stu-id="cc330-173">Word 2013 helps you to map the content of rich text content controls and document building block content controls to the XML data store.</span></span> <span data-ttu-id="cc330-174">若要执行此操作，则设置内容控件的*XML 映射*。</span><span class="sxs-lookup"><span data-stu-id="cc330-174">To do this, you set the  *XML mapping*  for the content control.</span></span> <span data-ttu-id="cc330-175">您可以使用对象模型中的现有**XMLMapping.SetMapping**方法设置此属性。</span><span class="sxs-lookup"><span data-stu-id="cc330-175">You can set this property by using the existing **XMLMapping.SetMapping** method in the object model.</span></span> <span data-ttu-id="cc330-176">自定义 XML 存储中的自定义 XML 部件，如下平面 Open XML 标记转换为字符串 （通过使用标准的 XML 编码），因此，它可以存储为自定义 XML 部件中的文本节点。</span><span class="sxs-lookup"><span data-stu-id="cc330-176">Within the custom XML part, the custom XML is stored as flat Open XML markup converted into a string (by using standard XML encoding), so that it can be stored as a text node in the custom XML part.</span></span> <span data-ttu-id="cc330-177">但是，映射用户都继续拥有可以仅成功映射到叶节点或属性的限制。</span><span class="sxs-lookup"><span data-stu-id="cc330-177">However, the mapping continues to have the limitation that it can only successfully map to leaf nodes or attributes.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cc330-p105">格式文本内容控件不能包含其他格式文本内容控件。如果一个格式文本内容控件位于另一个格式文本内容控件之中（例如，由于文件格式操作、复制和粘贴等），则它处于未链接的状态，直到它不再包含在一个映射的格式文本控件之中。</span><span class="sxs-lookup"><span data-stu-id="cc330-p105">Rich text content controls cannot contain other rich text content controls. If one exists inside of another (for example, because of file format manipulation, copy and paste, and so on), it is unlinked until it is no longer contained inside a mapped rich text control.</span></span> 
  
<span data-ttu-id="cc330-180">有关如何设置 XML 映射的详细信息，请参阅本主题后面的[新的 Word 2013 内容控件对象模型成员](#WordCC_NewOM)一节。</span><span class="sxs-lookup"><span data-stu-id="cc330-180">For more information about how to set up XML mapping, see the section [New Word 2013 content control object model members](#WordCC_NewOM) later in this topic.</span></span> 
  
### <a name="supporting-repeating-content"></a><span data-ttu-id="cc330-181">支持重复内容</span><span class="sxs-lookup"><span data-stu-id="cc330-181">Supporting repeating content</span></span>
<span data-ttu-id="cc330-182"><a name="WordCC_SupportingRepeating"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-182"></span></span>

<span data-ttu-id="cc330-183">除了可视化增强功能和支持的 XML 映射到格式文本内容控件，Word 2013 也添加新的内容控件，使您能够重复内容。</span><span class="sxs-lookup"><span data-stu-id="cc330-183">In addition to visualization enhancements and support for XML mapping to rich text content controls, Word 2013 also adds a new content control that enables you to repeat content.</span></span> <span data-ttu-id="cc330-184">重复节内容控件重复所包含的内容，包括其他内容控件。</span><span class="sxs-lookup"><span data-stu-id="cc330-184">The repeating section content control repeats the content contained within it, including other content controls.</span></span>
  
<span data-ttu-id="cc330-p107">您可以围绕整个段落或表行插入重复的节内容控件。一旦此控件包围一节，您可以在所包含的节的上方或下方插入该节的副本。</span><span class="sxs-lookup"><span data-stu-id="cc330-p107">You insert the repeating section content control around entire paragraphs or table rows. Once the control surrounds a section, you can insert copies of the section above or below the contained section.</span></span>
  
<span data-ttu-id="cc330-187">**图 6. 重复节内容控件上下文菜单**</span><span class="sxs-lookup"><span data-stu-id="cc330-187">**Figure 6. Repeating section content control context menu**</span></span>

<span data-ttu-id="cc330-188">![重复节内容控件上下文](media/DK2_WordCC_Fig06.jpg "重复节内容控件上下文")</span><span class="sxs-lookup"><span data-stu-id="cc330-188">![Repeating section content control context](media/DK2_WordCC_Fig06.jpg "Repeating section content control context")</span></span>
  
<span data-ttu-id="cc330-189">图 6 中所示，可以通过使用一端 （显示为带加号 （![+ 号](media/DK2_WordCC_Fig06A.jpg "加号")） 按钮） 的内容控件的控件或选择上下文菜单中，在命令重复插入部分。</span><span class="sxs-lookup"><span data-stu-id="cc330-189">You can repeat the inserted section by using either the control on the end of the content control (displayed as a button with a plus sign (![Plus sign](media/DK2_WordCC_Fig06A.jpg "Plus sign"))) or by choosing a command on the context menu, as shown in Figure 6.</span></span> <span data-ttu-id="cc330-190">重复的内容将成为一个单独的节，这样就可以分配一个标题，使用**内容控件属性**对话框中的控件。</span><span class="sxs-lookup"><span data-stu-id="cc330-190">The repeated content becomes a separate section of the control that you can assign a title by using the **Content Control Properties** dialog box.</span></span> 
  
<span data-ttu-id="cc330-191">**图 7. 在内容控件属性对话框中指定节标题**</span><span class="sxs-lookup"><span data-stu-id="cc330-191">**Figure 7. Assign a section title in the Content Control Properties dialog box**</span></span>

<span data-ttu-id="cc330-192">![内容控件属性对话框](media/DK2_WordCC_Fig07.jpg "内容控件属性对话框")</span><span class="sxs-lookup"><span data-stu-id="cc330-192">![Content control properties dialog box](media/DK2_WordCC_Fig07.jpg "Content control properties dialog box")</span></span>
  
<span data-ttu-id="cc330-193">一旦已授予部分中一个标题，如果在**内容控件属性**对话框中选择**允许用户添加和删除节**，用户可以通过添加或删除部分名称。</span><span class="sxs-lookup"><span data-stu-id="cc330-193">Once you have given the section a title, if you select **Allow users to add and remove sections** in the **Content Control Properties** dialog box, users can add or delete the section by name.</span></span> 
  
<span data-ttu-id="cc330-194">**图 8. 使用重复节内容控件上下文菜单来删除节**</span><span class="sxs-lookup"><span data-stu-id="cc330-194">**Figure 8. Use the repeating section content control context menu to delete a section**</span></span>

<span data-ttu-id="cc330-195">![重复节内容控件上下文](media/DK2_WordCC_Fig08.jpg "重复节内容控件上下文")</span><span class="sxs-lookup"><span data-stu-id="cc330-195">![Repeating section content control context](media/DK2_WordCC_Fig08.jpg "Repeating section content control context")</span></span>
  
<span data-ttu-id="cc330-p109">当重复节内容控件包围其他内容控件时，封装的内容控件在每个新项中重复；但是任何此类内容控件都将其内容重置为占位符文本。有两个保留了子控件内容的例外情况：</span><span class="sxs-lookup"><span data-stu-id="cc330-p109">When a repeating section content control surrounds other content controls, the enclosed content controls are repeated in each new item; but any such content controls have their contents reset to placeholder text. There are two exceptions where child control contents are preserved:</span></span> 
  
- <span data-ttu-id="cc330-198">当子控件为重复节控件时。</span><span class="sxs-lookup"><span data-stu-id="cc330-198">When a child control is a repeating section control.</span></span>
    
- <span data-ttu-id="cc330-199">当子控件为 XML 映射到的重复节内容控件外部的节点时。</span><span class="sxs-lookup"><span data-stu-id="cc330-199">When a child control is XML-mapped to a node outside the repeating section content control.</span></span>
    
<span data-ttu-id="cc330-200">**图 9. 重复节内容控件在重复前包含子控件**</span><span class="sxs-lookup"><span data-stu-id="cc330-200">**Figure 9. Repeating section content control containing child controls before repeat**</span></span>

<span data-ttu-id="cc330-201">![重复节内容控件之前重复](media/DK2_WordCC_Fig09.jpg "重复节内容控件之前重复")</span><span class="sxs-lookup"><span data-stu-id="cc330-201">![Repeating section content control before repeat](media/DK2_WordCC_Fig09.jpg "Repeating section content control before repeat")</span></span>
  
<span data-ttu-id="cc330-202">**图 10. 重复节内容控件在重复后包含子控件**</span><span class="sxs-lookup"><span data-stu-id="cc330-202">**Figure 10. Repeating section content control containing child controls after repeat**</span></span>

<span data-ttu-id="cc330-203">![重复节内容控件后重复](media/DK2_WordCC_Fig10.jpg "重复节内容控件后重复")</span><span class="sxs-lookup"><span data-stu-id="cc330-203">![Repeating section content control after repeat](media/DK2_WordCC_Fig10.jpg "Repeating section content control after repeat")</span></span>
  
### <a name="repeating-section-content-controls-around-xml-mapped-controls"></a><span data-ttu-id="cc330-204">围绕 XML 映射的控件的重复节内容控件</span><span class="sxs-lookup"><span data-stu-id="cc330-204">Repeating section content controls around XML-mapped controls</span></span>
<span data-ttu-id="cc330-205"><a name="WordCC_RepeatingSectionCCs"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-205"></span></span>

<span data-ttu-id="cc330-206">重复节中包含的 XML 映射，Word 2013 将它们映射，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cc330-206">For XML mappings that are contained in a repeating section, Word 2013 maps them as follows.</span></span>
  
<span data-ttu-id="cc330-207">如果与中的节点集作为其父链的一部分的项不相交映射，绑定是"绝对绑定"，并显示相同的内容中所有重复节项目。</span><span class="sxs-lookup"><span data-stu-id="cc330-207">If the mapping does not intersect with an item in the node set as part of its parent chain, the binding is an "absolute binding" and shows the same content in all repeating section items.</span></span>
  
<span data-ttu-id="cc330-208">如果映射执行相交与项目中的节点集作为其父链的一部分，绑定是一个"相对绑定"，并重新映射，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc330-208">If the mapping does intersect with an item in the node set as part of its parent chain, the binding is a "relative binding", and is remapped as follows:</span></span>
  
- <span data-ttu-id="cc330-209">确定节点的绝对绑定（延展任何查询表达式）─ 这应该在初始映射时发生</span><span class="sxs-lookup"><span data-stu-id="cc330-209">The absolute binding for the node is determined (flattening out any query expressions)─this should happen on initial mapping</span></span>
    
- <span data-ttu-id="cc330-210">删除与节点集交叉的绑定轴</span><span class="sxs-lookup"><span data-stu-id="cc330-210">The axis of the binding that intersects with the node set is removed</span></span>
    
- <span data-ttu-id="cc330-211">相对于 XPath 的重复节内容项评估 XPath 的其余部分</span><span class="sxs-lookup"><span data-stu-id="cc330-211">The remainder of the XPath is evaluated relative to the XPath of the repeating section content item</span></span>
    
<span data-ttu-id="cc330-212">例如，可能发生以下映射：</span><span class="sxs-lookup"><span data-stu-id="cc330-212">For example, the following mappings might occur:</span></span>
  
- <span data-ttu-id="cc330-213">重复节映射到 \root\next\path</span><span class="sxs-lookup"><span data-stu-id="cc330-213">The repeating section is mapped to \root\next\path</span></span>
    
- <span data-ttu-id="cc330-214">示例项中的控件映射到 \root\next\path[2]\baz</span><span class="sxs-lookup"><span data-stu-id="cc330-214">The control in the sample item is mapped to \root\next\path[2]\baz</span></span>
    
- <span data-ttu-id="cc330-215">Word 将 \root\next\path[2] 匹配到节点集中的某个项</span><span class="sxs-lookup"><span data-stu-id="cc330-215">Word matches \root\next\path[2] to an item in the node set</span></span>
    
<span data-ttu-id="cc330-216">因此，将此绑定作为 .\baz 进行评估，其中的基础是重复内容项的节点。</span><span class="sxs-lookup"><span data-stu-id="cc330-216">The binding is therefore evaluated as .\baz, where the base is the node of the repeating content item.</span></span>
  
<span data-ttu-id="cc330-217">使用重复内容控件的以下建议可以帮助您防止数据丢失，并避免产生挫折感。</span><span class="sxs-lookup"><span data-stu-id="cc330-217">The following suggestions for working with repeating content controls can help you prevent data loss and avoid frustration.</span></span>
  
### <a name="working-with-repeating-section-content-controls-that-are-mapped-to-xml-data"></a><span data-ttu-id="cc330-218">使用映射到 XML 数据的重复节内容控件</span><span class="sxs-lookup"><span data-stu-id="cc330-218">Working with repeating section content controls that are mapped to XML data</span></span>
<span data-ttu-id="cc330-219"><a name="WordCC_RepeatingSectionCCs"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-219"></span></span>

<span data-ttu-id="cc330-220">如果插入重复节内容控件映射到 XML 数据，每次用户重新打开文档时，Word 将重新创建基于数据存储中的信息的重复节项。</span><span class="sxs-lookup"><span data-stu-id="cc330-220">If you insert a repeating section content control that is mapped to XML data, every time your user reopens the document, Word recreates the repeating section items, based on the information in the data store.</span></span> <span data-ttu-id="cc330-221">即使保存文档时，用户在重复节项目文档中还不是映射到数据存储区进行任何更改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="cc330-221">Even if you save the document, any changes that the user makes in the repeating section items in the document that aren't also mapped into the data store are lost.</span></span>
  
<span data-ttu-id="cc330-222">若要有助于防止这种情况发生，请锁定重复节内容控件，并允许用户只在映射到 XML 的未锁定子内容控件中进行编辑。</span><span class="sxs-lookup"><span data-stu-id="cc330-222">To help prevent this from happening, lock the repeating section content control and allow the user to edit only in unlocked child content controls that are mapped to the XML as well.</span></span>
  
### <a name="binding-a-repeating-section-content-control-to-a-table"></a><span data-ttu-id="cc330-223">将重复节内容控件绑定到表</span><span class="sxs-lookup"><span data-stu-id="cc330-223">Binding a repeating section content control to a table</span></span>
<span data-ttu-id="cc330-224"><a name="WordCC_RepeatingSectionCCs"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-224"></span></span>

<span data-ttu-id="cc330-225">如果您想要重复节内容控件绑定到表，插入表*然后*插入重复节内容控件，并不是其他方法周围。</span><span class="sxs-lookup"><span data-stu-id="cc330-225">If you want to bind a repeating section content control to a table, insert the table and  *then*  the insert repeating section content control, and not the other way around.</span></span> <span data-ttu-id="cc330-226">（否则，您将无法选择仅的表）。</span><span class="sxs-lookup"><span data-stu-id="cc330-226">(Otherwise, you won't be able to select only the table).</span></span> 
  
### <a name="nesting-repeating-section-content-controls-within-a-table"></a><span data-ttu-id="cc330-227">在表中嵌套重复节内容控件</span><span class="sxs-lookup"><span data-stu-id="cc330-227">Nesting repeating section content controls within a table</span></span>
<span data-ttu-id="cc330-228"><a name="WordCC_RepeatingSectionCCs"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-228"></span></span>

<span data-ttu-id="cc330-229">当添加或删除内部节的一个项时，在表中紧密地嵌套重复节内容控件（例如，当父和子的重复节内容控件的末尾位于同一单元格时）会导致删除外部重复节。</span><span class="sxs-lookup"><span data-stu-id="cc330-229">Nesting repeating section content controls tightly within a table (for example, when the end of the parent and child repeating section content control is in the same cell) causes the outer repeating section to be deleted when the inner section has an item added or removed.</span></span>
  
<span data-ttu-id="cc330-230">如果不希望发生，可以添加一个重复节内容控件的末尾和下一行文本之间的段落标记。</span><span class="sxs-lookup"><span data-stu-id="cc330-230">You can prevent this from happening by adding a paragraph marker between the end of one repeating section content control and the next.</span></span> <span data-ttu-id="cc330-231">若要隐藏段落标记，取消选中功能区的**主页**选项卡上的**显示/隐藏**选项。</span><span class="sxs-lookup"><span data-stu-id="cc330-231">To hide the paragraph marker, deselect the **Show/Hide** option on the **Home** tab of the ribbon.</span></span> 
  
### <a name="open-xml-file-format-schema-additions"></a><span data-ttu-id="cc330-232">Open XML 文件格式架构的添加项</span><span class="sxs-lookup"><span data-stu-id="cc330-232">Open XML File Format schema additions</span></span>
<span data-ttu-id="cc330-233"><a name="WordCC"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-233"></span></span>

<span data-ttu-id="cc330-234">以下元素添加到 WordprocessingML Open XML 文件格式架构中。</span><span class="sxs-lookup"><span data-stu-id="cc330-234">The following elements were added to the WordprocessingML Open XML File Format schema.</span></span>
  
<span data-ttu-id="cc330-235">**表 1. 适用于内容控件的 WordprocessingML Open XML 文件格式架构中的新元素**</span><span class="sxs-lookup"><span data-stu-id="cc330-235">**Table 1. New elements in the WordprocessingML Open XML File Format schema for content controls**</span></span>

|<span data-ttu-id="cc330-236">**元素**</span><span class="sxs-lookup"><span data-stu-id="cc330-236">**Element**</span></span>|<span data-ttu-id="cc330-237">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-237">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-238">\<w:appearance\></span><span class="sxs-lookup"><span data-stu-id="cc330-238">\<w:appearance\></span></span>  <br/> |<span data-ttu-id="cc330-239">\<w:appearance\>是子元素的\<w:sdtPr\>。</span><span class="sxs-lookup"><span data-stu-id="cc330-239">\<w:appearance\> is a child element of \<w:sdtPr\>.</span></span>  <br/> <span data-ttu-id="cc330-240">以下值对 val 属性有效：</span><span class="sxs-lookup"><span data-stu-id="cc330-240">The following values are valid for the val attribute:</span></span>  <br/> <span data-ttu-id="cc330-241">\<w:appearance val = boundingBox</span><span class="sxs-lookup"><span data-stu-id="cc330-241">\<w:appearance val= boundingBox</span></span>|<span data-ttu-id="cc330-242">标记前添加的标记</span><span class="sxs-lookup"><span data-stu-id="cc330-242">tags</span></span>|<span data-ttu-id="cc330-243">隐藏。</span><span class="sxs-lookup"><span data-stu-id="cc330-243">hidden.</span></span>  <br/> <span data-ttu-id="cc330-244">默认值为 boundingBox。</span><span class="sxs-lookup"><span data-stu-id="cc330-244">The default value is boundingBox.</span></span>  <br/> |
|<span data-ttu-id="cc330-245">\<w:color\></span><span class="sxs-lookup"><span data-stu-id="cc330-245">\<w:color\></span></span>  <br/> |<span data-ttu-id="cc330-246">\<w:color\>是子元素的\<w:sdtPr\>。</span><span class="sxs-lookup"><span data-stu-id="cc330-246">\<w:color\> is a child element of \<w:sdtPr\>.</span></span>  <br/> <span data-ttu-id="cc330-p113">此内容模型与现有的 CT_Color 复杂类型相匹配。默认值是 Word 2010 中所使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="cc330-p113">The content model matches the existing CT_Color complex type. The default value is the color used in Word 2010.</span></span>  <br/> |
   
## <a name="new-word-2013-content-control-object-model-members"></a><span data-ttu-id="cc330-249">新的 Word 2013 内容控件对象模型成员</span><span class="sxs-lookup"><span data-stu-id="cc330-249">New Word 2013 content control object model members</span></span>
<span data-ttu-id="cc330-250"><a name="WordCC_NewOM"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-250"></span></span>

<span data-ttu-id="cc330-251">新的增强功能和内容控件在 Word 2013 中的新增功能，已更新 Word 对象模型，以允许的新功能集编程操作。</span><span class="sxs-lookup"><span data-stu-id="cc330-251">With the new enhancements and additions to content controls in Word 2013, the object model for Word has been updated to allow for programmatic manipulation of the new feature set.</span></span> <span data-ttu-id="cc330-252">此外，还进行了更改为字处理文档的基础 Open XML 文件格式。</span><span class="sxs-lookup"><span data-stu-id="cc330-252">In addition, changes have also been made to the underlying Open XML File Format for word processing documents.</span></span>
  
<span data-ttu-id="cc330-253">以下几节提供与每个内容控件增强功能相关的特定对象模型更改的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc330-253">The following sections provide more information about the specific object model changes related to each content control enhancement.</span></span>
  
### <a name="visualization-enhancements"></a><span data-ttu-id="cc330-254">可视化增强功能</span><span class="sxs-lookup"><span data-stu-id="cc330-254">Visualization enhancements</span></span>
<span data-ttu-id="cc330-255"><a name="WordCC_VisEnhancements"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-255"></span></span>

<span data-ttu-id="cc330-256">Word 2013 中的内容控件可视化增强功能包括几个对象模型新增内容。</span><span class="sxs-lookup"><span data-stu-id="cc330-256">Several object model additions are included in Word 2013 for content control visualization enhancements.</span></span> <span data-ttu-id="cc330-257">下表列出可视化的**ContentControl**对象的新成员。</span><span class="sxs-lookup"><span data-stu-id="cc330-257">The following table list new members of the **ContentControl** object for visualization.</span></span> 
  
<span data-ttu-id="cc330-258">**表 2. 新 ContentControl 对象成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-258">**Table 2. New ContentControl object members**</span></span>

|<span data-ttu-id="cc330-259">**成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-259">**Member**</span></span>|<span data-ttu-id="cc330-260">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-260">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-261">.</span><span class="sxs-lookup"><span data-stu-id="cc330-261"></span></span> <span data-ttu-id="cc330-262">作为**WdContentControlAppearance**的**外观**</span><span class="sxs-lookup"><span data-stu-id="cc330-262">**Appearance** as **WdContentControlAppearance**</span></span> <br/> |<span data-ttu-id="cc330-263">获取或设置内容控件的可视化。</span><span class="sxs-lookup"><span data-stu-id="cc330-263">Gets or sets the visualization of the content control.</span></span>  <br/> |
|<span data-ttu-id="cc330-264">.</span><span class="sxs-lookup"><span data-stu-id="cc330-264"></span></span> <span data-ttu-id="cc330-265">**颜色**为**WdColor**</span><span class="sxs-lookup"><span data-stu-id="cc330-265">**Color** as **WdColor**</span></span> <br/> |<span data-ttu-id="cc330-266">获取或设置内容控件的颜色。</span><span class="sxs-lookup"><span data-stu-id="cc330-266">Gets or sets the color of the content control.</span></span>  <br/> |
   
<span data-ttu-id="cc330-267">下表列出了新 **WdContentControlAppearance** 枚举中的常量。</span><span class="sxs-lookup"><span data-stu-id="cc330-267">The following table lists constants in the new **WdContentControlAppearance** enumeration.</span></span> 
  
<span data-ttu-id="cc330-268">**表 3. 新 WdContentControlAppearance 枚举的常量**</span><span class="sxs-lookup"><span data-stu-id="cc330-268">**Table 3. New WdContentControlAppearance enumeration constants**</span></span>

|<span data-ttu-id="cc330-269">**常量**</span><span class="sxs-lookup"><span data-stu-id="cc330-269">**Constant**</span></span>|<span data-ttu-id="cc330-270">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-270">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-271">**wdContentControlBoundingBox**</span><span class="sxs-lookup"><span data-stu-id="cc330-271">**wdContentControlBoundingBox**</span></span> <br/> |<span data-ttu-id="cc330-272">表示显示为阴影矩形/边界框（带可选标题）的内容控件。</span><span class="sxs-lookup"><span data-stu-id="cc330-272">Represents a content control shown as a shaded rectangle/bounding box (with optional title).</span></span>  <br/> |
|<span data-ttu-id="cc330-273">**wdContentControlTags**</span><span class="sxs-lookup"><span data-stu-id="cc330-273">**wdContentControlTags**</span></span> <br/> |<span data-ttu-id="cc330-274">表示显示为开始/结束标记的内容控件。</span><span class="sxs-lookup"><span data-stu-id="cc330-274">Represents a content control shown as start/end markers.</span></span>  <br/> |
|<span data-ttu-id="cc330-275">**wdContentControlHidden**</span><span class="sxs-lookup"><span data-stu-id="cc330-275">**wdContentControlHidden**</span></span> <br/> |<span data-ttu-id="cc330-276">表示未显示的内容控件。</span><span class="sxs-lookup"><span data-stu-id="cc330-276">Represents a content control that is not shown.</span></span>  <br/> |
   
### <a name="code-sample"></a><span data-ttu-id="cc330-277">代码示例</span><span class="sxs-lookup"><span data-stu-id="cc330-277">Code sample</span></span>
<span data-ttu-id="cc330-278"><a name="WordCC_VisEnhancements"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-278"></span></span>

<span data-ttu-id="cc330-279">以下代码示例说明如何创建格式文本内容控件以及如何以编程方式设置可视化。</span><span class="sxs-lookup"><span data-stu-id="cc330-279">The following code sample shows how to create rich text content controls and set visualization programmatically.</span></span>
  
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

### <a name="xml-mapping"></a><span data-ttu-id="cc330-280">XML 映射</span><span class="sxs-lookup"><span data-stu-id="cc330-280">XML mapping</span></span>
<span data-ttu-id="cc330-281"><a name="WordCC_XMLMappingOM"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-281"></span></span>

<span data-ttu-id="cc330-282">Word 2013 对象模型不进行任何添加以适应格式文本映射到文档数据存储中的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="cc330-282">No additions were made to the Word 2013 object model to accommodate rich text mapping to XML nodes in the document data store.</span></span> <span data-ttu-id="cc330-283">而是使用现有的对象模型将格式文本内容控件映射到文档数据存储区中的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="cc330-283">Instead, use the existing object model to map a rich text content control to an XML node in the document data store.</span></span> <span data-ttu-id="cc330-284">此外，对新包括格式文本内容控件支持专门针对 XML 映射的一部分的基础 Open XML 文件格式 WordprocessingML 架构未不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="cc330-284">Additionally, no changes were made to the underlying Open XML File Format WordprocessingML schema as part of the newly included rich text content control support specifically for XML mapping.</span></span>
  
#### <a name="code-sample"></a><span data-ttu-id="cc330-285">代码示例</span><span class="sxs-lookup"><span data-stu-id="cc330-285">Code sample</span></span>

<span data-ttu-id="cc330-286">以下代码示例说明如何以编程方式将格式文本内容控件映射到 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="cc330-286">The following code sample shows how to map a rich text content control to an XML node programmatically.</span></span>
  
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

### <a name="repeating-section-content-controls-represented-in-the-object-model"></a><span data-ttu-id="cc330-287">在对象模型中表示的重复节内容控件</span><span class="sxs-lookup"><span data-stu-id="cc330-287">Repeating section content controls represented in the object model</span></span>
<span data-ttu-id="cc330-288"><a name="WordCC_RepeatingSection"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-288"></span></span>

<span data-ttu-id="cc330-p119">通过使用 **ContentControl** 对象和新 **RepeatingSectionItem** 和 **RepeatingSectionItemColl** 对象的以下添加项，重复节内容控件在对象模型中可用。表 4 列出了 **ContentControl** 对象中针对重复节内容控件的最重要新成员。</span><span class="sxs-lookup"><span data-stu-id="cc330-p119">The repeating section content control is available in the object model by using the following additions to the **ContentControl** object and the new **RepeatingSectionItem** and **RepeatingSectionItemColl** objects. Table 4 lists the most important new members of the **ContentControl** object for repeating section content controls.</span></span> 
  
<span data-ttu-id="cc330-291">**表 4. ContentControl 对象成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-291">**Table 4. ContentControl object members**</span></span>

|<span data-ttu-id="cc330-292">**成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-292">**Member**</span></span>|<span data-ttu-id="cc330-293">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-293">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-294">**AllowInsertDeleteSection** 为 **Boolean**</span><span class="sxs-lookup"><span data-stu-id="cc330-294">**AllowInsertDeleteSection** as **Boolean**</span></span> <br/> |<span data-ttu-id="cc330-295">获取或设置是否用户可以添加或删除节内容控件中使用用户界面。</span><span class="sxs-lookup"><span data-stu-id="cc330-295">Gets or sets whether users can add or remove sections from the content control by using the UI.</span></span> <span data-ttu-id="cc330-296">如果不是类型重复节内容控件调用此属性，则调用将失败并显示以下错误消息:"此属性仅可与重复节内容控件。"</span><span class="sxs-lookup"><span data-stu-id="cc330-296">If this property is called for a content control that is not of type repeating section, the call fails with the following error message: "This property can only be used with repeating section content controls."</span></span>  <br/> |
|<span data-ttu-id="cc330-297">**RepeatingSectionItemTitle** 为 **String**</span><span class="sxs-lookup"><span data-stu-id="cc330-297">**RepeatingSectionItemTitle** as **String**</span></span> <br/> |<span data-ttu-id="cc330-298">获取或设置的重复节项目上下文菜单中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="cc330-298">Gets or sets the name of repeating section items used in the context menu.</span></span> <span data-ttu-id="cc330-299">如果不是类型重复节内容控件调用此属性，则调用将失败并:"此属性仅可与重复节内容控件。"</span><span class="sxs-lookup"><span data-stu-id="cc330-299">If this property is called for a content control that is not of type repeating section, the call fails with: "This property can only be used with repeating section content controls."</span></span>  <br/> |
|<span data-ttu-id="cc330-300">**InsertRepeatingSectionItemBefore** 为 **ContentControl**</span><span class="sxs-lookup"><span data-stu-id="cc330-300">**InsertRepeatingSectionItemBefore** as **ContentControl**</span></span> <br/> |<span data-ttu-id="cc330-301">添加在当前项之前的重复节项并返回新的重复节项。</span><span class="sxs-lookup"><span data-stu-id="cc330-301">Adds a repeating section item before the current item and returns the new repeating section item.</span></span> <span data-ttu-id="cc330-302">如果不是重复部分项目的类型的内容控件调用此方法，则调用将失败并:"此属性仅可与重复节项内容控件。"</span><span class="sxs-lookup"><span data-stu-id="cc330-302">If this method is called for a content control that is not of type repeating section item, the call fails with: "This property can only be used with repeating section item content controls."</span></span>  <br/> |
|<span data-ttu-id="cc330-303">**InsertRepeatingSectionItemAfter** 为 **ContentControl**</span><span class="sxs-lookup"><span data-stu-id="cc330-303">**InsertRepeatingSectionItemAfter** as **ContentControl**</span></span> <br/> |<span data-ttu-id="cc330-304">当前项之后添加重复部分项目并返回新的重复节项。</span><span class="sxs-lookup"><span data-stu-id="cc330-304">Adds a repeating section item after the current item and returns the new repeating section item.</span></span> <span data-ttu-id="cc330-305">如果不是重复部分项目的类型的内容控件调用此方法，则调用将失败并:"此属性仅可与重复节项内容控件。"</span><span class="sxs-lookup"><span data-stu-id="cc330-305">If this method is called for a content control that is not of type repeating section item, the call fails with: "This property can only be used with repeating section item content controls."</span></span>  <br/> |
   
<span data-ttu-id="cc330-306">表 5 列出了 **RepeatingSectionItem** 对象的最重要成员。</span><span class="sxs-lookup"><span data-stu-id="cc330-306">Table 5 lists the most important members of the **RepeatingSectionItem** object.</span></span> 
  
<span data-ttu-id="cc330-307">**表 5. RepeatingSectionItem 对象成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-307">**Table 5. RepeatingSectionItem object members**</span></span>

|<span data-ttu-id="cc330-308">**成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-308">**Member**</span></span>|<span data-ttu-id="cc330-309">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-309">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-310">**Range** 为 **Range**</span><span class="sxs-lookup"><span data-stu-id="cc330-310">**Range** as **Range**</span></span> <br/> |<span data-ttu-id="cc330-311">返回指定重复节项，但不包括开始和结束标记的区域。</span><span class="sxs-lookup"><span data-stu-id="cc330-311">Returns the range of the specified repeating section item, excluding the start and end tags.</span></span>  <br/> |
|<span data-ttu-id="cc330-312">**删除**</span><span class="sxs-lookup"><span data-stu-id="cc330-312">**Delete**</span></span> <br/> |<span data-ttu-id="cc330-313">删除指定的重复节项。</span><span class="sxs-lookup"><span data-stu-id="cc330-313">Deletes the specified repeating section item.</span></span>  <br/> |
|<span data-ttu-id="cc330-314">**InsertItemAfter** 为 **RepeatingSectionItem**</span><span class="sxs-lookup"><span data-stu-id="cc330-314">**InsertItemAfter** as **RepeatingSectionItem**</span></span> <br/> |<span data-ttu-id="cc330-315">在指定项后面添加一个重复节项，并返回新项。</span><span class="sxs-lookup"><span data-stu-id="cc330-315">Adds a repeating section item after the specified item and returns the new item.</span></span>  <br/> |
|<span data-ttu-id="cc330-316">**InsertItemBefore** 为 **RepeatingSectionItem**</span><span class="sxs-lookup"><span data-stu-id="cc330-316">**InsertItemBefore** as **RepeatingSectionItem**</span></span> <br/> |<span data-ttu-id="cc330-317">在指定项前面添加一个重复节项，并返回新项。</span><span class="sxs-lookup"><span data-stu-id="cc330-317">Adds a repeating section item before the specified item and returns the new item.</span></span>  <br/> |
   
<span data-ttu-id="cc330-318">表 6 列出了 **RepeatingSectionItemColl** 对象最重要的成员。</span><span class="sxs-lookup"><span data-stu-id="cc330-318">Table 6 lists the most important members of the **RepeatingSectionItemColl** object.</span></span> 
  
<span data-ttu-id="cc330-319">**表 6. RepeatingSectionItemColl 对象成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-319">**Table 6. RepeatingSectionItemColl object members**</span></span>

|<span data-ttu-id="cc330-320">**成员**</span><span class="sxs-lookup"><span data-stu-id="cc330-320">**Member**</span></span>|<span data-ttu-id="cc330-321">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-321">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-322">**Item** 为 **RepeatingSectionItem**</span><span class="sxs-lookup"><span data-stu-id="cc330-322">**Item** as **RepeatingSectionItem**</span></span> <br/> |<span data-ttu-id="cc330-323">返回一个单独的重复节项。</span><span class="sxs-lookup"><span data-stu-id="cc330-323">Returns an individual repeating section item.</span></span>  <br/> |
   
<span data-ttu-id="cc330-324">表 7 显示重复节内容控件 **WdContentControlType** 枚举的新成员。</span><span class="sxs-lookup"><span data-stu-id="cc330-324">Table 7 shows the new member of the **WdContentControlType** enumeration for repeating section content controls.</span></span> 
  
<span data-ttu-id="cc330-325">**表 7. WdContentControlType 枚举添加项**</span><span class="sxs-lookup"><span data-stu-id="cc330-325">**Table 7. WdContentControlType enumeration addition**</span></span>

|<span data-ttu-id="cc330-326">**常量**</span><span class="sxs-lookup"><span data-stu-id="cc330-326">**Constant**</span></span>|<span data-ttu-id="cc330-327">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-327">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-328">**wdContentControlRepeatingSection**</span><span class="sxs-lookup"><span data-stu-id="cc330-328">**wdContentControlRepeatingSection**</span></span> <br/> |<span data-ttu-id="cc330-329">表示包含重复节中单个项的内容控件</span><span class="sxs-lookup"><span data-stu-id="cc330-329">Represents a content control that contains a single item in a repeating section.</span></span>  <br/> |
   
### <a name="code-sample"></a><span data-ttu-id="cc330-330">代码示例</span><span class="sxs-lookup"><span data-stu-id="cc330-330">Code sample</span></span>
<span data-ttu-id="cc330-331"><a name="WordCC_RepeatingSection"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-331"></span></span>

<span data-ttu-id="cc330-332">以下代码示例说明如何以编程方式使用重复节内容控件。</span><span class="sxs-lookup"><span data-stu-id="cc330-332">The following code sample shows how to use repeating section content controls programmatically.</span></span>
  
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

### <a name="open-xml-file-format-changes-for-repeating-section-content-controls"></a><span data-ttu-id="cc330-333">Open XML 文件格式因重复节内容控件而异</span><span class="sxs-lookup"><span data-stu-id="cc330-333">Open XML File Format changes for repeating section content controls</span></span>
<span data-ttu-id="cc330-334"><a name="WordCC_RepeatingSection"> </a></span><span class="sxs-lookup"><span data-stu-id="cc330-334"></span></span>

<span data-ttu-id="cc330-335">重复节内容控件的文件格式表示法通常使用相同的元素名称，值等作为现有的 XML 标记;但是， \<sdt\>元素表示外部重复部分容器中存在的 Word 2013 命名空间，以确保与早期版本的 Word 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="cc330-335">The file format representation of a repeating section content control generally uses the same element names, values, and so on as the existing XML markup; however, the \<sdt\> element representing the outer repeating section container exists in the Word 2013 namespace, to ensure compatibility with earlier versions of Word.</span></span>
  
<span data-ttu-id="cc330-p124">使用现有的 WordprocessingML 表示形式将重复节内容控件（即包围每个单独项）中的单个重复项保存为格式文本内容控件。表 8 列出了 WordprocessingML 架构中针对重复节内容控件的新元素。</span><span class="sxs-lookup"><span data-stu-id="cc330-p124">The individual repeating items within the repeating section content control (that surround each individual item) are saved as rich text content controls using the existing WordprocessingML representation. Table 8 lists new elements in the WordprocessingML schema for repeating section content controls.</span></span>
  
<span data-ttu-id="cc330-338">**表 8. WordprocessingML 架构中针对重复节内容控件的新元素**</span><span class="sxs-lookup"><span data-stu-id="cc330-338">**Table 8. New elements in the WordprocessingML schema for repeating section content controls**</span></span>

|<span data-ttu-id="cc330-339">**元素**</span><span class="sxs-lookup"><span data-stu-id="cc330-339">**Element**</span></span>|<span data-ttu-id="cc330-340">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc330-340">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc330-341">\<w15:repeatingSection\></span><span class="sxs-lookup"><span data-stu-id="cc330-341">\<w15:repeatingSection\></span></span>  <br/> |<span data-ttu-id="cc330-p125">指定一个重复节内容控件。此元素与所有其他控件类型相互排斥，且没有子元素或属性。</span><span class="sxs-lookup"><span data-stu-id="cc330-p125">Specifies a repeating section content control. This element is mutually exclusive with all other control types and has no child elements or attributes.</span></span>  <br/> |
|<span data-ttu-id="cc330-344">\<w15:repeatingSectionItem\></span><span class="sxs-lookup"><span data-stu-id="cc330-344">\<w15:repeatingSectionItem\></span></span>  <br/> |<span data-ttu-id="cc330-p126">指定一个重复节项内容控件。此元素与所有其他控件类型相互排斥，且没有子元素或属性。</span><span class="sxs-lookup"><span data-stu-id="cc330-p126">Specifies a repeating section item content control. This element is mutually exclusive with all other control types, and has no child elements or attributes.</span></span>  <br/> |
|<span data-ttu-id="cc330-347">\<w15:doNotAllowInsertDeleteSection\></span><span class="sxs-lookup"><span data-stu-id="cc330-347">\<w15:doNotAllowInsertDeleteSection\></span></span>  <br/> |<span data-ttu-id="cc330-348">指定用户不能添加或删除使用 Word 2013 中的用户界面的各节。</span><span class="sxs-lookup"><span data-stu-id="cc330-348">Specifies that the user cannot add or delete sections by using the user interface in Word 2013.</span></span>  <br/> |
|<span data-ttu-id="cc330-349">\<w15:sectionTitle\></span><span class="sxs-lookup"><span data-stu-id="cc330-349">\<w15:sectionTitle\></span></span>  <br/> |<span data-ttu-id="cc330-350">指定重复节项（当选定此控件时，在上下文菜单中使用此重复节项）的名称。</span><span class="sxs-lookup"><span data-stu-id="cc330-350">Specifies the name of repeating section items (and is used in the context menu when the control is chosen).</span></span>  <br/> |
   

  

