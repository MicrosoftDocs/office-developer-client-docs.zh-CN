---
title: 应用程序接口 (OneNote)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 87926f7d-e1dc-41d5-8805-6ba91fc7b154
description: 应用程序接口包括帮助检索、操作和更新 OneNote 信息和内容的方法。这些方法分为四大类：
ms.openlocfilehash: b34cb5e4812842cc3660e24ad2a94268563a4964
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391477"
---
# <a name="application-interface-onenote"></a>应用程序接口 (OneNote)

**应用程序**接口包括帮助检索、操作和更新 OneNote 信息和内容的方法。这些方法分为四大类： 
  
- **笔记本结构** &ndash; 用于处理笔记本结构的方法，包括用于发现、打开、修改、关闭和删除笔记本、节组与节的方法。 
    
- **页面内容** &ndash; 用于处理页面和页面内容的方法，包括用于发现、修改、保存和删除页面内容的方法。 页面内容包括二进制对象（如墨迹和图像）和文本对象（如边框）。 
    
- **导航** &ndash; 用于查找、链接到和导航到页面与对象的方法。 
    
- **功能** &ndash; 在 OneNote 中执行特定操作或设置参数的所有其他方法。 
    
此外，**应用程序**接口包含许多*属性*和*事件*。 
  
## <a name="notebook-structure-methods"></a>笔记本结构方法
<a name="ON14DevRef_Application_NotebookStructure"> </a>

通过本节中介绍的方法，可以发现、打开、修改、关闭和删除 OneNote 笔记本、节组和节。
  
### <a name="gethierarchy-method"></a>GetHierarchy 方法

