---
title: 关于 InfoPath 对 XML 技术的支持
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 074181a2-3a75-824c-049d-549aabff0f9f
description: Microsoft InfoPath 是一种混合式工具，它结合了传统文档编辑体验（例如字处理器或电子邮件应用程序）的优点，以及表单数据包精确的数据捕获功能。 本文描述了 InfoPath 可解决的问题，并介绍了用于解决这些问题的设计原则和 XML 行业标准。
ms.openlocfilehash: 20831635fba8d76b9d6b45f42a5308ab7236db20
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407226"
---
# <a name="about-infopath-support-for-xml-technologies"></a>关于 InfoPath 对 XML 技术的支持

Microsoft InfoPath 是一种混合式工具，它结合了传统文档编辑体验（例如字处理器或电子邮件应用程序）的优点，以及表单数据包精确的数据捕获功能。 本文描述了 InfoPath 可解决的问题，并介绍了用于解决这些问题的设计原则和 XML 行业标准。
  
## <a name="introduction"></a>简介

InfoPath 是一种高级 XML 创作工具，利用该工具，普通的最终用户将能创建符合自定义 XML 架构的 XML 文档。当用户编辑 XML 文档时，XML 架构将控制对文档所做的修改。
  
用户通过一个内容丰富的带格式视图与 XML 文档交互，通过将 XSLT 样式表应用于文档，将会显示该视图。XML 文档中的叶节点或属性值显示为域（例如文本框或复选框），而节点层次结构呈现为域组。
  
利用 InfoPath，可通过显示对于当前选定域或域组有效的编辑操作，实现经过验证的、结构化的 XML 数据编辑。这种结构化的编辑使用户能够通过使用内容丰富的动态视图中显示的域组，在看不到元素和属性的情况下添加和移除有效的 XML 元素和属性。
  
InfoPath 通过提供可随着添加使用 XML 分层数据模型的域组而增大的表单，解决了数据收集领域中的一个问题，这一问题在 XML 出现之前无法得到解决。InfoPath 将字处理器文档的灵活性和表单应用程序精确的验证功能结合到了一起。复杂的 XSLT 转换是此解决方案密不可分的一部分，它提供了易于使用的动态 XML 数据视图。
  
## <a name="limitations-of-traditional-forms-and-documents-for-gathering-data"></a>用于收集数据的传统表单和文档的限制

在收集公司数据时，用户通常需要比静态表单更高的灵活性，而需要比字处理器文档更有条理的编辑和验证。
  
传统的表单是静态的，并且长度受限。它们的重复行数目是固定的，并且在填写表单时无法扩展。传统的表单难于使用，原因是它们没有丰富的编辑功能。通常，用户必须在一个轮次中提供所有信息。
  
另一方面，使用字处理器创建的传统文档允许用户自由地添加和移除内容，但几乎没有提供有关如何输入完整、结构化并且有效的信息的指导；在文档中定义的任何域都只会对数据值和数据类型进行最小限度的验证，或者不会进行验证。域中数据的标记方式不适当，无法实现轻松的引用和自动重用。数据形式松散，而并非结构化；您无法将信息分组，例如将"地址"标签应用于"街道"、"城市"和"省/市/自治区"域组。
  
因此，就需要这样一种灵活而结构化的编辑功能，但是，由于在 XML 出现之前没有这种技术，因此开发人员不得不创建自定义应用程序，而这样需要大量的编码。自定义应用程序成本昂贵，难于修改，并且需要进行自定义编码才能实现验证。自定义应用程序通常需要最终用户培训，并且很难重用其他业务流程生成的数据。
  
## <a name="providing-structured-editing-by-displaying-xml-data-as-field-groups"></a>通过将 XML 数据显示为域组，从而提供结构化的编辑

一个必须要解决的重要技术设计问题是：如何提供一个易于使用的用户界面，用于在不显示元素和属性的情况下添加和移除 XML 元素和属性，但要使 DOM 树依照自定义 XML 架构保持有效。该用户界面需要提供一种自然的方式来编辑 DOM 树，包括插入可选的子树、替换子树选项，以及扩展现有子树。
  
