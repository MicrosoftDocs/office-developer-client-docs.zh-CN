---
title: 使用 InfoPath 对象模型添加事件处理程序
manager: soliver
ms.date: 01/20/2015
ms.audience: Developer
keywords:
- onafterimport event [infopath 2007],OnAfterChange event [InfoPath 2007],OnBeforeChange event [InfoPath 2007],OnSubmitRequest event [InfoPath 2007],OnVersionUpgrade event [InfoPath 2007],InfoPath 2003-compatible form templates, event handlers,OnLoad event [InfoPath 2007],event handlers [InfoPath 2007], adding using InfoPath 2003 object model,OnValidate event [InfoPath 2007],OnContextChange event [InfoPath 2007],OnSaveRequest event [InfoPath 2007],OnClick event [InfoPath 2007],OnSwitchView event [InfoPath 2007],OnSign event [InfoPath 2007],OnMergeRequest event [InfoPath 2007]
localization_priority: Normal
ms.assetid: 0520df55-2d91-4cc5-be31-82144a2db4f6
description: 与 InfoPath 2003 对象模型兼容的表单模板项目中用于添加事件处理程序函数的菜单命令在本质上与其他类型的表单模板相同。
ms.openlocfilehash: 8533b6bc11dccdad9d0f05de35406ad3cf68eacd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386703"
---
# <a name="add-an-event-handler-using-the-infopath-object-model"></a><span data-ttu-id="374fc-104">使用 InfoPath 对象模型添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-104">Add an event handler using the InfoPath object model</span></span>

<span data-ttu-id="374fc-105">与 InfoPath 2003 对象模型兼容的表单模板项目中用于添加事件处理程序函数的菜单命令在本质上与其他类型的表单模板相同。</span><span class="sxs-lookup"><span data-stu-id="374fc-105">The menu commands for adding event handler functions in a form template project that is compatible with the InfoPath 2003 object model are essentially the same as those for other types of form templates.</span></span> <span data-ttu-id="374fc-106">例如，为了添加“OnLoad”\*\*\*\* 事件处理程序，在 InfoPath 设计器中的表单模板打开的状态下，单击“开发工具”\*\*\*\* 选项卡上的“On Load Event”\*\*\*\* 命令。焦点将自动切换到 Visual Studio 2012 代码编辑器中的“OnLoad”\*\*\*\* 事件处理程序的表单代码。</span><span class="sxs-lookup"><span data-stu-id="374fc-106">For example, in order to add an **OnLoad** event handler, with the form template open in the InfoPath designer, click the **On Load Event** command on the **Developer** tab. The focus automatically switches to the form code for the **OnLoad** event handler in the Visual Studio 2012 code editor.</span></span> 
  
<span data-ttu-id="374fc-107">在与 InfoPath 2003 兼容的托管代码表单模板项目中，包含事件处理程序函数和事件处理程序本身的类都用代码模块中专用于 InfoPath 的属性来标识。</span><span class="sxs-lookup"><span data-stu-id="374fc-107">In managed-code form template projects compatible with InfoPath 2003, the class that contains event handler functions and the event handlers themselves are identified by attributes specific to InfoPath in the code module.</span></span>

## <a name="adding-event-handlers"></a><span data-ttu-id="374fc-108">添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-108">Adding event handlers</span></span>

<span data-ttu-id="374fc-109">以下所有过程假定你已使用 Visual Studio 2012 打开 Microsoft InfoPath 中的表单模板项目。</span><span class="sxs-lookup"><span data-stu-id="374fc-109">All of the following procedures assume that you have a form template project open in Microsoft InfoPath with Visual Studio 2012.</span></span>
  
### <a name="add-an-event-handler-for-the-onclick-event-of-a-command-button"></a><span data-ttu-id="374fc-110">为命令按钮的 OnClick 事件添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-110">Add an event handler for the OnClick event of a command button</span></span>

1. <span data-ttu-id="374fc-111">在“控件”\*\*\*\* 窗格中，单击“按钮”\*\*\*\* 向表单添加按钮。</span><span class="sxs-lookup"><span data-stu-id="374fc-111">In the **Controls** pane, click **Button** to add a button to the form.</span></span> 
    
