---
title: 添加事件处理程序使用 InfoPath 对象模型
manager: soliver
ms.date: 01/20/2015
ms.audience: Developer
keywords:
- onafterimport event [infopath 2007],OnAfterChange event [InfoPath 2007],OnBeforeChange event [InfoPath 2007],OnSubmitRequest event [InfoPath 2007],OnVersionUpgrade event [InfoPath 2007],InfoPath 2003-compatible form templates, event handlers,OnLoad event [InfoPath 2007],event handlers [InfoPath 2007], adding using InfoPath 2003 object model,OnValidate event [InfoPath 2007],OnContextChange event [InfoPath 2007],OnSaveRequest event [InfoPath 2007],OnClick event [InfoPath 2007],OnSwitchView event [InfoPath 2007],OnSign event [InfoPath 2007],OnMergeRequest event [InfoPath 2007]
localization_priority: Normal
ms.assetid: 0520df55-2d91-4cc5-be31-82144a2db4f6
description: 用于与 InfoPath 2003 对象模型兼容的表单模板项目中添加事件处理程序函数菜单命令本质上是相同的其他类型的表单模板。
ms.openlocfilehash: 9f037c59180b9c8d858ec73d79ef892974efe483
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773995"
---
# <a name="add-an-event-handler-using-the-infopath-object-model"></a>添加事件处理程序使用 InfoPath 对象模型

用于与 InfoPath 2003 对象模型兼容的表单模板项目中添加事件处理程序函数菜单命令本质上是相同的其他类型的表单模板。 例如，以便添加**OnLoad**事件处理程序，在 InfoPath 设计器中，打开表单模板中，单击**开发人员**选项卡上的**Onload 事件**命令。自动，焦点将切换到 Visual Studio 2012 代码编辑器中的**OnLoad**事件处理程序的表单代码。 
  
在与 InfoPath 2003 兼容的托管代码表单模板项目中，包含事件处理程序函数和事件处理程序本身的类都用代码模块中专用于 InfoPath 的属性来标识。

## <a name="adding-event-handlers"></a>添加事件处理程序

以下所有过程都假设您在含有 Visual Studio 2008 的 Microsoft InfoPath 中打开了一个表单模板项目。
  
### <a name="add-an-event-handler-for-the-onclick-event-of-a-command-button"></a>为命令按钮的 OnClick 事件添加事件处理程序

1. 在**控件**窗格中，单击**按钮**以向表单添加按钮。 
    
2. 在**属性**选项卡中，单击**自定义代码**。
    
   焦点将切换到代码编辑器中 [OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) 事件的事件处理程序的存根。 
    
### <a name="add-an-event-handler-for-the-onbeforechange-onvalidate-or-onafterchange-event-of-a-field-or-group"></a>为域或组的 OnBeforeChange、OnValidate 或 OnAfterChange 事件添加事件处理程序

1. 右键单击绑定到域或组，例如**文本框**控件的数据输入控件。 
    
2. 指向**编程**，，然后单击其中一个命令，如**Onvalidate 事件**。
    
   焦点将切换到代码编辑器中的以下事件之一事件处理程序的存根： [OnBeforeChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnBeforeChange.aspx)、 [OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx)或[OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx)。 
    
### <a name="add-an-event-handler-for-the-onload-onswitchview-oncontextchange-or-onsign-event-of-a-form"></a>为表单的 OnLoad、OnSwitchView、OnContextChange 或 OnSign 事件添加事件处理程序

- 在**工具**菜单中，指向**编程**，，然后单击您想要编写事件处理程序的表单事件。
    
    焦点将切换到代码编辑器中下面某个事件处理程序的存根： [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx)、 [OnSwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSwitchView.aspx)、 [OnContextChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnContextChange.aspx)或[OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSign.aspx)。 
    
### <a name="add-an-event-handler-for-the-onsubmitrequest-event-of-a-form"></a>为表单的 OnSubmitRequest 事件添加事件处理程序

1. 在**数据**选项卡中，单击**提交选项**。
    
2. 选择**允许用户提交此表单**复选框，然后单击**执行使用代码的自定义操作**。
    
3. 单击**编辑代码**，然后单击**确定**。
    
   焦点将切换到代码编辑器中 [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx) 事件的事件处理程序的存根。 
    
### <a name="add-an-event-handler-for-the-onsaverequest-event-of-a-form"></a>为表单的 OnSaveRequest 事件添加事件处理程序

1. 单击**文件**选项卡，然后单击**表单选项**。
    
2. 在**保存**类别中中,，单击**使用自定义代码保存**，单击**编辑**，然后单击**确定**。
    
   焦点将切换到代码编辑器中 [OnSaveRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSaveRequest.aspx) 事件的事件处理程序的存根。 
    
### <a name="add-an-event-handler-for-the-onversionupgrade-event-of-a-form"></a>为表单的 OnVersionUpgrade 事件添加事件处理程序