To provide this easy user interface, a DOM subtree is displayed as a field group, or section. A field group is a group of UI controls, such as text boxes and drop-down lists, and serves as an easy user interface that enables the user to visualize and edit hierarchical XML data. A field group can contain other field groups and can be optional or repeating, just as a DOM subtree can contain other subtrees and can be optional or repeating. A subtree is added to the DOM tree when the user rests the mouse pointer over a field group, clicks the drop-down menu that appears on the field group, and then selects **Insert \<field group name\>**.
  
InfoPath provides this structured editing of XML data by using the specified XML schema to constrain and guide editing. The schema controls whether the **Insert** and **Remove** commands appear on the drop-down menu for a field group. The schema is also used for validation. To enable editing of an XML document for which there is no XML schema, InfoPath can generate a schema from the XML document. 
  
## <a name="providing-easy-to-use-views-of-xml-data-by-using-xslt-transformations"></a>通过使用 XSLT 转换提供易于使用的 XML 数据视图

另一个需要解决的技术设计难题是：如何能够采用与 XML 数据结构截然不同的方式来组织 UI 视图的内容。为了采用对用户最有意义并使用户能够轻松阅读和编辑数据的方式来呈现数据，设计器必须能够按与 DOM 数据树中不同的顺序来显示数据、从视图中省略某些数据、将邻近的数据树节点重新组织为单独的视图，以及将不同数据树部分中的数据收集到一个视图中。
  
因此，视图内容的顺序和结构必须独立于 DOM 树节点的顺序和结构。呈现和数据的这种结构上的独立性要求在视图的分组域和 DOM 树的节点之间进行复杂、动态的绑定或映射。
  
为了在视图和数据之间提供这种复杂的映射，InfoPath 广泛地使用了 XSL 转换 (XSLT)。XSLT 是一种功能强大的样式表语言，它支持复杂的 XSLT 转换，以及能够动态、灵活地呈现内容的丰富视图。将为每个视图使用一个 XSLT 文件。在 SGML 和 XML 创作工具中，使用样式表是一种已被广泛接受的常见设计方法，并且 XSLT 是用于这种复杂转换的样式表的 W3C 标准。
  
为了避免在用户每次修改 DOM 中子树的结构时运行整个 XSLT 转换，将使用算法来确定视图的哪个部分必须刷新。然后，将仅应用 XSLT 样式表的相关部分，并刷新受影响的视图部分。
  
## <a name="how-xml-standards-are-used-when-editing-a-form"></a>在编辑表单时如何使用 XML 标准

InfoPath 完全是依据 XML 标准构建的，这些标准包括：
  
- 可扩展标记语言 (XML) 1.0 第二版
    
- XML 中的命名空间
    
- XML Path 语言 (XPath) 1.0
    
- XML 架构 (XSD) 1.0 第一部分：结构，及第二部分：数据类型
    
- 可扩展样式表语言转换 (XSLT) 1.0
    
- 可扩展超文本标记语言 (XHTML) 1.0
    
- 级联样式表 (CSS)
    
- 文档对象模型 (DOM) 1.0
    
- XML 数字签名 (XML DSig)
    
- 简单对象访问协议 (SOAP) 1.1
    
- Web Services 描述语言 (WSDL) 1.1
    
- 通用描述、发现和集成 (UDDI) 1.0
    
例如，InfoPath 使用并生成可在各种业务流程中重用的标准 XML、XSLT 和 XSD 文件。InfoPath 使用 MSXML、SOAP 工具包和 .NET System.XML 命名空间来支持这些标准，并提供对 XML Web 服务的完整集成支持。
  
Figure 1 shows the context-sensitive drop-down menu for a **customer** field group, which enables the user to add another **customer** field group, remove this **customer** field group, insert an **item** row in the table of purchase items in this field group, or insert an optional **actions** field group within this field group. The **Click here** link provides another way to insert the **actions** field group. A shorter drop-down menu appears on each purchase-item row. 
  
1. 在 InfoPath 中，用户基于 InfoPath 表单模板创建新 XML 文档，或打开基于表单模板的现有 XML 文档。XML 文档是一个 XML 数据文件，其中包含对表单模板的引用，并可使用 XML 命名空间。 
    
    表单模板是一组文件，利用这些文件可对符合特定自定义 XML 架构的 XML 文档进行结构化编辑。可以将组成表单模板的文件打包为普通文件夹中的单独文件，或打包为位于压缩文件夹中的文件。不论哪种情况，文件都是标准 XML 文件和可选的支持文件（例如托管代码程序集）。
    