|||
|:-----|:-----|
|**说明** <br/> |获取笔记本节点层次结构，从您指定的节点开始（所有笔记本或单个笔记本、节组或节），并向下扩展到指定级别的所有后代。  <br/> |
|**语法** <br/> | `HRESULT GetHierarchy(`<br/>`[in]BSTR bstrStartNodeID,`<br/>`[in]HierarchyScope hsScope,`<br/>`[out]BSTR * pbstrHierarchyXmlOut,`<br/>`[in,defaultvalue(xs2013)]XMLSchema xsSchema);` <br/> |
|**参数** <br/> | _bstrStartNodeID_ &ndash; 你需要其后代的节点（笔记本、节组或节）。 如果传递 null 字符串 ("")，则该方法将获取根节点下的所有节点（即所有笔记本、节组和节）。 如果指定笔记本、节组或节节点，则该方法仅获取该节点的后代。  <br/><br/>_hsScope_ &ndash; 你需要的最低后代节点级别。 例如，如果指定页面，则该方法将获取该页面级别下的所有节点。 如果您指定节，该方法将仅获取笔记本下的节节点。 有关详细信息，请参阅[枚举](enumerations-onenote-developer-reference.md#odc_HierarchyScope)主题中的 **HierarchyScope** 枚举。  <br/><br/>_pbstrHierarchyXmlOut_ &ndash;（输出参数）指向你希望 OneNote 在其中写入 XML 输出的字符串的指针。  <br/><br/>_xsSchema_ &ndash;（可选）你希望作为输出的 OneNote XML 结构的版本，其类型为 **XMLSchema**。 您可以指定您需要 XML 架构版本 2013、2010、2007 还是当前版本。  <br/><br/>**注意**：我们建议指定 OneNote 版本（例如 **xs2013**），而不是使用 **xsCurrent** 或将其留空，因为这样会使你的加载项使用 OneNote 的未来版本。           |
   
默认情况下，GetHierarchy 方法返回 OneNote 2013 XML 格式的字符串，或者您可以使用可选的  _xsSchema_ 参数设置首选 XML 架构版本。 
  
根据您传递的参数， **GetHierarchy** 方法可能返回各种列表（例如，所有笔记本、所有笔记本中的所有节、指定节中的所有页面或指定笔记本中的所有页面）。对于每个节点，返回的 XML 字符串会提供相关属性（例如，节或页面标题、ID 和最后修改时间）。 
  
并非开始节点和范围的所有组合均有效。例如，如果您指定节起始节点和笔记本范围， **GetHierarchy** 将返回一个无效结果，因为笔记本在节点层次结构中高于节。 
  
以下 C# 示例说明了如何使用 **GetHierarchy** 方法获取向下到页面级别的整个 OneNote 层次结构，包括所有笔记本。它将输出字符串复制到剪贴板，您可从中将字符串粘贴到文本编辑器以进行检查。 
  
```cs
static void GetEntireHierarchy()
    {
        String strXML;
        OneNote.Application onApplication = new OneNote.Application();
        onApplication.GetHierarchy(null, 
            OneNote.HierarchyScope.hsPages, out strXML);
        Clipboard.SetText(strXML);
        MessageBox.Show("The XML has been copied to the clipboard");
    }

```

### <a name="updatehierarchy-method"></a>UpdateHierarchy 方法

|||
|:-----|:-----|
|**说明**|修改或更新笔记本的层次结构。例如，您可以向笔记本添加节或节组、添加新笔记本、在笔记本内移动节，更改节名称、向节添加页面或更改节内页面的顺序。|
|**语法**| `HRESULT UpdateHierarchy(`<br/>`[in]BSTR bstrChangesXmlIn,`<br/>`[in,defaultvalue(xsCurrent)] XMLSchema xsSchema);`|
|**参数**| _bstrChangesXmlIn_ &ndash; 包含 OneNote XML 代码的字符串，用于指定要进行的层次结构更改。 例如，如果要插入新节，则可以在 XML 字符串中添加**节**元素，以指示要添加新节的位置。 或者，如果要更改现有节的名称，则可以保留相同的节 ID，并在 XML 代码中更改其**名称**属性。<br/><br/>_xsSchema_ &ndash;（可选）字符串 _bstrChangesXmln_ 的 OneNote 架构版本。 此可选值用于指定 _bstrChangesXmlIn_ 字符串所在的 OneNote XML 架构的版本。 如果未指定此值，则 OneNote 将假定 XML 在架构版本 _xsCurrent_ 中。 <br/><br/>**注意**：我们建议指定 OneNote 版本（例如 **xs2013**），而不是使用 **xsCurrent** 或将其留空，因为这样会使你的加载项使用 OneNote 的未来版本。           |
   
如果仅传递  _bstrChangesXmlIn_ 参数的部分 OneNote XML 字符串，OneNote 将尝试推断您需要的更改。例如，如果您提供了一个仅包含一个节的 **Notebook** 元素，OneNote 将在任何现有节后面添加节。但是，如果您指定的操作有歧义，结果则很难确定。例如，如果某个现有笔记本包含四个节，且您传递的 XML 字符串包括笔记本和仅第四和第一个节（按此顺序），OneNote 可能会将第二和第三个节放在第四个节之前或第一个节之后。 
  
无法使用 **UpdateHierarchy** 方法删除笔记本的一部分，即传递仅包含现有层次结构一部分的 XML 字符串不会删除未包含在字符串中的节。要删除层次结构的一部分，请使用 **DeleteHierarchy** 方法。 
  
以下 C# 代码显示了通过更改现有节的名称，使用 **UpdateHierarchy** 方法更改 OneNote 层次结构的一种方式。它从 C 盘根目录一个名为 ChangeSectionName.xml 的示例文件中读取 XML 代码，将其加载到 XML 文档，然后将该文档的 XML 结构传递给方法。 
  
```cs
static void UpdateExistingHierarchy()
    {
        OneNote.Application onApplication = new OneNote.Application();
        
        // Get the XML from the file.
        XmlTextReader reader = new XmlTextReader("C:\\ChangeSectionName.xml");
        reader.WhitespaceHandling = WhitespaceHandling.None;
        XmlDocument xmlDocIn = new XmlDocument();
        xmlDocIn.Load(reader);
        
        // Update the hierarchy.
        onApplication.UpdateHierarchy(xmlDocIn.OuterXml,
        OneNote.XMLSchema.xs2007);   
    }

```

以下 XML 代码摘自之前的 C# 代码传递到方法的 ChangeSectionName.xml 文件。当 XML 传递到 **UpdateHierarchy** 方法时，它会更改现有层次结构中某个节的名称（通过将 **name** 属性的值更改为"My Renamed Section"）。然后它删除所有节，除了更改了名称的节以外。此外，代码将从目标 **Section** 元素中删除不必要的属性，包括 **lastModifiedTime**、 **isCurrentlyViewed** 和 **color** 属性，仅将 **name**、 **ID** 和 **path** 属性保持不变。 
  
```XML
<?xml version="1.0" ?> 
    <one:Notebooks xmlns:one="https://schemas.microsoft.com/office/onenote/12/2004/onenote"> 
        <one:Notebook name="My Notebook" nickname="My Notebook" ID="{0B8E7305-AC2C-4BCB-8651-1CDA55AAE14C}{1}{B0}"> 
            <one:Section name="My Renamed Section" ID="{5F4E2908-44BA-4C02-91FE-49FC665E9A33}{1}{B0}" path="C:\My Section.one" /> 
        </one:Notebook> 
    </one:Notebooks>
```

以上 XML 代码是使用 **GetHierarchy** 方法的示例中所示的代码获取的，我们如下所述对其进行了修改，以将范围限制到节。 
  
```cs
static void GetAllSections()
    {
        String strXML;
        OneNote.Application onApplication = new OneNote.Application();
        onApplication.GetHierarchy(System.String.Empty, 
            OneNote.HierarchyScope.hsSections, out strXML);
        Clipboard.SetText(strXML.ToString());
        MessageBox.Show("The XML has been copied to the Clipboard");
    }

```

以下 C# 示例显示了一个完整的控制台应用程序，该应用程序可搜索名为" `Sample_Section`"的节，提示用户为节输入一个新名称，然后使用 **UpdateHierarchy** 方法将节名称更改为用户键入的名称。在运行代码之前，将"  `Sample_Section`"更改为 OneNote 层次结构中存在的节的名称。
  
```cs
    static void Main(string[] args)
    {
        
        // OneNote 2013 Schema namespace.
        string strNamespace = "https://schemas.microsoft.com/office/onenote/2013/onenote";
        string outputXML;
        Application onApplication = new Application();
        onApplication.GetHierarchy(null, HierarchyScope.hsSections, out outputXML);
        // Load a new XmlDocument.
        XmlDocument xmlDoc = new XmlDocument();
        xmlDoc.LoadXml(outputXML);
        XmlNamespaceManager nsmgr = new XmlNamespaceManager(xmlDoc.NameTable);
            nsmgr.AddNamespace("one", strNamespace);
        // Search for the section named "Sample_Section".
        XmlNode xmlNode = xmlDoc.SelectSingleNode("//one:Section[@name='Sample_Section']", nsmgr);
        // Prompt for a new section title.
        System.Console.Write("Please enter a new title for the section: ");
        string input = System.Console.ReadLine();
        xmlNode.Attributes["name"].Value = input; 
        // Update the section with the new title.
        onApp.UpdateHierarchy(xmlNode.OuterXml);
        System.Console.Write("Done!\n");
    }

```

### <a name="openhierarchy-method"></a>OpenHierarchy 方法

|||
|:-----|:-----|
|**说明** <br/> |打开您指定的节组或节。  <br/> |
|**语法** <br/> | `HRESULT OpenHierarchy(`<br/>`[in]BSTR bstrPath,`<br/>`[in]BSTR bstrRelativeToObjectID,`<br/>`[out]BSTR * pbstrObjectID,`<br/>`[in,defaultvalue(cftNone)]CreateFileType cftIfNotExist);` <br/> |
|**参数** <br/> | _bstrPath_ &ndash; 你想打开的路径。 对于笔记本或笔记本中的节组， _bstrPath_ 可能是文件夹路径或 .one 节文件的路径。 如果指定 .one 节文件的路径，则必须在文件路径字符串中包含 .one 扩展名。  <br/><br/>_bstrRelativeToObjectID_ &ndash; 你希望新对象在其下打开的父对象（笔记本或节组）的 OneNote ID。 如果 _bstrPath_ 参数是绝对路径，则可以为 _bstrRelativeToObjectID_ 传递空字符串 ("")。 或者，您也可以传递应包含想要创建的对象（节或节组）的笔记本或节组的对象 ID，然后指定您希望在该父对象下创建的对象的文件名（例如 section1.one）。  <br/><br/>_pbstrObjectID_ &ndash;（输出参数）OneNote 为 **OpenHierarchy** 方法打开的笔记本、节组或节返回的对象 ID。 此参数是指向你希望方法将 ID 写入其中的字符串的指针。  <br/><br/>_cftlfNotExist_ &ndash;（可选）[CreateFileType](enumerations-onenote-developer-reference.md#odc_CreateFileType) 枚举的枚举值。 如果为  _cftIfNotExist_ 传递一个值， **OpenHierarchy** 方法将在指定路径创建节组或节文件，前提是仅当文件尚不存在。  <br/> |
   
如果指定打开的笔记本中没有的节组， **OpenHierarchy** 方法会将该节组作为笔记本打开。如果您指定的节不在打开的笔记本中， **OpenHierarchy** 方法将打开"最近打开的节"节组中的节。如果您指定的节组或节已在打开的笔记本中，则不会发生任何结果，因为节组或节也已打开。不管在什么情况下， **OpenHierarchy** 都会返回您指定的节组、笔记本或节的对象 ID，以便在其他操作中使用。 
  
您还可以使用 **OpenHierarchy** 方法创建新节，而不是通过导入 XML 来创建。 
  
以下代码显示了如何使用 **OpenHierarchy** 方法在"工作"笔记本中打开"会议"节并获取该节的 ID。如果该节尚不存在，OneNote 将在您指定的位置进行创建。 
  
```cs
static void OpenSection()
    {
        String strID;
        OneNote.Application onApplication = new OneNote.Application();
        onApplication.OpenHierarchy("C:\\Documents and Settings\\user\\My Documents\\OneNote Notebooks\\Work\\Meetings.one", 
        System.String.Empty, out strID, OneNote.CreateFileType.cftSection);
    }

```

### <a name="deletehierarchy-method"></a>DeleteHierarchy 方法

|||
|:-----|:-----|
|**说明** <br/> |从 OneNote 笔记本层次结构中删除任何层次结构对象（节组、节或页面）。  <br/> |
|**语法** <br/> | `HRESULT DeleteHierarchy(`<br/>`[in]BSTR bstrObjectID,`<br/>`[in,defaultvalue(0)]DATE dateExpectedLastModified,`<br/>`[in,defaultvalue(false)]VARIANT_BOOL deletePermanently);` <br/> |
|**参数** <br/> | _bstrObjectID_ &ndash; 你想删除的对象的 OneNote ID。 对象可以是节组、节或页面。  <br/><br/>_dateExpectedLastModified_ &ndash;（可选）你认为要删除的对象的上次修改日期和时间。 如果您为此参数传递一个非零值，OneNote 将继续更新，前提是仅当您传递的值与对象上次修改的实际日期和时间匹配。 为此参数传递一个值有助于防止意外覆盖自上次对象修改以来用户所做的编辑。  <br/><br/>_deletePermanently_ &ndash;（可选）设置为 **true** 可永久删除内容，设置为 **false** 可将内容移到相应笔记本的 OneNote 回收站中（默认设置）。 如果笔记本是 OneNote 2007 格式，则不存在回收站，因此会永久删除内容。  <br/> |
   
### <a name="createnewpage-method"></a>CreateNewPage 方法

|||
|:-----|:-----|
|**说明** <br/> |向您指定的节添加新页面。新页面添加为节的最后一页。  <br/> |
|**语法** <br/> | `HRESULT CreateNewPage(`<br/>`[in]BSTR bstrSectionID,`<br/>`[out]BSTR * pbstrPageID);`<br/>`[in,defaultvalue(npsDefault)]NewPageStyle npsNewPageStyle);` <br/> |
|**参数** <br/> | _bstrSectionID_ &ndash; 包含你希望在其中创建新页面的节的 OneNote ID 的字符串。  <br/><br/>_pbstrPageID_ &ndash;（输出参数）指向该方法在其中写入新创建页面的 OneNote ID 的字符串的指针。  <br/><br/>_npsNewPageStyle_ &ndash; **NewPageStyle** 枚举中的值，用于指定要创建的页面的样式。  <br/> |
   
为了方便，OneNote API 包含 **CreateNewPage** 方法。您可以实现相同的结果，同时对新页面在层次结构中的放置进行更好的控制，方法是调用 **UpdateHierarchy** 方法。 **UpdateHierarchy** 方法还允许您在创建新页面的同时创建子页面。 
  
### <a name="closenotebook-method"></a>CloseNotebook 方法

|||
|:-----|:-----|
|**说明** <br/> |关闭指定的笔记本。  <br/> |
|**语法** <br/> | `HRESULT CloseNotebook(`<br/>`[in]BSTR bstrNotebookID,`<br/>`[in,defaultvalue(false)]VARIANT_BOOL force);` <br/> |
|**参数** <br/> | _bstrNotebookID_ &ndash; 你想关闭的笔记本的 OneNote ID。  <br/><br/>_force_ &ndash;（可选）设置为 **true** 可关闭笔记本，即使笔记本中包含 OneNote 在关闭之前无法同步的更改；否则设置为 **false**（默认设置）。  <br/> |
   
您可以使用 **CloseNotebook** 方法关闭您指定的笔记本。当调用此方法时，会将任何脱机文件与当前的笔记本内容同步，然后根据需要关闭指定的笔记本。该方法返回后，该笔记本将不会再显示在 OneNote 用户界面 (UI) 上打开的笔记本列表中。 
  
### <a name="gethierarchyparent-method"></a>GetHierarchyParent 方法

|||
|:-----|:-----|
|**说明** <br/> |获取某个 OneNote 对象的父对象的 OneNote ID。  <br/> |
|**语法** <br/> | `HRESULT GetHierarchyParent (`<br/>`[in]BSTR bstrObjectID,`<br/>`[out]BSTR * pbstrParentID);` <br/> |
|**参数** <br/> | _bstrObjectID_ &ndash; 包含你希望在其中查找父对象的对象的 OneNote ID 的字符串。  <br/><br/>_pbstrParentID_ &ndash;（输出参数）指向该方法在其中写入父对象的 OneNote ID 的字符串的指针。  <br/> |
   
如果 OneNote 对象没有父对象（例如，当用户想要获取笔记本的父对象时），将抛出一个异常。
  
### <a name="getspeciallocation-method"></a>GetSpecialLocation 方法

|||
|:-----|:-----|
|**说明** <br/> |查找 OneNote 在其中存储某些特殊项目（例如备份、未归档笔记和默认笔记本）的位置的路径。  <br/> |
|**语法** <br/> | `HRESULT GetSpecialLocation(`<br/>`[in]SpecialLocation slToGet,`<br/>`[out]BSTR * pbstrSpecialLocationPath);` <br/> |
|**参数** <br/> | _slToGet_ &ndash; [SpecialLocation](enumerations-onenote-developer-reference.md#odc_SpecialLocation) 枚举值之一，用于指定要获取的特殊文件夹位置。  <br/><br/>_pbstrSpecialLocationPath_ &ndash;（输出参数）指向你希望 OneNote 在其中写入特殊文件夹路径的字符串的指针。  <br/> |
   
您可以使用此方法确定未归档笔记文件夹在磁盘上的位置。这是 OneNote 用于存储将项目拖到 OneNote 中时的笔记，以及直接来自其他应用程序的笔记（例如当您在 Microsoft Outlook 或 Microsoft Internet Explorer 中单击“发送到 OneNote”**** 时产生的笔记）的文件夹。 
  
## <a name="page-content-methods"></a>页面内容方法
<a name="ON14DevRef_Application_PageContent"> </a>

此部分中所述的方法使您可以发现、更新和删除 OneNote 笔记本中页面上的内容，也可发布 OneNote 内容。
  
### <a name="getpagecontent-method"></a>GetPageContent 方法

|||
|:-----|:-----|
|**说明**|获取指定页面的所有内容（OneNote XML 格式）。|
|**语法**| `HRESULT GetPageContent(`<br/>`[in]BSTR bstrPageID,`<br/>`[out]BSTR * pbstrPageXmlOut,`<br/>`[in,defaultvalue(piBasic)]PageInfo pageInfoToExport,`<br/>`[in,defaultvalue(xsCurrent)]XMLSchema xsSchema);`|
|**参数**| _bstrPageId_ &ndash; 你想获取其内容的页面的 OneNote ID。<br/><br/>_pbstrPageXmlOut_ &ndash;（输出参数）指向你希望 OneNote 在其中写入 XML 输出的字符串的指针。<br/><br/>_pageInfoToExport_ &ndash;（可选）指定 **GetPageContent** 方法是否返回嵌入在 XML 代码和 base-64 编码中的二进制内容。 例如，二进制内容可以包括图像和墨迹数据。 _pageInfoToExport_ 参数还指定是否在 **GetPageContent** 方法返回的 XML 代码中标记选择。 它从 [PageInfo](enumerations-onenote-developer-reference.md#odc_PageInfo) 枚举中获取枚举值。<br/><br/>_xsSchema_ &ndash;（可选）你希望作为输出的 OneNote XML 结构的版本，其类型为 **XMLSchema**。 您可以指定您需要 XML 架构版本 2013、2010、2007 还是当前版本。 <br/><br/>**注意**：我们建议指定 OneNote 版本（例如 **xs2013**），而不是使用 **xsCurrent** 或将其留空，因为这样会使你的加载项使用 OneNote 的未来版本。           |
   
默认情况下，为了避免返回的 XML 字符串过长，OneNote 不会在 XML 代码中嵌入二进制内容。出于相同的原因，它不会使用选择属性标记当前选择。二进制对象的标记中包括 OneNote ID。要获取二进制对象，您可以调用 **GetBinaryPageContent** 方法并向其传递从 **GetPageContent** 方法获取的 OneNote ID。如果您并非立即需要二进制数据，可使用 **GetPageContent** 方法。 
  
### <a name="updatepagecontent-method"></a>UpdatePageContent 方法

|||
|:-----|:-----|
|**说明**|更新或修改页面上的内容。|
|**语法**| `HRESULT UpdatePageContent(`<br/>`[in]BSTR bstrPageChangesXmlIn,`<br/>`[in,defaultvalue(0)]DATE dateExpectedLastModified,`<br/>`[in,defaultvalue(xsCurrent)]XMLSchema xsSchema,`<br/>`[in,defaultvalue(false)]VARIANT_BOOL force);`|
|**参数**| _bstrPageChangesXmlIn_ &ndash; 包含 OneNote XML 代码的字符串，其中包括你想对页面所做的更改。<br/><br/>_dateExpectedLastModified_ &ndash;（可选）你认为要更新的页面的上次修改日期和时间。 如果你为此参数传递一个非零值，OneNote 将继续更新，前提是仅当你传递的值与页面上次修改的实际日期和时间匹配。 为此参数传递一个值有助于防止意外覆盖自上次页面修改以来用户所做的编辑。<br/><br/>_xsSchema_ &ndash;（可选）你希望作为输出的 OneNote XML 结构的版本，其类型为 **XMLSchema**。 你可以指定需要 XML 架构版本 2013、2010、2007 还是当前版本。 <br/><br/>**注意**：我们建议指定 OneNote 版本（例如 **xs2013**），而不是使用 **xsCurrent** 或将其留空，因为这样会使你的加载项使用 OneNote 的未来版本。<br/><br/>_force_（可选）设置为 **true** 可更新页面内容，即使页面上有来自 OneNote 未来版本的未知数据；否则，设置为 **false**（默认设置）。 |
   
您可以使用此方法以多种方式修改页面。例如，您可以使用 **UpdatePageContent** 方法向页面添加轮廓、更改轮廓的内容、添加图像、添加墨迹、移动内容或修改轮廓中的文本。 
  
更具体地说，您可以使用 **GetPageContent** 方法导入现有页面，对页面的 XML 代码进行一些更改，然后使用 **UpdatePageContent** 方法再次导入整个页面。或者，您可以使用此方法在现有页面底部添加新页面对象，例如图像。 
  
在您传递到 **UpdatePageContent** 方法的 XML 代码中，您唯一必须包含的对象是已经更改的页面级别对象（例如轮廓、页面上的图像或页面上的墨迹）。此方法不会修改或删除未在  _bstrPageChangesXmlIn_ 参数中指定的页面级别对象。该方法会完全替换 ID 与所传递对象匹配的页面级别对象。因此，您必须在代码中完整指定所有页面级别对象，包括现有内容以及您想对其所做的更改。 
  
例如，如果您的页面包含轮廓和背景页面图像，您可以替换轮廓并将图像保留不变，方法是在 XML 代码中完全指定轮廓、使用现有轮廓的 ID 且不在代码中包含图像。因为您在代码中修改的轮廓完全替换了现有轮廓，您必须包含轮廓的完整内容。
  
此外， **UpdatePageContent** 方法仅修改在  _bstrPageChangesXmlIn_ 参数中指定的元素属性。例如，如果您指定了 **PageSettings** 元素的部分但并非全部属性，您未指定的属性将保留不变。 
  
以下示例说明如何使用 **UpdatePageContent** 方法更改页面的标题并向页面添加示例文本。在运行此代码之前，将代码中显示的页面 ID 替换为有效的页面 ID，以便代码可在您的计算机上正常运行。您可以使用 **GetHierarchy** 方法并检查输出，以获取页面的页面 ID。 
  
```cs
static void UpdatePageContent()
    {
        OneNote.Application onApplication = new OneNote.Application();
        String strImportXML;
        strImportXML = "<?xml version=\"1.0\"?>" +
            "<one:Page xmlns:one=\"https://schemas.microsoft.com/office/onenote/12/2004/onenote\" 
            ID=\"{3428B7BB-EF39-4B9C-A167-3FAE20630C37}{1}{B0}\">" +
            "    <one:PageSettings RTL=\"false\" color=\"automatic\">" +
            "        <one:PageSize>" +
            "            <one:Automatic/>" +
            "        </one:PageSize>" +
            "        <one:RuleLines visible=\"false\"/>" +
            "    </one:PageSettings>" +
            "    <one:Title style=\"font-family:Calibri;
                 font-size:17.0pt\" lang=\"en-US\">" +
            "        <one:OE alignment=\"left\">" +
            "            <one:T>" +
            "                <![CDATA[My Sample Page]]>" +
            "            </one:T>" +
            "        </one:OE>" +
            "    </one:Title>" +
            "    <one:Outline >" +
            "        <one:Position x=\"120\" y=\"160\"/>" +
            "        <one:Size width=\"120\" height=\"15\"/>" +
            "        <one:OEChildren>" +
            "            <one:OE alignment=\"left\">" +
            "                <one:T>" +
            "                    <![CDATA[Sample Text]]>" +
            "                </one:T>" +
            "            </one:OE>" +
            "        </one:OEChildren>" +
            "    </one:Outline>" +
            "</one:Page>";
        // Update the page content.
        onApplication.UpdatePageContent(strImportXML, System.DateTime.MinValue);
    }

```

### <a name="getbinarypagecontent-method"></a>GetBinaryPageContent 方法

|||
|:-----|:-----|
|**说明** <br/> |在 OneNote 页面上返回二进制对象（例如墨迹或图像）作为 base-64 编码的字符串。  <br/> |
|**语法** <br/> | `HRESULT GetBinaryPageContent(`<br/>`[in]BSTR bstrPageID,`<br/>`[in]BSTR bstrCallbackID,`<br/>`[out]BSTR * pbstrBinaryObjectB64Out);` <br/> |
|**参数** <br/> | _bstrPageID_ &ndash; 包含要获取的二进制对象的页面的 OneNote ID。  <br/><br/>_bstrCallBackID_ &ndash; 你获取的二进制对象的 OneNote ID。 此 ID 称为 **callbackID**，位于 **GetPageContent** 方法返回的页面的 OneNote XML 代码中。  <br/><br/>_pbstrBinaryObectB64Out_ &ndash;（输出参数）指向 OneNote 在其中写入二进制对象作为 base-64 编码字符串的字符串的指针。  <br/> |
   
### <a name="deletepagecontent-method"></a>DeletePageContent 方法

|||
|:-----|:-----|
|**说明** <br/> |从页面中删除对象 &ndash; 例如，**边框**、**墨迹**或**图像**对象。  <br/> |
|**语法** <br/> | `HRESULT DeletePageContent(`<br/>`[in]BSTR bstrPageID,`<br/>`[in]BSTR bstrObjectID,`<br/>`[in,defaultvalue(0)]DATE dateExpectedLastModified,`<br/>`[in,defaultvalue(#)]VARIANT_BOOL force);` <br/> |
|**参数** <br/> | _bstrPageID_ &ndash; 包含要删除的对象的页面的 OneNote ID。  <br/><br/>_bstrObjectID_ &ndash; 你想删除的对象的 OneNote ID。  <br/><br/>_dateExpectedLastModified_ &ndash;（可选）你认为包含要删除的内容的页面的上次修改日期和时间。 如果您为此参数传递一个非零值，OneNote 将继续删除，前提是仅当您传递的值与页面上次修改的实际日期和时间匹配。 为此参数传递一个值有助于防止意外覆盖自上次页面修改以来用户所做的编辑。  <br/><br/>_force_ &ndash;（可选）设置为 **true** 可更新页面内容，即使页面上有来自 OneNote 未来版本的未知数据；否则，设置为 **false**（默认设置）。  <br/> |
   
### <a name="publish-method"></a>Publish 方法

|||
|:-----|:-----|
|**说明** <br/> |将您指定的页面导出到 OneNote 支持的任何格式的文件。  <br/> |
|**语法** <br/> | `HRESULT Publish(`<br/>`[in]BSTR bstrHierarchyID,`<br/>`[in]BSTR bstrTargetFilePath,`<br/>`[in,defaultvalue(pfOneNote)]PublishFormat pfPublishFormat,`<br/>`[in,defaultvalue(0)]BSTR bstrCLSIDofExporter);` <br/> |
|**参数** <br/> | _bstrHierarchyID_ &ndash; 你想导出的层次结构的 OneNote ID。  <br/><br/>_bstrTargetFilePath_ &ndash; 你想保存生成的输出文件的位置的绝对路径。 你指定的文件必须是该位置尚不存在的文件。  <br/><br/>_pfPublishFormat_ &ndash; [PublishFormat](enumerations-onenote-developer-reference.md#odc_PublishFormat) 枚举值之一，用于指定你希望发布页面所用的格式（例如 MTHML、PDF 等）。  <br/><br/>_bstrCLSIDofExporter_ &ndash; 可以导出 Microsoft Windows 增强型图元文件 (.emf) 的注册 COM 应用程序的类 ID (CLSID)。 COM 应用程序必须实现 **IMsoDocExporter** 接口。 包含此参数是为了允许第三方开发人员写入自己的代码以使用自定义格式发布 OneNote 内容。 有关 **IMsoDocExporter** 界面的详细信息，请参阅 [扩展 Office 2007 固定格式导出功能](https://msdn.microsoft.com/library/office/aa338206%28v=office.12%29.aspx)。  <br/> |
   
当前 OneNote 支持以下文件格式：
  
- MHTML 文件 (.mht)
- Adobe Acrobat PDF 文件 (.pdf)
- XML Paper Specification (XPS) 文件 (.xps)
- OneNote 2013、2010 或 2007 文件 (.one)
- OneNote Package 文件 (.onepkg)
- Microsoft Word 文档（.doc 或 .docx）
- Microsoft Windows 增强型图元文件 (.emf)
- HTML 文件 (.html)
    
此方法产生的结果与你通过单击 UI 中的“发布”**** 并指定格式获取的结果完全相同。 
  
## <a name="navigation-methods"></a>Navigation 方法
<a name="ON14DevRef_Application_Navigation"> </a>

此部分中所述的方法使您可以查找、导航到并链接到 OneNote 笔记本、节组、节、页面和页面对象。
  
### <a name="navigateto-method"></a>NavigateTo 方法

|||
|:-----|:-----|
|**说明** <br/> |导航到指定对象（例如节、页面和页面中的 **Outline** 元素）。  <br/> |
|**语法** <br/> | `HRESULT NavigateTo(`<br/>`[in]BSTR bstrHierarchyObjectID,`<br/>`[in,defaultvalue(#)]BSTR bstrObjectID,`<br/>`[in,defaultvalue(0)]VARIANT_BOOL fNewWindow);` <br/> |
|**参数** <br/> | _bstrHierarchyObjectID_ &ndash; 你希望在 OneNote 层次结构中导航到的对象的 OneNote ID。  <br/><br/>_bstrObjectID_ &ndash; 你希望在 OneNote 页面上导航到的对象的 OneNote ID。  <br/><br/>_fNewWindow_ &ndash;（可选）设置为 **true** 可在一个新的 OneNote 窗口中打开指定对象。 设置为 **false** 不会打开一个新的 OneNote 窗口（如果已打开一个窗口）。  <br/> |
   
### <a name="navigatetourl-method"></a>NavigateToUrl 方法

|||
|:-----|:-----|
|**说明** <br/> |如果已传递 OneNote 链接 (onenote://)，OneNote 窗口便会在 OneNote 中的相应位置打开。如果链接是 OneNote 外部的（如 https:// 或 file://），便会看到安全对话框。解除后，OneNote 便会尝试打开链接，此时返回 **HResult.hrObjectDoesNotExist** 错误。<br/> |
|**语法** <br/> | `HRESULT NavigateTo(`<br/>`[in]BSTR bstrUrl,`<br/>`[in,defaultvalue(0)]VARIANT_BOOL fNewWindow);` <br/> |
|**参数** <br/> | _bstrUrl_ &ndash; 指示导航到何处的字符串。 这可以是 OneNote 链接，也可以是任何其他 URL，例如 Web 链接或网络位置。  <br/><br/>_fNewWindow_ &ndash;（可选）设置为 **true** 可在一个新的 OneNote 窗口中打开指定 URL。 设置为 **false** 不会打开一个新的 OneNote 窗口（如果已打开一个窗口）。  <br/> |
   
### <a name="gethyperlinktoobject-method"></a>GetHyperLinkToObject 方法

|||
|:-----|:-----|
|**说明** <br/> |获取指定笔记本、节组、节、页面或页面对象的 OneNote 超链接。  <br/> |
|**语法** <br/> | `HRESULT GetHyperlinkToObject(`<br/>`[in] BSTR bstrHierarchyID,`<br/>`[in] BSTR bstrPageContentObjectID,`<br/>`[out] BSTR * pbstrHyperlinkOut);` <br/> |
|**参数** <br/> | _bstrHierarchyID_ &ndash; 你需要其超链接的笔记本、节组、节或页面的 OneNote ID。  <br/><br/>_bstrPageContentObjectID_ &ndash;（可选）你需要其超链接的页面中对象的 OneNote ID。 例如，对象可以是边框或 **Outline** 元素。 如果您传递空字符串 ("")，返回的链接将指向在  _bstrHierarchyID_ 参数中指定的笔记本、节组、节或页面。 如果您为  _bstrPageContentObjectID_ 参数指定非空字符串，  _bstrHierarchyID_ 参数必须为对包含指定对象的页面的引用。  <br/><br/>_pbstrHyperlinkOut_ &ndash;（输出参数）指向 **GetHyperlinkToObject** 方法将在其中写入输出超链接文本的字符串的指针。  <br/> |
   
当你尝试导航到生成的链接时，OneNote 将在浏览器中打开并显示指定的对象。
  
### <a name="getwebhyperlinktoobject-method"></a>GetWebHyperlinktoObject 方法

|||
|:-----|:-----|
|**说明** <br/> |返回在 OneNote Web 客户端中打开的对象的超链接。  <br/> |
|**语法** <br/> | `HRESULT GetWebHyperlinkToObject (`<br/>`[in] BSTR bstrHierarchyID,`<br/>`[in] BSTR bstrPageContentObjectID,`<br/>`[out] BSTR * pbstrHyperlinkOut);` <br/> |
|**参数** <br/> | _bstrHierarchyID_ &ndash; 你需要其 Web 超链接的笔记本、节组、节或页面的 OneNote ID。  <br/><br/>_bstrPageContentObjectID_ &ndash;（可选）你需要其超链接的页面中对象的 OneNote ID。 例如，对象可以是边框或 **Outline** 元素。 如果您传递空字符串 ("")，返回的链接将指向在  _bstrHierarchyID_ 参数中指定的笔记本、节组、节或页面。 如果您为  _bstrPageContentObjectID_ 参数指定非空字符串，  _bstrHierarchyID_ 参数必须为对包含指定对象的页面的引用。  <br/><br/>_pbstrHyperlinkOut_ &ndash;（输出参数）指向 **GetWebHyperlinkToObject** 方法将在其中写入输出超链接文本的字符串的指针。 如果无法为笔记本创建 Web 超链接，则返回 null 值。  <br/> |
   
### <a name="findpages-method"></a>FindPages 方法

|||
|:-----|:-----|
|**说明**|返回与指定查询词匹配的页面的列表。|
|**语法**| `HRESULT FindPages(`<br/>`[in]BSTR bstrStartNodeID,`<br/>`[in]BSTR bstrSearchBSTR,`<br/>`[out]BSTR * pbstrHierarchyXmlOut,`<br/>`[in,defaultvalue(#)]VARIANT_BOOL fIncludeUnindexedPages,`<br/>`[in,defaultvalue(0)]VARIANT_BOOL fDisplay,`<br/>`[in,defaultvalue(#)]XMLSchema xsSchema);`|
|**参数**| _bstrStartNodeID_ &ndash; 要在其下搜索内容的节点（根、笔记本、节组或节）。 此参数设置搜索的范围。<br/><br/>_bstrSearchString_ &ndash; 搜索字符串。 传递与你在 OneNote UI 的搜索框中键入的字符串完全相同的字符串。 可以使用按位运算符，例如 **AND** 和 **OR**，它们必须全部为大写。<br/><br/>_pbstrHierarchyXmlOut_ &ndash;（输出参数）指向你希望 OneNote 将输出 XML 字符串写入其中的字符串的指针。 生成的 XML 字符串包含从根向下到包含与搜索字符串匹配的任何页面的笔记本层次结构。 例如，**FindPages** 方法不会列出层次结构中没有页面匹配的节。 此外，如果单个节中只有一个页面与字符串匹配，则返回的层次结构包括该节和页面的路径，但不包括笔记本层次结构的任何其他部分。<br/><br/>_fIncludeUnindexedPages_ &ndash;（可选）设置为 **true** 可搜索尚未由 Windows Search 编制索引的页面，否则设置为 **false**。<br/><br/>_fDisplay_ &ndash;（可选）设置为 **true** 还可以在用户的 UI 中运行搜索，就像是用户自己键入的一样。 设置为 **false** 则在不更改 UI 的情况下执行查询（默认设置）。<br/><br/>_xsSchema_ &ndash;（可选）字符串 _pbstrHierarchyXmlOut_ 的 OneNote 架构版本。 此可选值用于指定包含 _pbstrHierarchyXmlOut_ 字符串的 OneNote XML 架构的版本。 如果未指定此值，则 OneNote 将假定 XML 在架构版本 _xsCurrent_ 中。 <br/><br/>**注意**：我们建议指定 OneNote 版本（例如 **xs2013**），而不是使用 **xsCurrent** 或将其留空，因为这样会使你的加载项使用 OneNote 的未来版本。           |
   
 仅当您已在计算机上安装 Microsoft Search 3.0 或 4.0 时， **FindPages** 才能正常运行。Windows Vista 和 Windows 7 包括此组件。但是，如果您运行 Windows 的早期版本，则必须安装 [Windows Search](https://www.microsoft.com/windows/products/winfamily/desktopsearch/getitnow.mspx) 才能使 **FindPages** 正常运行。 
  
### <a name="findmeta-method"></a>FindMeta 方法

|||
|:-----|:-----|
|**说明**|返回包含与指定查询词匹配的元数据的 OneNote 对象列表。|
|**语法**| `HRESULT FindMeta (`<br/>`[in]BSTR bstrStartNodeID,`<br/>`[in]BSTR bstrSearchBSTRName,`<br/>`[out]BSTR * pbstrHierarchyXmlOut,`<br/>`[in,defaultvalue(#)]VARIANT_BOOL fIncludeUnindexedPages,`<br/>`[in,defaultvalue(#)]XMLSchema xsSchema);`|
|**参数**| _bstrStartNodeID_ &ndash; 要在其下搜索内容的节点（根、笔记本、节组或节）。 此参数设置搜索的范围。<br/><br/>_bstrSearchStringName_ &ndash; 搜索字符串。 传入元数据名称的任何部分。 如果传入空字符串或 null 值，则具有元数据的所有对象将与查询匹配。<br/><br/>_pbstrHierarchyXmlOut_ &ndash;（输出参数）指向你希望 OneNote 将输出 XML 字符串写入其中的字符串的指针。 生成的 XML 字符串包含从根向下到包含与搜索字符串匹配的任何页面的笔记本层次结构。 例如，**FindPages** 方法不会列出层次结构中没有页面匹配的节。 此外，如果单个节中只有一个页面与字符串匹配，则返回的层次结构包括该节和页面的路径，但不包括笔记本层次结构的任何其他部分。  <br/><br/>_fIncludeUnindexedPages_ &ndash;（可选）设置为 **true** 可搜索尚未由 Windows Search 编制索引的页面，否则设置为 **false**。<br/><br/>_xsSchema_ &ndash;（可选）字符串 _pbstrHierarchyXmlOut_ 的 OneNote 架构版本。 此可选值用于指定包含 _pbstrHierarchyXmlOut_ 字符串的 OneNote XML 架构的版本。 如果未指定此值，则 OneNote 将假定 XML 在架构版本 _xsCurrent_ 中。 <br/><br/>**注意**：我们建议指定 OneNote 版本（例如 **xs2013**），而不是使用 **xsCurrent** 或将其留空，因为这样会使你的加载项使用 OneNote 的未来版本。           |
   
仅当您已在计算机上安装 Microsoft Windows Search 3.0 或 4.0 时， **FindMeta** 才能正常运行。Windows Vista 和 Windows 7 包括此组件。但是，如果您运行 Windows 的早期版本，则必须安装 [Windows Search](https://www.microsoft.com/windows/products/winfamily/desktopsearch/getitnow.mspx) 才能使 **FindMeta** 正常运行。 
  
## <a name="functional-methods"></a>功能性方法
<a name="ON14DevRef_Application_Functional"> </a>

本节中介绍的方法使你可以在 OneNote 应用程序中执行某些操作或设置参数。
  
### <a name="mergefiles-method"></a>MergeFiles 方法

|||
|:-----|:-----|
|**说明** <br/> |允许用户将同一个文件的更改合并为一个。要使文件被视为同一个，它们必须使用相同的 OneNote ID。  <br/> |
|**语法** <br/> | `HRESULT MergeFiles (`<br/>`[in]BSTR bstrBaseFile,`<br/>`[in]BSTR bstrClientFile,`<br/>`[in]BSTR bstrServerFile,`<br/>`[in]BSTR bstrTargetFile);` <br/> |
|**参数** <br/> | _bstrBaseFile_ &ndash; 文件的初始状态的 .one 文件位置的路径字符串。  <br/><br/>_bstrClientFile_ &ndash; 服务器文件更改与基文件合并后，第二组更改要与基文件合并的 .one 文件位置的路径字符串。  <br/><br/>_bstrServerFile_ &ndash; 第一组更改要与基文件合并的 .one 文件位置的路径字符串。  <br/><br/>_bstrTargetFile_ &ndash; 包含合并后更改的文件的 .one 文件位置的路径字符串。  <br/> |
   
**MergeFiles** 方法适用于可能存在多个版本的 OneNote 文件的移动方案。 
  
### <a name="mergesections-method"></a>MergeSections 方法

|||
|:-----|:-----|
|**说明** <br/> |将一个节的内容合并到 OneNote 中的另一个节。  <br/> |
|**语法** <br/> | `HRESULT MergeSections (`<br/>`[in]BSTR bstrSectionSourceId,`<br/>`[in]BSTR bstrSectionDestinationId);` <br/> |
|**参数** <br/> | _bstrSectionSourceId_ &ndash; 要合并的节的 OneNote ID。  <br/><br/>_bstrSectionDestinationId_ &ndash; 要合并到的节的 OneNote ID。 源节将合并到此目标节。  <br/> |
   
此方法执行的操作与你右键单击某个节时可见的**合并到另一个节**功能相同。 
  
### <a name="quickfiling-method"></a>QuickFiling 方法

|||
|:-----|:-----|
|**说明** <br/> |返回 [IQuickFilingDialog](quick-filing-dialog-box-interfaces-onenote.md#odc_IQuickFilingDialog) 对话框的一个实例，可用于在 OneNote 层次结构树中选择位置。  <br/> |
|**语法** <br/> | `HRESULT QuickFiling (`<br/>` );` <br/> |
   
### <a name="synchierarchy-method"></a>SyncHierarchy 方法

|||
|:-----|:-----|
|**说明** <br/> |强制 OneNote 将指定对象与磁盘上的源文件中同步。  <br/> |
|**语法** <br/> | `HRESULT SyncHierarchy (`<br/>`[in]BSTR bstrHierarchyID);` <br/> |
|**参数** <br/> | _bstrHierarchyID_ &ndash; 要同步的对象的 OneNote ID。  <br/> |
   
### <a name="setfilinglocation-method"></a>SetFilingLocation 方法

|||
|:-----|:-----|
|**说明** <br/> |允许用户指定应在 OneNote 中的什么位置以及如何归档特定类型的内容。  <br/> |
|**语法** <br/> | `HRESULT SetFilingLocation (`<br/>`[in]FilingLocation flToSet,`<br/>`[in]FilingLocationType fltToSet,`<br/>`[in]BSTR bstrFilingSectionID);`           <br/> |
|**参数** <br/> | _flToSet_ &ndash; 要设置的归档位置的对象类型。  <br/><br/>_fltToSet_ &ndash; 类型要归档到的位置。  <br/><br/>_bstrFilingSectionID_ &ndash; 你希望在其中设置位置的节或页面的 OneNote ID。 如果不适用，则用户可以传入 null 或空字符串。  <br/> |
   
可以归档的内容类型包括 Outlook 项目和 Internet Explorer 中的 Web 笔记，这些笔记在各个应用程序中通过“发送到 OneNote”**** 命令导入到 OneNote。打印到 OneNote 的项目的归档位置也可以使用此方法进行设置。 
  
## <a name="properties"></a>属性
<a name="ON14DevRef_Application_Properties"> </a>

此部分介绍了 **Application** 界面的属性。 
  
|**属性**|**说明**|
|:-----|:-----|
|**Windows** <br/> |允许用户访问打开的 OneNote 窗口。此属性允许用户通过一系列 OneNote 窗口进行枚举并修改特定的窗口属性。有关详细信息，请参阅 [Windows 界面](window-interfaces-onenote.md)。  <br/> |
|**COMAddIns** <br/> |返回 OneNote 的 **COMAddIns** 集合。该集合包含对 OneNote 可用的所有 COM 加载项。 **COMAddins** 集合的 **Count** 属性返回可用 COM 加载项的数目。有关详细信息，请参阅 [COMAddIns](https://msdn.microsoft.com/library/office/ff865489.aspx) 对象。  <br/> |
|**LanguageSettings** <br/> |使您可以访问一些 API 以更改 OneNote 的公共语言设置。  <br/> |
   
## <a name="events"></a>活动
<a name="ON14DevRef_Application_Events"> </a>

此部分介绍了 Application 界面的事件。
  
> [!CAUTION]
> 当前无法在托管代码中添加事件。 
  
### <a name="onnavigate-event"></a>OnNavigate 事件

|||
|:-----|:-----|
|**说明** <br/> |允许用户指定在从当前 OneNote 位置离开以导航 OneNote UI 时要调用的函数。  <br/> |
|**语法** <br/> | `Event OnNavigate (`<br/>` );` <br/> |
   
### <a name="onhierarchychange-method"></a>OnHierarchyChange 方法

|||
|:-----|:-----|
|**说明** <br/> |允许用户指定在 OneNote 层次结构变更（例如，添加或删除页面，或移动各个节）时要调用的函数。层次结构变更分批进行，因此如果同时或几乎同时发生了多个变更，OneNote 引发事件一次。  <br/> |
|**语法** <br/> | `Event OnHierarchyChange (`<br/>` BSTR bstrActivePageID);` <br/> |
|**参数** <br/> | _bstrActivePageID_ &ndash; 传递活动页面的 OneNote ID。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [OneNote 开发人员参考](onenote-developer-reference.md)