2. <span data-ttu-id="374fc-112">在“属性”\*\*\*\* 选项卡上，单击“自定义代码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-112">On the **Properties** tab, click **Custom Code**.</span></span>
    
   <span data-ttu-id="374fc-113">焦点将切换到代码编辑器中 [OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) 事件的事件处理程序的存根。</span><span class="sxs-lookup"><span data-stu-id="374fc-113">The focus switches to the stub for the event handler for the [OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) event in the code editor.</span></span> 
    
### <a name="add-an-event-handler-for-the-onbeforechange-onvalidate-or-onafterchange-event-of-a-field-or-group"></a><span data-ttu-id="374fc-114">为域或组的 OnBeforeChange、OnValidate 或 OnAfterChange 事件添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-114">Add an event handler for the OnBeforeChange, OnValidate, or OnAfterChange event of a field or group</span></span>

1. <span data-ttu-id="374fc-115">右键单击绑定到字段或组的数据输入控件，例如“文本框”\*\*\*\* 控件。</span><span class="sxs-lookup"><span data-stu-id="374fc-115">Right-click a data-entry control bound to the field or group, such as a **Text Box** control.</span></span> 
    
2. <span data-ttu-id="374fc-116">指向“编程”\*\*\*\*，然后单击其中一个命令，例如，“On Validate Event”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-116">Point to **Programming**, and then click one of the commands, such as **On Validate Event**.</span></span>
    
   <span data-ttu-id="374fc-117">焦点将切换到代码编辑器中下面某个事件的事件处理程序的存根：[OnBeforeChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnBeforeChange.aspx)、[OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx) 或 [OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx)。</span><span class="sxs-lookup"><span data-stu-id="374fc-117">The focus switches to the stub for the event handler for one of the following events in the code editor: [OnBeforeChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnBeforeChange.aspx), [OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx), or [OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx).</span></span> 
    
### <a name="add-an-event-handler-for-the-onload-onswitchview-oncontextchange-or-onsign-event-of-a-form"></a><span data-ttu-id="374fc-118">添加表单的 OnLoad、OnSwitchView、OnContextChange 或 OnSign 事件的事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-118">Add an event handler for the OnLoad, OnSwitchView, OnContextChange, or OnSign event of a form</span></span>

- <span data-ttu-id="374fc-119">在“工具”\*\*\*\* 菜单上，指向“编程”\*\*\*\*，然后单击要为其编写事件处理程序的表单事件。</span><span class="sxs-lookup"><span data-stu-id="374fc-119">On the **Tools** menu, point to **Programming**, and then click the form event that you want to write an event handler for.</span></span>
    
    <span data-ttu-id="374fc-120">焦点将切换到代码编辑器中下面某个事件的事件处理程序的存根：[OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx)、[OnSwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSwitchView.aspx)、[OnContextChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnContextChange.aspx) 或 [OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSign.aspx)。</span><span class="sxs-lookup"><span data-stu-id="374fc-120">The focus switches to the stub for the event handler for one of the following in the code editor: [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx), [OnSwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSwitchView.aspx), [OnContextChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnContextChange.aspx), or [OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSign.aspx).</span></span> 
    
### <a name="add-an-event-handler-for-the-onsubmitrequest-event-of-a-form"></a><span data-ttu-id="374fc-121">添加表单的 OnSubmitRequest 事件的事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-121">Add an event handler for the OnSubmitRequest event of a form</span></span>

1. <span data-ttu-id="374fc-122">在“数据”\*\*\*\* 选项卡上，单击“提交选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-122">On the **Data** tab, click **Submit Options**.</span></span>
    
2. <span data-ttu-id="374fc-123">选中“允许用户提交此表单”\*\*\*\* 复选框，然后单击“使用代码执行自定义操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-123">Select the **Allow users to submit this form** check box, and then click **Perform custom action using Code**.</span></span>
    
3. <span data-ttu-id="374fc-124">单击“编辑代码”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-124">Click **Edit Code**, and then click **OK**.</span></span>
    
   <span data-ttu-id="374fc-125">焦点将切换到代码编辑器中 [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx) 事件的事件处理程序的存根。</span><span class="sxs-lookup"><span data-stu-id="374fc-125">The focus switches to the stub for the event handler for the [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx) event in the code editor.</span></span> 
    