2. 如果使用 XML 签名通过数字方式对 XML 文档进行了签名，则 InfoPath 将在打开 XML 文件之前确认该文件是一致的。
    
3. InfoPath 将创建内存中 XML 文档的 DOM 数据树。
    
4. XSLT 转换将应用于 DOM 树，从而生成以适当方式向用户呈现文档的视图。XML 文档开头的元素可显示在视图的底部，也可以按不同的排列形式显示在另一个视图中。视图由诸如节等 UI 容器组成，其中包含文本和控件，例如文本框、格式文本框、日期选取器和下拉列表。容器也可以包含其他容器。
    
5. XSLT 转换生成 XHTML 作为输出，然后使用 CSS 来控制 XHTML 的呈现。
    
6. 如果 XML 架构允许向数据树的某个节点中添加节点，则映射到该节点的域或域组具有下拉菜单，用户可使用该下拉菜单来添加或移除域组。用户通过添加重复或可选的域组、输入值、选择选项或输入格式文本来编辑文档。如果 XML 架构节点与 XHTML 的架构关联，则 InfoPath 将呈现一个用于创建格式文本的 UI。当用户输入格式文本时，将创建 XHTML 内容作为 DOM 中的子树。
    
7. DOM 树始终保持有效。在用户编辑 XML 文档时，将依据关联的 XML 架构对所做编辑进行验证。将依据 XML 架构来验证尝试对 DOM 结构和叶节点值所做的更改，以确保其数据类型和值有效。如果尝试进行的更改无效，则会打开一个验证对话框，并且更改将不会应用于 DOM 树。如果更改有效，则更新 DOM 树。
    
8. 通过仅将所需的 XSLT 样式表部分应用于 DOM 树，刷新视图的已更改部分。
    
9. 用户可以保存 XML 文档，或通过使用简单的 HTTP 或 SOAP 提交 XML 文档。除非依照 XML 架构文档是有效的，否则将不允许用户提交文档。
    
## <a name="how-xml-standards-are-used-when-designing-a-form"></a>如何在设计表单时使用 XML 标准

您可以通过以下方式设计表单：从现有 XML 架构开始、连接到 XML Web Services 或数据库并获取其 XML 架构，或者依据新表单或 XML 数据文件自动生成架构。下面的过程中描述了这些方案。图 3 显示了用于设计表单模板的基本用户界面。
  
1. Create a new form in the InfoPath Designer by selecting the **XML or Schema** form template, and then select an existing XML schema file as the data source. The XML schema is loaded into the task pane and shown as a tree control. 
    
2. 使用设计布局工具在一个或多个视图中安排 UI 控件的布局，例如行和背景设计。此操作将生成某些 XSLT 元素。XSLT 视图和 XML 架构将自动与表单模板关联。
    
3. 通过使用拖放将 XML 架构元素映射到视图中的 UI 控件。InfoPath 将帮助您基于架构元素的种类为 XML 架构元素选择适当的控件。例如，如果 XML 数据类型为日期，则 InfoPath 建议使用日期选取器控件。InfoPath 可基于 XML 架构中的选择来插入可选域组或重复域组。通过将 XML 架构元素映射到 UI 控件，将生成 XSLT 结构。
    
4. 保存表单模板。您可以将组成表单模板的文件保存为常规文件夹中的单独文件，或保存为压缩文件夹内的文件。不论哪种情况，文件都是标准 XML 文件。表单模板现在即可供用户使用。
    
表单模板包含在 InfoPath 中打开表单时提供结构化编辑所需的所有语义信息。表单模板包括清单文件、定义视图的 XSLT 文件、验证数据所需的信息，以及 XML Web Services 的可选资源标识符。
  
清单（或表单定义文件）是表单模板需要的所有文件的公共中心和入口点。清单包含对表单模板中其他文件的引用，并包含验证数据和提供结构化编辑所需的信息。将针对生成的用户界面自定义 XML 架构验证信息，并将该信息添加到清单文件。例如，如果架构允许在特定子树中插入多个可选元素，则可以设计 UI 以便在用户执行单一 UI 操作时添加多个可选元素。若要为普通用户提供出色的用户体验，这种自定义非常重要。 
  
