---
title: 访问表单数据
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
keywords:
- form data [infopath 2007],forms [InfoPath 2007], accessing properties,form templates [InfoPath 2007], accessing properties,opening forms [InfoPath 2007],printing forms [InfoPath 2007],forms [InfoPath 2007], printing,closing forms [InfoPath 2007],InfoPath 2007, accessing form data,forms [InfoPath 2007], accessing data source,forms [InfoPath 2007], closing,forms [InfoPath 2007], opening,printing [InfoPath 2007], forms,forms [InfoPath 2007], creating
localization_priority: Normal
ms.assetid: fd7374d3-a268-4e30-9872-7579cd681bd0
description: 如果要扩展 InfoPath 表单的功能，通常必须以编程方式访问有关表单的基础 XML 文档的信息，访问 XML 文档所包含的数据或对 XML 文档执行某操作。InfoPath 对象模型通过结合使用 XmlForm 类和 XmlFormCollection 类来支持对表单的基础 XML 文档的访问和操作。
ms.openlocfilehash: c8251afcd75391f102215811694515c06b9f3e7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300208"
---
# <a name="access-form-data"></a>访问表单数据

如果要扩展 InfoPath 表单的功能，通常必须以编程方式访问有关表单的基础 XML 文档的信息，访问 XML 文档所包含的数据或对 XML 文档执行某操作。InfoPath 对象模型通过结合使用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 类和 [XmlFormCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.aspx) 类来支持对表单的基础 XML 文档的访问和操作。 
  
[XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 类是 InfoPath 对象模型中最有用的类型之一，因为它提供各种属性和方法，不仅能与表单的基础 XML 文档进行交互，而且能够执行可从 InfoPath 用户界面中执行的许多操作。 
  
## <a name="overview-of-the-xmlformcollection-class"></a>XmlFormCollection 类概述

[XmlFormCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.aspx) 类提供下列方法和属性，表单开发人员可以使用它们管理集合所包含的 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 对象。 
  
|**名称**|**说明**|
|:-----|:-----|
|[New(String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.New.aspx) 方法  <br/> |基于指定的表单创建新表单。  <br/> |
|[New(String, XmlFormOpenMode)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.New.aspx) 方法（重载 1）  <br/> |使用指定的打开模式行为，基于指定的表单创建新表单。  <br/> |
|[NewFromFormTemplate(String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.NewFromFormTemplate.aspx) 方法  <br/> |基于指定的表单模板创建新表单。  <br/> |
|[NewFromFormTemplate(String, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.NewFromFormTemplate.aspx) 方法（重载 1）  <br/> |基于指定的表单模板和 XML 数据创建新表单。  <br/> |
|[NewFromFormTemplate(String, String, XmlFormOpenMode)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.NewFromFormTemplate.aspx) 方法（重载 2）  <br/> |基于指定的表单模板以及由 [XPathNavigator](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator%28v=vs.110%29.aspx) 对象指定的数据创建新表单。  <br/> |
|[NewFromFormTemplate(String, XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.NewFromFormTemplate.aspx) 方法（重载 3）  <br/> |使用指定的打开模式行为，基于指定的表单模板以及由 **XPathNavigator** 对象指定的数据创建新表单。  <br/> |
|[Open(String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.Open.aspx) 方法  <br/> |打开指定的表单。  <br/> |
|[Open(String, XmlFormOpenMode)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.Open.aspx) 方法（重载 1）  <br/> |使用指定的打开模式行为打开指定表单。  <br/> |
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.Count.aspx) 属性  <br/> |获取集合中包含的 **XmlForm** 对象的数目。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.Item.aspx) 属性  <br/> |按照索引值获取一个对集合中指定 **XmlForm** 对象的引用。  <br/> |
   
## <a name="overview-of-the-xmlform-class"></a>XmlForm 类概述

[XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 类提供下列方法和属性，表单开发人员可以使用它们与表单的基础 XML 文档进行交互，并对该文档执行操作。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Close](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Close.aspx) 方法  <br/> |关闭表单。  <br/> |
|[GetWorkflowTasks](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.GetWorkflowTasks.aspx) 方法  <br/> |获取一个对当前表单的 **Microsoft.Office.Core.WorkflowTasks** 集合的引用。  <br/> |
|[GetWorkflowTemplates](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.GetWorkflowTemplates.aspx) 方法  <br/> |获取一个对当前表单的 **Microsoft.Office.Core.WorkflowTemplates** 集合的引用。  <br/> |
|[MergeForm(String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MergeForm.aspx) 方法  <br/> |将当前表单与通过路径或 URL 指定的表单合并。  <br/> |
|[MergeForm(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MergeForm.aspx) 方法（重载 1）  <br/> |将当前表单与传递到该方法的 **XPathNavigator** 所返回的节点中指定的目标表单进行合并。  <br/> |
|[NotifyHost](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.NotifyHost.aspx) 方法  <br/> |为宿主应用程序或 ASPX 页提供自定义值。  <br/> |
|[Print()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Print.aspx) 方法  <br/> |按照表单内容在表单的活动视图中的显示效果打印表单内容。  <br/> |
|[Print(Boolean)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Print.aspx) 方法（重载 1）  <br/> |通过显示“打印”对话框打印在表单的活动视图中呈现的表单内容。  <br/> |
|[Save](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Save.aspx) 方法  <br/> |将表单保存到当前关联的统一资源定位器 (URL)。  <br/> |
|[SaveAs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SaveAs.aspx) 方法  <br/> |将表单保存到指定的统一资源定位器 (URL)。  <br/> |
|[SetSaveAsDialogFilename](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SetSaveAsDialogFilename.aspx) 方法  <br/> |设置“另存为”对话框的默认文件名。  <br/> |
|[SetSaveAsDialogLocation](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SetSaveAsDialogLocation.aspx) 方法  <br/> |设置使用“另存为”对话框保存表单的默认路径。  <br/> |
|[Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Submit.aspx) 方法  <br/> |使用表单模板中定义的提交操作来提交表单。  <br/> |
|[CurrentView](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.CurrentView.aspx) 属性  <br/> |获取一个代表表单的当前视图的 [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 对象。  <br/> |
|[DataConnections](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataConnections.aspx) 属性  <br/> |获取一个与表单关联的 [DataConnectionCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataConnectionCollection.aspx) 对象。  <br/> |
|[DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx) 属性  <br/> |获取与表单关联的 [DataSourceCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.aspx) 对象。  <br/> |
|[Dirty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Dirty.aspx) 属性  <br/> |获取一个值，该值指示表单中的数据自上次保存之后是否被修改过。  <br/> |
|[Errors](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Errors.aspx) 属性  <br/> |获取一个对与表单关联的 [FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) 的引用。  <br/> |
|[Extension](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Extension.aspx) 属性  <br/> |获取一个 [System.Object](https://msdn.microsoft.com/library/system.object%28v=vs.110%29.aspx)，用于使用 [System.Reflection](https://msdn.microsoft.com/library/system.reflection(v=vs.110).aspx) 访问表单的主要表单代码文件中包含的函数和全局变量。  <br/> |
|[FormState](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.FormState.aspx) 属性  <br/> |获取一个对 [System.Collections.IDictionary](https://msdn.microsoft.com/library/system.collections.idictionary%28v=vs.110%29.aspx) 类型的属性包的引用，启用浏览器功能的表单可以使用该属性包来维护服务器上各个会话的状态信息。  <br/> |
|[Host](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Host.aspx) 属性  <br/> |获取一个 [System.Object](https://msdn.microsoft.com/library/system.object%28v=vs.110%29.aspx)，在 InfoPath 的宿主实例中运行的代码可以使用它访问宿主应用程序的对象模型。  <br/> |
|[Hosted](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Hosted.aspx) 属性  <br/> |获取一个值，指示 InfoPath 是否作为控件承载在另一个应用程序中。  <br/> |
|[HostName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.HostName.aspx) 属性  <br/> |获取将 InfoPath 作为控件承载的应用程序的名称。  <br/> |
|[MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) 属性  <br/> |获取一个代表表单主数据源的 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 对象。  <br/> |
|[NamespaceManager](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.NamespaceManager.aspx) 属性  <br/> |获取一个对 [XmlNamespaceManager](https://msdn.microsoft.com/library/System.Xml.XmlNamespaceManager.aspx) 对象的引用，该对象可用于解析、添加或删除表单中使用的命名空间。  <br/> |
|[New](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.New.aspx) 属性  <br/> |获取一个指定表单是否为新表单的值。  <br/> |
|[Permission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Permission.aspx) 属性  <br/> |获取一个对与表单关联的 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.aspx) 对象的引用。  <br/> |
|[QueryDataConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.QueryDataConnection.aspx) 属性  <br/> |获取一个对 [DataConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataConnection.aspx) 对象的引用，该对象代表与表单关联的数据连接。  <br/> |
|[ReadOnly](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.ReadOnly.aspx) 属性  <br/> |获取一个值，该值指示表单模板是否处于只读或锁定状态。  <br/> |
|[Recovered](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Recovered.aspx) 属性  <br/> |获取一个值，该值指示表单上次是否是由自动恢复保存操作保存的。  <br/> |
|[Signed](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Signed.aspx) 属性  <br/> |获取一个值，该值指示是否已经对表单进行过数字签名。  <br/> |
|[SignedDataBlocks](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SignedDataBlocks.aspx) 属性  <br/> |获取一个对与表单关联的 [SignedDataBlockCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlockCollection.aspx) 集合的引用。  <br/> |
|[TaskPanes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.TaskPanes.aspx) 属性  <br/> |获取一个对与表单模板关联的 [TaskPaneCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.TaskPaneCollection.aspx) 的引用。  <br/> |
|[Template](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Template.aspx) 属性  <br/> |获取一个对 [FormTemplate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.aspx) 对象的引用，该对象代表与表单关联的表单模板的清单 (.xsf)。  <br/> |
|[Uri](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Uri.aspx) 属性  <br/> |获取表单的统一资源标识符 (URI)。  <br/> |
|[UserRole](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.UserRole.aspx) 属性  <br/> |获取或设置表单角色名称的当前用户。  <br/> |
|[ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.ViewInfos.aspx) 属性  <br/> |获取一个对与表单模板关联的 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 对象的引用  <br/> |
|[XmlLang](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.XmlLang.aspx) 属性  <br/> |获取表单的基础 XML 文档中 **xml:lang** 属性的值。  <br/> |
   
## <a name="using-the-xmlformcollection-class"></a>使用 XmlFormCollection 类

可以通过 **Application** 类的 [XmlForms](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.XmlForms.aspx) 属性访问 [XmlFormCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类。在使用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的成员提供的对象模型创建的托管代码表单模板中，可以在表单代码中使用 **this** (C#) 或 **Me** (Visual Basic) 关键字访问 **Application** 类及其成员。 
  
下面的示例使用 **Application** 类的 **XmlForms** 属性创建一个名为 myForms 的对象变量，该对象变量引用当前运行的 InfoPath 实例的 **XDocumentsCollection** 对象。然后，此变量可用来显示已打开表单的数量。 
  
```cs
// Create variable for accessing the XmlFormCollection.
XmlFormCollection myForms = this.Application.XmlForms;
// Display the number of forms that are currently open.
MessageBox.Show("Forms open: " + myForms.Count);
```

```vb
// Create variable for accessing the XmlFormCollection.
Dim myForms As XmlFormCollection = Me.Application.XmlForms
' Display the number of forms that are currently open.
MessageBox.Show("Forms open: " + myForms.Count)
```

然后，还可以使用 myForms 变量创建新表单（使用 **New** 或 **NewFromTemplate** 方法之一），或者打开现有表单（使用 **Open** 方法之一）。 
  
## <a name="using-the-xmlform-class"></a>使用 XmlForm 类

在使用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间的成员提供的对象模型创建的托管代码表单模板中，可以在表单代码中使用 **this** (C#) 或 **Me** (Visual Basic) 关键字直接访问 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 类的成员（而无需对象变量建立对 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 类的引用）。 
  
### <a name="accessing-a-forms-property-values"></a>访问表单的属性值

下面的示例使用 **this** 或 **Me** 关键字访问 **XmlForm** 类的 **New**、 **ReadOnly**、 **Signed** 和 **Uri** 属性，并在一个消息框中显示为当前表单返回的值。 
  
```cs
MessageBox.Show(
   "Is new: " + this.New + System.Environment.NewLine +
   "Is read-only: " + this.ReadOnly + System.Environment.NewLine +
   "Is signed: " + this.Signed + System.Environment.NewLine +
   "Form URI: " + this.Uri);
```

```vb
MessageBox.Show( _
   "Is new: " &amp; Me.New &amp; System.Environment.NewLine &amp; _
   "Is read-only: " &amp; Me.ReadOnly &amp; System.Environment.NewLine + _
   "Is signed: " &amp; Me.Signed &amp; System.Environment.NewLine &amp; _
   "Form URI: " &amp; this.Uri)
```

### <a name="accessing-a-forms-data-source"></a>访问表单的数据源

**XmlForm** 类与表单数据有关的一个关键属性是 **MainDataSource** 属性。此属性返回对 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 对象的引用，该对象代表当前表单的基础 XML 数据，也称为表单的 主 数据源或 主要 数据源。 **DataSource** 类提供了 [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 方法，该方法可创建一个位于表单基础 XML 文档根节点处的 [XPathNavigator](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator%28v=vs.110%29.aspx) 对象。随后，可以使用 **XPathNavigator** 类的属性和方法来浏览和编辑表单的基础 XML 数据。 
  
下面的示例使用 **XmlForm** 类的 **MainDataSource** 属性创建一个位于表单主数据源根节点处的 **XPathNavigator** 对象。然后，可以使用 **XPathNavigator** 类的 **OuterXml** 属性返回和显示表单的基础 XML 文档的全部内容。 
  
```cs
// Get outer XML of the underlying XML document.
string myDoc = this.MainDataSource.CreateNavigator.OuterXml.ToString();
// Display XML.
MessageBox.Show(myDoc);
```

```vb
' Get outer XML of the underlying XML document.
Dim myDoc As String myDoc = _
   Me.MainDataSource.CreateNavigator.OuterXml.ToString()
' Display XML.
MessageBox.Show(myDoc)
```

> [!NOTE]
> 由于在使用 **this** 或 **Me** 关键字访问时，InfoPath 将 **MainDataSource** 属性视为 **XmlForm** 对象的默认属性，因此可以在用于创建 **XPathNavigator** 对象的代码行中省略该属性。 
  
若要了解有关 InfoPath 表单模板业务逻辑中的 **XPathNavigator** 类的详细信息，请参阅 [使用 XPathNavigator 和 XPathNodeIterator 类](how-to-work-with-the-xpathnavigator-and-xpathnodeiterator-classes.md)。
  
### <a name="accessing-data-about-a-forms-form-template-file"></a>访问有关表单的表单模板文件的数据

还可以使用 **XmlForm** 类访问有关与某个表单关联的表单模板的信息，包括表单定义文件 (.xsf ) 和表单所包含的源 XML 数据。使用 [Template](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Template.aspx) 属性可以访问这些信息，该属性返回对 [FormTemplate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.aspx) 对象的引用，而该对象代表与当前表单关联的表单模板。 
  
在下面的示例中，第一个消息框显示通过 **Template** 类提供的一些数据，例如，统一资源标识符 (URI) 位置（使用 [Uri](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.Uri.aspx) 属性）、缓存标识符（使用 [CacheId](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.CacheId.aspx) 属性）及其版本号（使用 [Version](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.Version.aspx) 属性）。下一个消息框使用 [Template](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.Manifest.aspx) 类的 **Manifest** 属性创建一个 **XPathNavigator** 对象，该对象用来显示表单定义文件 (.xsf) 的源 XML。 
  
```cs
// Display form template properties.
MessageBox.Show(
   "Cache ID: " + this.Template.CacheId + System.Environment.NewLine +
   "URI: " + this.ReadOnly + System.Environment.NewLine +
   "Version: " + this.Signed, "Form Template Properties");
// Display form definition file XML.
MessageBox.Show(this.Template.Manifest.OuterXml, 
   "Form Definition File XML");
```

```vb
' Display form template properties.
MessageBox.Show( _
   "Cache ID: " &amp; Me.Template.CacheId &amp; System.Environment.NewLine &amp;
   "URI: " &amp; Me.ReadOnly &amp; System.Environment.NewLine &amp;
   "Version: " &amp; Me.Signed, "Form Template Properties")
' Display form definition file XML.
MessageBox.Show(Me.Template.Manifest.OuterXml, _
   "Form Definition File XML")
```