1. 单击**文件**选项卡，然后单击**表单选项**。
    
2. 在**版本控制**类别中，从**更新现有表单**列表中选择**使用自定义事件**，单击**编辑**，然后单击**确定**。
    
    焦点将切换到代码编辑器中 [OnVersionUpgrade](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnVersionUpgrade.aspx) 事件的事件处理程序的存根。 
    
### <a name="add-an-event-handler-for-the-onmergerequest-event-of-a-form"></a>为表单的 OnMergeRequest 事件添加事件处理程序

1. 单击**文件**选项卡，然后单击**表单选项**。
    
2. 在**高级**类别中，选择**启用表单合并**和**使用自定义代码合并**复选框、 单击**编辑**，然后单击**确定**。
    
    焦点将切换到代码编辑器中 [OnMergeRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnMergeRequest.aspx) 事件的事件处理程序的存根。 
    
## <a name="adding-an-event-handler-for-the-onafterimport-event"></a>添加事件处理程序 OnAfterImport 事件

若要为 [OnAfterImport](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnAfterImport.aspx) 事件添加事件处理程序，必须打开托管代码表单模板的表单代码，手动添加事件处理程序函数。有关如何为此事件编写事件处理程序的信息，请单击 **OnAfterImport** 事件的链接。 
  
## <a name="adding-an-event-handler-for-a-secondary-data-source"></a>添加事件处理程序辅助数据源

以下示例显示如何为辅助数据源添加一个事件处理程序。该示例假设存在一个来自名为 books.xml 的资源文件的辅助数据源，其架构如下所示：
  
```xml
<?xml version="1.0"?>
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
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

表单的视图是从该数据源构建的。表单代码将基于作者及其撰写书目的数量来创建一个哈希表。您可以更新视图中显示的表中的条目，此时 **OnAfterChange** 事件处理程序将更新该哈希表。请注意， [InfoPathEventHandler](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.DataObject.aspx) 属性（由 **InfoPathEventHandlerAttribute** 类实现）的 [DataObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) 属性用于引用辅助数据源。 
  
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

## <a name="how-the-class-that-contains-event-handlers-is-identified"></a>如何标识包含事件处理程序的类

当您新建与 InfoPath 2003 托管代码对象模型兼容的 InfoPath 表单模板项目时，系统会将程序集级别的 **System.ComponentModel.Description** 属性应用于位于表单代码模块开头的类，以标识包含表单模板的所有事件处理程序的类。 
  
> [!IMPORTANT]
> [!重要信息] 不要修改该类中的 **System.ComponentModel.Description** 属性。如果对其进行了修改，表单模板将无法标识事件处理程序所在的位置，从而导致事件处理程序无法运行。 
  
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

## <a name="how-event-handlers-are-identified"></a>如何标识事件处理程序

当您使用 InfoPath 设计模式用户界面中的菜单命令或按钮添加新的事件处理程序时，系统会将事件处理程序函数的存根写入表单。下面的示例演示为 [OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx) （为名为"total"的域添加）创建的存根事件处理程序。 
  
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

然后，可以通过使用  `thisXDocument` 或  `thisApplication` 变量的专用缓存成员，或者通过使用从  `e` **EventArgs** 对象（通过事件处理程序接收）中访问的成员，来添加调用 InfoPath 对象模型的成员的代码： 
  
```cs
thisXDocument.UI.Alert.(e.Site.text);

```

```vb
thisXDocument.UI.Alert.(e.Site.text)

```

**InfoPathEventHandler** 属性（由 [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) 类定义）是要用作事件处理程序的函数的自定义属性。 
  
当事件需要时， **MatchPath** 参数（由 [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.MatchPath.aspx) 类的 **MatchPath** 属性定义）指定标识事件源的 XPath 表达式。 **EventType** 参数（由 [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.EventType.aspx) 类的 **EventType** 属性定义）指定事件的类型。不应更改这些参数的值。如果更改了这些参数的值，事件处理程序将无法正确编译，或者事件通知将无法按预期发生。 
  
## <a name="obfuscating-code-in-event-handlers"></a>事件处理程序中的模糊处理代码

如果对编译托管代码表单模板时生成的程序集运行模糊器 (obfuscator) 实用程序 ( *projectname*  .dll)，则当用户打开表单时，InfoPath 将无法加载该程序集。如果要对事件处理程序的代码或其他表单代码进行模糊处理，则必须将要模糊处理的代码置于单独的程序集中，在项目中引用该程序集，然后从 FormCode.cs 或 FormCode.vb 调用所引用程序集的成员。仅对引用的程序集运行模糊器实用程序，这一点很重要。 
  
## <a name="see-also"></a>另请参阅

- [响应表单事件使用 InfoPath 2003 对象模型](how-to-respond-to-form-events-using-the-infopath-2003-object-model.md)