也可以通过使用现有 XML Web Services 来提供 XML 架构，从而设计表单。为此，请执行以下操作：
  
1. 使用 UDDI 找到相关 Web 服务。
    
2. 选择要使用的 Web 服务。InfoPath 将读取与 Web 服务关联的 WSDL 文件，并确定要使用的 XML 架构。
    
3. 打开 XML 架构以将其加载。
    
4. 安排 UI 控件的布局，并将它们与 XML 架构元素和属性关联。
    
5. 定义如何将 XML 文档提交到使用 SOAP 的 Web 服务。
    
如果要从头开始设计表单并自动生成 XML 架构：
  
1. On the **File** tab, select either the **Blank Form** or **Blank Form (InfoPath Filler)** form template, and then click **Design Form**.
    
2. On the **Home** tab, click the arrow in the lower-right corner of the **Controls** group to display the **Controls** task pane, and then make sure that the **Automatically create the data source** check box is selected. (By default, this check box is selected.) 
    
3. 安排 UI 控件的布局。当您安排这些控件的布局时，InfoPath 将自动创建 XML 架构并将其元素和属性映射到 UI 控件。
    
若要从任何格式标准的 XML 数据文件开始设计表单：
  
1. On the **File** tab, select the **XML or Schema** form template, and then click **Design Form**.
    
2. In the **Data Source Wizard**, select the XML file that you want to use as the data source. An XML schema is automatically created, based on the XML data file.
    
3. 按本节中前面所述的方式安排 UI 控件的布局。
    
## <a name="designed-as-an-ideal-client-for-web-services"></a>设计为 Web 服务的理想客户端

Web 服务正在获得广泛的业界支持。许多后端系统和中间层系统都可配置为使用诸如 SOAP、UDDI 和 WSDL 等 Web 服务标准进行通信。这些启用 Web 服务的系统包括数据库、工作流系统、企业资源计划 (ERP)、客户关系管理 (CRM) 和其他系统。现在，InfoPath 提供了一个理想的 UI 来查看和编辑通过 Web 服务发送的 XML 数据。图 4 显示了集成的 XML Web 服务支持。
  
InfoPath 非常适合于 Web 服务的松散耦合模型，在这种模型中，将以完整 XML 文档的形式在计算机之间发送数据。这种粗粒度的通信模型非常适合于 Web 的异步特性。作为一种 XML 文档高级创作工具，InfoPath 支持文档/文本 SOAP 编码，而不是远程过程调用 (RPC) SOAP 编码。InfoPath 是 Web 服务的理想客户端，因为它能够以本地方式读取 SOAP 消息中指定的 XML 架构，然后基于该架构创建 UI，从而使用户能够轻松地查看和编辑对应 Web 服务生成或收到的 XML 文档。InfoPath 还支持包括修订的 ADO.NET 数据集。
  
## <a name="terminology"></a>术语

|||
|:-----|:-----|
|**域组：** <br/> |一个节、重复节、可选节或重复表。节和重复表是表单上的控件，这些控件包含其他控件并根据需要重复。用户在填写表单时可插入多个节或行。  <br/> |
|**DOM 树：** <br/> |表单的数据源的结构。特别是，为 InfoPath 表单定义和存储数据的域和组的集合。  <br/> |
   
## <a name="conclusion"></a>结论

InfoPath 使用开放 XML 标准向用户提供灵活而结构化的 XML 编辑用于数据收集。为了提供用于可视化和编辑分层 XML 数据的易于使用的用户界面，包含 UI 控件的嵌套域组将映射到 DOM 树。利用 XSLT 转换，可以按与 XML 数据的结构不同的方式组织 UI 视图的内容。
  
InfoPath 提供了比静态表单更高的灵活性，以及比字处理器文档更有条理的编辑和验证。两者结合在一起，就组成一个集传统文档编辑体验的优点和表单数据包精确的数据捕获功能于一身的混合式工具，从而使普通用户能够创建符合自定义 XML 架构的有效 XML 文档。利用对 Web 服务的集成支持，可以轻松地定义一些视图，用于编辑符合 Web 服务架构的 XML 文档。
  