### <a name="add-an-event-handler-for-the-onsaverequest-event-of-a-form"></a><span data-ttu-id="374fc-126">为表单的 OnSaveRequest 事件添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-126">Add an event handler for the OnSaveRequest event of a form</span></span>

1. <span data-ttu-id="374fc-127">单击“文件”\*\*\*\* 选项卡，然后单击“表单选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-127">Click the **File** tab, and then click **Form Options**.</span></span>
    
2. <span data-ttu-id="374fc-128">在“保存”\*\*\*\* 类别中，依次单击“使用自定义代码保存”\*\*\*\*、“编辑”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-128">In the **Save** category, click **Save using custom code**, click **Edit**, and then click **OK**.</span></span>
    
   <span data-ttu-id="374fc-129">焦点将切换到代码编辑器中 [OnSaveRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSaveRequest.aspx) 事件的事件处理程序的存根。</span><span class="sxs-lookup"><span data-stu-id="374fc-129">The focus switches to the stub for the event handler for the [OnSaveRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSaveRequest.aspx) event in the code editor.</span></span> 
    
### <a name="add-an-event-handler-for-the-onversionupgrade-event-of-a-form"></a><span data-ttu-id="374fc-130">为表单的 OnVersionUpgrade 事件添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-130">Add an event handler for the OnVersionUpgrade event of a form</span></span>

1. <span data-ttu-id="374fc-131">单击“文件”\*\*\*\* 选项卡，然后单击“表单选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-131">Click the **File** tab, and then click **Form Options**.</span></span>
    
2. <span data-ttu-id="374fc-132">在“版本控制”\*\*\*\* 类别中，从“更新现有表单”\*\*\*\* 列表中选择“使用自定义事件”\*\*\*\*，单击“编辑”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-132">In the **Versioning** category, select **Use custom event** from the **Update existing forms** list, click **Edit**, and then click **OK**.</span></span>
    
    <span data-ttu-id="374fc-133">焦点将切换到代码编辑器中 [OnVersionUpgrade](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnVersionUpgrade.aspx) 事件的事件处理程序的存根。</span><span class="sxs-lookup"><span data-stu-id="374fc-133">The focus switches to the stub for the event handler for the [OnVersionUpgrade](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnVersionUpgrade.aspx) event in the code editor.</span></span> 
    
### <a name="add-an-event-handler-for-the-onmergerequest-event-of-a-form"></a><span data-ttu-id="374fc-134">为表单的 OnMergeRequest 事件添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-134">Add an event handler for the OnMergeRequest event of a form</span></span>

1. <span data-ttu-id="374fc-135">单击“文件”\*\*\*\* 选项卡，然后单击“表单选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-135">Click the **File** tab, and then click **Form Options**.</span></span>
    
2. <span data-ttu-id="374fc-136">在“高级”\*\*\*\* 类别中，选中“启用表单合并”\*\*\*\* 和“使用自定义代码合并”\*\*\*\* 复选框，单击“编辑”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="374fc-136">In the **Advanced** category, select the **Enable Form merging** and the **Merge using custom code** check boxes, click **Edit**, and then click **OK**.</span></span>
    
    <span data-ttu-id="374fc-137">焦点将切换到代码编辑器中 [OnMergeRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnMergeRequest.aspx) 事件的事件处理程序的存根。</span><span class="sxs-lookup"><span data-stu-id="374fc-137">The focus switches to the stub for the event handler for the [OnMergeRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnMergeRequest.aspx) event in the code editor.</span></span> 
    
## <a name="adding-an-event-handler-for-the-onafterimport-event"></a><span data-ttu-id="374fc-138">为 OnAfterImport 事件添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-138">Adding an event handler for the OnAfterImport event</span></span>

<span data-ttu-id="374fc-p102">若要为 [OnAfterImport](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnAfterImport.aspx) 事件添加事件处理程序，必须打开托管代码表单模板的表单代码，手动添加事件处理程序函数。有关如何为此事件编写事件处理程序的信息，请单击 **OnAfterImport** 事件的链接。</span><span class="sxs-lookup"><span data-stu-id="374fc-p102">To add event handlers for the [OnAfterImport](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnAfterImport.aspx) event, you must open the form code for your managed-code form template and add the event handler function manually. For information on how to write an event handler for this event, click the link for the **OnAfterImport** event.</span></span> 
  
## <a name="adding-an-event-handler-for-a-secondary-data-source"></a><span data-ttu-id="374fc-141">为辅助数据源添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-141">Adding an event handler for a secondary data source</span></span>

<span data-ttu-id="374fc-p103">以下示例显示如何为辅助数据源添加一个事件处理程序。该示例假设存在一个来自名为 books.xml 的资源文件的辅助数据源，其架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="374fc-p103">The following example shows how to add an event handler for a secondary data source. The example assumes a secondary data source from a resource file named books.xml, which has the following schema:</span></span>
  
```xml
<?xml version="1.0"?>
<xsd:schema xmlns:xsd="https://www.w3.org/2001/XMLSchema">
    <xsd:element name="catalog">
        <xsd:complexType>
            <xsd:sequence>
                <xsd:element ref="book" minOccurs="0" maxOccurs="unbounded"></xsd:element>
            </xsd:sequence>
        </xsd:complexType>
    </xsd:element>
    <xsd:element name="genre" type="xsd:string"></xsd:element>
    <xsd:element name="author" type="xsd:string"></xsd:element>
    <xsd:element name="book">
        <xsd:complexType>
            <xsd:all>
                <xsd:element ref="author" minOccurs="0" maxOccurs="1"></xsd:element>
                <xsd:element ref="title" minOccurs="0" maxOccurs="1"></xsd:element>
                <xsd:element ref="genre" minOccurs="0" maxOccurs="1"></xsd:element>
                <xsd:element ref="price" minOccurs="0" maxOccurs="1"></xsd:element>
                <xsd:element ref="publish_date" minOccurs="0" maxOccurs="1"></xsd:element>
                <xsd:element ref="description" minOccurs="0" maxOccurs="1"></xsd:element>
            </xsd:all>
            <xsd:attribute ref="id"></xsd:attribute>
        </xsd:complexType>
    </xsd:element>
    <xsd:element name="price" type="xsd:string"></xsd:element>
    <xsd:element name="title" type="xsd:string"></xsd:element>
    <xsd:element name="publish_date" type="xsd:string"></xsd:element>
    <xsd:element name="description" type="xsd:string"></xsd:element>
    <xsd:attribute name="id" type="xsd:string"></xsd:attribute>
</xsd:schema>

```

<br/>

<span data-ttu-id="374fc-p104">表单的视图是从该数据源构建的。表单代码将基于作者及其撰写书目的数量来创建一个哈希表。您可以更新视图中显示的表中的条目，此时 **OnAfterChange** 事件处理程序将更新该哈希表。请注意， [InfoPathEventHandler](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.DataObject.aspx) 属性（由 **InfoPathEventHandlerAttribute** 类实现）的 [DataObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) 属性用于引用辅助数据源。</span><span class="sxs-lookup"><span data-stu-id="374fc-p104">The form's view is built from this data source. The form code creates a hash table based on the authors and the number of books they have written. You can update an entry from the table shown in the view and the **OnAfterChange** event handler updates the hash table. Note that the [DataObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.DataObject.aspx) property of the **InfoPathEventHandler** attribute (which is implemented by the [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) class) is used to reference the secondary data source.</span></span> 
  
```cs
namespace AuxDom
{
    // InfoPathNamespace attribute goes here.
    public class AuxDom
    {
        private XDocument thisXDocument;
        private Application thisApplication;
        private Hashtable authors;
        public void _Startup(Application app, XDocument doc)
        {
            thisXDocument = doc;
            thisApplication = app;
            authors = new Hashtable();
        }
        public void _Shutdown()
        {
            authors.Clear();
        }
        // The following function handler is created by Microsoft
        // Office InfoPath. Do not modify the type or number of
        // arguments. 
        [InfoPathEventHandler(EventType=InfoPathEventType.OnLoad)]
        public void OnLoad(DocReturnEvent e)
        {
            IXMLDOMDocument books = thisXDocument.GetDOM("books");
            DOMNodeList externalAuthors = books.selectNodes("/catalog/book/author");
            foreach (IXMLDOMNode authorNode in externalAuthors)
            {
                AddBookFromAuthor(authorNode.text);
            }
        }
        // The following function handler is created by Microsoft
        // Office InfoPath. Do not modify the type or number of
        // arguments. 
        [InfoPathEventHandler(MatchPath="/catalog/book/author", EventType=InfoPathEventType.OnAfterChange, DataObject="books")]
        public void books__author_OnAfterChange(DataDOMEvent e)
        {
            if (e.IsUndoRedo)
            {
                // An undo or redo operation has occurred and the DOM 
                // is read-only.
                return;
            }
            
            if (e.Source.text != e.NewValue.ToString())
            {
                RemoveBookFromAuthor(e.OldValue.ToString());
                AddBookFromAuthor(e.NewValue.ToString());
            }
        }
        private void AddBookFromAuthor(string authorName)
        {
            if (authors.Contains(authorName))
            {
                authors[authorName] = (int)authors[authorName] + 1;
            }
            else
            {
                authors.Add(authorName, 1);
            }
        }
        private void RemoveBookFromAuthor(string authorName)
        {
            if (authors.Contains(authorName))
            {
                authors[authorName] = (int)authors[authorName] - 1;
            }
            if ((int)authors[authorName] == 0)
            {
                authors.Remove(authorName);
            }
        }
        // The following function handler is created by Microsoft
        // Office InfoPath. Do not modify the type or number of
        // arguments. 
        [InfoPathEventHandler(MatchPath="ShowAuthors", EventType=InfoPathEventType.OnClick)]
        public void ShowAuthors_OnClick(DocActionEvent e)
        {
            // Write your code here.
            StringBuilder report = new StringBuilder();
            foreach (string authorName in authors.Keys)
            {
                report.Append(authorName + ",\t\t\t");
                report.Append(authors[authorName] + "\n");
            }
            thisXDocument.UI.Alert(report.ToString());
        }
    }
}

```

## <a name="how-the-class-that-contains-event-handlers-is-identified"></a><span data-ttu-id="374fc-148">如何标识包含事件处理程序的类</span><span class="sxs-lookup"><span data-stu-id="374fc-148">How the class that contains event handlers is identified</span></span>

<span data-ttu-id="374fc-149">当您新建与 InfoPath 2003 托管代码对象模型兼容的 InfoPath 表单模板项目时，系统会将程序集级别的 **System.ComponentModel.Description** 属性应用于位于表单代码模块开头的类，以标识包含表单模板的所有事件处理程序的类。</span><span class="sxs-lookup"><span data-stu-id="374fc-149">When you create a new InfoPath form template project that is compatible with the InfoPath 2003 managed code object model, an assembly-level **System.ComponentModel.Description** attribute is applied to the class at the beginning of the form code module to identify the class that contains all event handlers for the form template.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="374fc-p105">不要修改该类中的 **System.ComponentModel.Description** 属性。如果对其进行了修改，表单模板将无法标识事件处理程序所在的位置，从而导致事件处理程序无法运行。</span><span class="sxs-lookup"><span data-stu-id="374fc-p105">Do not modify the **System.ComponentModel.Description** attribute in this class. If you do so, your form template will not be able to identify where event handlers are located, and the event handlers will fail to run.</span></span> 
  
```cs
using System;
using Microsoft.Office.Interop.InfoPath.SemiTrust;
// Office integration attribute. Identifies the startup class for the // form. Do not modify.
[assembly: System.ComponentModel.DescriptionAttribute(    "InfoPathStartupClass, Version=1.0, Class=Template1.FormCode")]
```

```vb
Imports System
Imports Microsoft.Office.Interop.InfoPath.SemiTrust
' Office integration attribute. Identifies the startup class for the form. Do not modify.
<Assembly: System.ComponentModel.DescriptionAttribute( _    "InfoPathStartupClass, Version=1.0, Class=Template1.FormCode")>
```

## <a name="how-event-handlers-are-identified"></a><span data-ttu-id="374fc-152">如何标识事件处理程序</span><span class="sxs-lookup"><span data-stu-id="374fc-152">How event handlers are identified</span></span>

<span data-ttu-id="374fc-p106">当您使用 InfoPath 设计模式用户界面中的菜单命令或按钮添加新的事件处理程序时，系统会将事件处理程序函数的存根写入表单。下面的示例演示为 [OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx) （为名为"total"的域添加）创建的存根事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="374fc-p106">When you add a new event handler using menu commands or buttons in the InfoPath design mode user interface, the stub for the event handler function is written into the form. The following example shows the stub event handler created for an [OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx) added for a field named 'total'.</span></span> 
  
```cs
[InfoPathEventHandler(MatchPath="/invoice/total", EventType=InfoPathEventType.OnValidate)]
public void total_OnValidate(DataDOMEvent e)
{
    // Write your code here.
}

```

```vb
<InfoPathEventHandler(MatchPath:="/invoice/total",EventType:= OnValidate)> Public Sub total_OnValidate(ByVal e As EventArgs)
    ' Write your code here.
End Sub

```

<span data-ttu-id="374fc-155">然后，可以通过使用  `thisXDocument` 或  `thisApplication` 变量的专用缓存成员，或者通过使用从  `e` **EventArgs** 对象（通过事件处理程序接收）中访问的成员，来添加调用 InfoPath 对象模型的成员的代码：</span><span class="sxs-lookup"><span data-stu-id="374fc-155">You can then add code that invokes members of the InfoPath object model using the private cached members of the  `thisXDocument` or  `thisApplication` variables, or by using the members accessed from the  `e` **EventArgs** object received by the event handler:</span></span> 
  
```cs
thisXDocument.UI.Alert.(e.Site.text);

```

```vb
thisXDocument.UI.Alert.(e.Site.text)

```

<span data-ttu-id="374fc-156">**InfoPathEventHandler** 属性（由 [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) 类定义）是要用作事件处理程序的函数的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="374fc-156">The **InfoPathEventHandler** attribute (as defined by the [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) class) is the custom attribute for functions that will be used as event handlers.</span></span> 
  
<span data-ttu-id="374fc-p107">当事件需要时， **MatchPath** 参数（由 [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.MatchPath.aspx) 类的 **MatchPath** 属性定义）指定标识事件源的 XPath 表达式。 **EventType** 参数（由 [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.EventType.aspx) 类的 **EventType** 属性定义）指定事件的类型。不应更改这些参数的值。如果更改了这些参数的值，事件处理程序将无法正确编译，或者事件通知将无法按预期发生。</span><span class="sxs-lookup"><span data-stu-id="374fc-p107">When required by the event, the **MatchPath** parameter (as defined by the [MatchPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.MatchPath.aspx) property of the **InfoPathEventHandlerAttribute** class) specifies an XPath expression that identifies the event source. The **EventType** parameter (as defined by the [EventType](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.EventType.aspx) property of the **InfoPathEventHandlerAttribute** class) specifies the type of event. You should not change the values of these parameters. If the values of these parameters are changed, the event handler may not compile correctly, or event notification will not occur as expected.</span></span> 
  
## <a name="obfuscating-code-in-event-handlers"></a><span data-ttu-id="374fc-161">事件处理程序中的模糊处理代码</span><span class="sxs-lookup"><span data-stu-id="374fc-161">Obfuscating code in event handlers</span></span>

<span data-ttu-id="374fc-p108">如果对编译托管代码表单模板时生成的程序集运行模糊器 (obfuscator) 实用程序 ( *projectname*  .dll)，则当用户打开表单时，InfoPath 将无法加载该程序集。如果要对事件处理程序的代码或其他表单代码进行模糊处理，则必须将要模糊处理的代码置于单独的程序集中，在项目中引用该程序集，然后从 FormCode.cs 或 FormCode.vb 调用所引用程序集的成员。仅对引用的程序集运行模糊器实用程序，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="374fc-p108">If you run an obfuscator utility on the assembly that is generated when a managed-code form template is compiled ( *projectname*  .dll), InfoPath will not be able to load the assembly when a user opens the form. If you want to obfuscate the code for your event handlers or other form code, you must put the code that you want to obfuscate in a separate assembly, and reference that assembly in your project, and then call members of the referenced assembly from FormCode.cs or FormCode.vb. It is important that you run the obfuscator utility only on the referenced assembly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="374fc-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="374fc-165">See also</span></span>

- [<span data-ttu-id="374fc-166">使用 InfoPath 2003 对象模型响应表单事件</span><span class="sxs-lookup"><span data-stu-id="374fc-166">Respond to Form Events Using the InfoPath 2003 Object Model</span></span>](how-to-respond-to-form-events-using-the-infopath-2003-object-model.md)

