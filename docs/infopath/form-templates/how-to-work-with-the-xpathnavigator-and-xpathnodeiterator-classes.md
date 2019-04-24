---
title: 使用 XPathNavigator 和 XPathNodeIterator 类
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
keywords:
- xpathnodeiterator class [infopath 2007],XPathNavigator class [InfoPath 2007],form XML data [InfoPath 2007], accessing,XML DOM [InfoPath 2007],converting MSXML5 script [InfoPath 2007],MSXML5 script [InfoPath 2007], converting
localization_priority: Normal
ms.assetid: 72fb3ee5-f18e-4f9c-adc6-698ac037b79d
description: 为了访问和操作表单模板数据源中的 XML 数据，可以让 Microsoft.Office.InfoPath 命名空间提供的许多托管代码对象模型成员创建 System.Xml.XPath 命名空间的 XPathNavigator 类的一个实例，或者可以向它们传递一个这样的实例。在您具有 InfoPath 对象模型成员所返回的 XPathNavigator 对象的访问权限后，可以使用 XPathNavigator 类的属性和方法处理数据。
ms.openlocfilehash: f34f2e1a1cbdb8d9e389c864a9b979be20726e6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303547"
---
# <a name="work-with-the-xpathnavigator-and-xpathnodeiterator-classes"></a>使用 XPathNavigator 和 XPathNodeIterator 类

为了访问和操作表单模板数据源中的 XML 数据，可以让 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的许多托管代码对象模型成员创建 **System.Xml.XPath** 命名空间的 **XPathNavigator** 类的一个实例，或者可以向它们传递一个这样的实例。在您具有 InfoPath 对象模型成员所返回的 **XPathNavigator** 对象的访问权限后，可以使用 **XPathNavigator** 类的属性和方法处理数据。 
  
使用 **XPathNavigator** 类的 **Microsoft.Office.InfoPath** 命名空间的最常用的成员是 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 类的 [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 方法，您可以通过该方法处理 **DataSource** 对象代表的存储数据。 **CreateNavigator** 方法创建一个 **XPathNavigator** 对象，该对象位于 **DataSource** 对象代表的数据源的根节点处。 
  
> [!TIP]
> 如果您熟悉在脚本中使用 MSXML5 处理 Microsoft InfoPath 2003 中的数据，就可以将 **CreateNavigator** 方法视为 **DataObject** 的 **DOM** 属性的替代者。 
  
## <a name="using-the-xpathnavigator-class-to-access-the-main-data-source-of-the-form"></a>使用 XPathNavigator 类访问表单的主数据源

若要访问表单的主数据源，请直接通过 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) (C#) 或 **Me** (Visual Basic) 关键字调用 **CreateNavigator** 方法。下面的示例使用 **CreateNavigator** 方法创建一个位于主数据源的根节点处的 **XPathNavigator** 对象，然后使用 **XPathNavigator** 类的 **OuterXml** 属性，在一个消息框中显示返回的 XML。 
  
```cs
XPathNavigator myNavigator = 
   this.CreateNavigator();
MessageBox.Show("Main data source XML: " +
   myNavigator.OuterXml.ToString());
```

```vb
Dim myNavigator As XPathNavigator  = _
   Me.CreateNavigator()
MessageBox.Show("Main data source XML: " &amp; _
   myNavigator.OuterXml.ToString())
```

> [!NOTE]
> 直接通过 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 或 **Me** 关键字调用 **CreateNavigator** 方法等同于：通过使用 [MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 属性 (  [](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx)) 或通过向 `this.MainDataSource.CreateNavigator()` 类 (  [](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx)) 的 [DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性传递一个空字符串来调用 `this.DataSources[""].CreateNavigator()` 方法。 
  
## <a name="selecting-and-setting-the-xml-nodes-for-fields-in-the-main-data-source"></a>选择和设置主数据源中的域的 XML 节点
<a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a>

若要选择数据源中的某个域的单一 XML 节点，请使用 **XPathNavigator** 类的 **SelectSingleNode(String,IXmlNamespaceResolver)** 方法。若要处理一组重复域或重复组，请使用 **XPathNavigator** 类的 **Select(String,IXmlNamespaceResolver)** 方法。此方法返回一个表示节点集合的 **XPathNodeIterator** 对象。 
  
### <a name="selecting-and-setting-the-value-of-a-single-node"></a>选择和设置单一节点的值

您必须使用的重载的 **SelectSingleNode** 方法具有以下两个参数：一个采用 XPath 表达式作为字符串的  _xpath_ 参数，以及一个采用 _XmlNamespaceManager_ 对象来解析命名空间前缀的  **resolver** 参数。若要选择表单的主数据源中的单个节点，请为  _xpath_ 参数传入指定要选择的域或组的 XPath 表达式，以及由 **XmlForm** 对象的 [NamespaceManager](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.NamespaceManager.aspx) 属性返回的 **XmlNamespaceManager** 对象。返回的 **XmlNamespaceManager** 对象在加载时通过表单模板的表单定义文件 (.xsf) 所定义的所有命名空间进行初始化。 
  
> [!TIP]
> The easiest way to create an XPath expression for selecting a node in the form's data source is to right-click the field or group in the **Fields** task pane, and then click **Copy XPath**. To create and test hand-edited XPath expressions for accessing nodes in a complex or heavily nested XML schema, add an **Expression Box** control to the form, specify the XPath expression for the control, and then preview the form to display the results. 
  
下面的示例使用 **SelectSingleNode** 方法选择  `EmailAlias` 域的单一节点。然后，它使用 **XPathNavigator** 类的 **SetValue** 方法和 [User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) 类的 [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) 属性将该域的值设置为当前用户的别名。 
  
```cs
XPathNavigator emailAlias = 
   this.CreateNavigator().SelectSingleNode(
      "/my:myFields/my:EmailAlias", NamespaceManager);
emailAlias.SetValue(this.Application.User.UserName.ToString());
```

```vb
Dim emailAlias As XPathNavigator = _
   Me.CreateNavigator().SelectSingleNode( _
      "/my:myFields/my:EmailAlias", NamespaceManager)
emailAlias.SetValue(Me.Application.User.UserName.ToString())
```

有关如何创建 XPath 表达式的信息，请参阅 MSDN 上的 XPath 参考和 [XML Path 语言 (XPath) 版本 1.0 W3C 建议](https://www.w3.org/TR/xpath)。
  
### <a name="setting-the-value-of-a-node-that-has-the-xsinil-attribute"></a>设置具有 xsi:nil 属性的节点的值

对于某些数据类型，尝试以编程方式设置空白域的值时将引发"架构验证过程发现非数据类型错误"错误。导致出现此错误的原因通常是，元素的 [xsi:nil](https://www.w3.org/TR/2001/REC-xmlschema-1-20010502/#xsi_nil) 属性设置为 **true**。如果您检查表单中空白域的基础 XML 元素，您会看到此设置。例如，以下空白日期域的 XML 段的 **xsi:nil** 属性设置为 **true**。
  
```XML
<my:myDate xsi:nil="true"></my:myDate>
```

如果 **xsi:nil** 属性设置为 **true**，则表示相应元素存在但没有值，或者换句话说就是元素为 null。如果您尝试以编程方式设置这样一个节点的值，InfoPath 将显示"架构验证过程发现非数据类型错误"消息，原因是元素当前标记为 null。InfoPath 将以下数据类型的 null 域的 **xsi:nil** 属性设置为 **true**： 
  
- **Whole Number (integer)**
    
- **Decimal (double)**
    
- **Date (date)**
    
- **Time (time)**
    
- **Date and Time (dateTime)**
    
为了防止发生此错误，您的代码必须测试 **xsi:nil** 属性。如果该属性存在，则在设置节点值前删除该属性。下面的子例程采用一个位于您要设置的节点上的 **XpathNavigator** 对象，检查 **nil** 属性，然后将其删除（如果它存在）。 
  
```cs
public void DeleteNil(XPathNavigator node)
{
   if (node.MoveToAttribute(
      "nil", "https://www.w3.org/2001/XMLSchema-instance"))
      node.DeleteSelf();
}
```

```vb
Public Sub DeleteNil(ByVal node As XPathNavigator)
   If (node.MoveToAttribute( _
      "nil", "https://www.w3.org/2001/XMLSchema-instance")) Then
      node.DeleteSelf()
   End If
End Sub
```

在尝试设置可能具有 **xsi:nil** 属性的某数据类型的域之前，您可以调用此子例程，如以下设置日期域的示例所示。 
  
```cs
// Access the main data source.
XPathNavigator myForm = this.CreateNavigator();
// Select the field.
XPathNavigator myDate = myForm.SelectSingleNode("/my:myFields/my:myDate", NamespaceManager);
// Check for and remove the "nil" attribute.
DeleteNil(myDate);
// Build the current date in the proper format. (yyyy-mm-dd)
string curDate = DateTime.Today.Year + "-" + DateTime.Today.Month + 
   "-" + DateTime.Today.Day;
// Set the value of the myDate field.
myDate.SetValue(strCurDate);
```

```vb
' Access the main data source.
Dim myForm As XPathNavigator = Me.CreateNavigator()
' Select the field.
Dim myDate As XPathNavigator = _
   myForm.SelectSingleNode("/my:myFields/my:myDate", NamespaceManager)
' Check for and remove the "nil" attribute.
DeleteNil(myDate)
' Build the current date in the proper format. (yyyy-mm-dd)
Dim curDate As String = DateTime.Today.Year + "-" + _
   DateTime.Today.Month + "-" + DateTime.Today.Day
' Set the value of the myDate field.
myDate.SetValue(strCurDate)
```

> [!NOTE]
> 尽管 InfoPath 中的 **XPathNavigator** 对象实现可公开 **SetTypedValue** 方法（用于设置使用特定类型值的节点），但是 InfoPath 不会实现该方法。您必须改用 **SetValue** 方法，并为节点的数据类型传递一个正确格式的字符串值。 
  
### <a name="selecting-and-setting-a-set-of-repeating-nodes"></a>选择和设置一组重复节点

若要指定一组为不确定数字的重复字段或组，请使用 **XPathNavigator** 类的 **Select** 方法。 此方法会返回一个 XPathNodeIterator 对象，你可以使用该对象迭代指定的节点集合。 
  
下面的示例假定你的表单模板包含一个绑定到名为 `field1` 的重复元素的**项目符号列表**或类似的重复控件。 字段的 XPath 传递给 **Select** 方法，返回的 **XPathNodeIterator** 分配给 `nodes` 变量。 使用 MoveNext 方法迭代节点集合，使用 Current 属性返回位于当前节点上的 **XPathNavigator** 对象。 最后，使用 **Value** 属性检索并显示每个重复字段的值。 
  
```cs
string message = String.Empty;
XPathNavigator root = this.CreateNavigator();
XPathNodeIterator nodes = 
   root.Select("/my:myFields/my:group1/my:field1", NamespaceManager);
while (nodes.MoveNext())
{
    message += nodes.Current.Value + System.Environment.NewLine;
}
MessageBox.Show(message);
```

```vb
Dim message As String = String.Empty
Dim root As XPathNavigator = Me.CreateNavigator()
Dim nodes As XPathNodeIterator = _
   root.Select("/my:myFields/my:group1/my:field1", NamespaceManager)
Do While nodes.MoveNext
    message += nodes.Current.Value &amp; System.Environment.NewLine
Loop
MessageBox.Show(message)
```

前面的示例使用指定的重复域中的字符串值。但是，如果该域包含数值，则可使用类似代码循环访问该域中的值以进行算术运算，如计算值的总计或平均数。
  
同样，不必使用 **Value** 属性来检索重复域的每个实例的值，您可以改为使用 **SetValue** 方法来循环访问各个域并设置它们的值，如以下示例所示。 
  
```cs
XPathNavigator root = this.CreateNavigator();
XPathNodeIterator nodes = 
   root.Select("/my:myFields/my:group1/my:field1", NamespaceManager);
int myInt = 1;
while (nodes.MoveNext())
{
   nodes.Current.SetValue(myInt.ToString());
   myInt = myInt + 1;
}
```

```vb
Dim root As XPathNavigator = Me.CreateNavigator()
Dim nodes As XPathNodeIterator = _
   root.Select("/my:myFields/my:group1/my:field1", NamespaceManager)
Dim myInt As Integer = 1
Do While nodes.MoveNext
   nodes.Current.SetValue(myInt.ToString())
   myInt = myInt + 1
Loop
```

## <a name="using-the-xpathnavigator-class-to-access-an-external-data-source"></a>使用 XPathNavigator 类访问外部数据源
<a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a>

To access an external data source associated with the form, pass the name of the data source to the [DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class. To create a connection to a new external data source, or to view a list of the names of existing external data source connections, click **Data Connections** on the **Data** tab of the ribbon. 
  
下面的代码示例演示如何使用 **CreateNavigator** 方法创建一个位于名为"CityList"的外部数据源的根节点处的 **XPathNavigator** 对象，然后使用 **XPathNavigator** 类的 **OuterXml** 属性在一个消息框中显示返回的 XML。该代码示例假定您创建了一个与存储在外部数据源（如 XML 文档或 SharePoint 列表）中的城市名称列表的连接，并将该数据连接命名为"CityList"。 
  
```cs
XPathNavigator myNavigator = 
   this.DataSources["CityList"].CreateNavigator();
MessageBox.Show("External data source XML: " + 
   myNavigator.OuterXml.ToString());
```

```vb
Dim myNavigator As XPathNavigator  = _
   Me.DataSources("CityList").CreateNavigator()
MessageBox.Show("External data source XML: " &amp; _
   myNavigator.OuterXml.ToString())
```

在您具有对位于外部数据源的根节点处的 **XPathNavigator** 对象的访问权限后，您可以使用 **XPathNavigator** 类的成员（如 **SelectSingleNode** 和 **SetValue** 方法）处理该对象包含的数据。 
  
## <a name="infopath-object-model-members-that-use-the-xpathnavigator-and-xpathnodeiterator-classes"></a>使用 XPathNavigator 和 XPathNodeIterator 类的 InfoPath 对象模型成员
<a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a>

下表汇总了 **Microsoft.Office.InfoPath** 命名空间中所有使用 **XPathNavigator** 类访问、操作或提交 XML 数据的成员。 
  
|**父类**|**成员**|
|:-----|:-----|
|[AdoQueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoQueryConnection.aspx) <br/> |[BuildSqlFromXmlNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoQueryConnection.BuildSqlFromXmlNodes.aspx) 方法  <br/> |
|[AdoSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoSubmitConnection.aspx) <br/> |[BuildSqlFromXmlNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoSubmitConnection.BuildSqlFromXmlNodes.aspx) 方法  <br/> |
|[ClickedEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ClickedEventArgs.aspx) <br/> |[Source](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ClickedEventArgs.Source.aspx) 属性  <br/> |
|[ContextChangedEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ContextChangedEventArgs.aspx) <br/> |[Context](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ContextChangedEventArgs.Context.aspx) 属性  <br/> |
|[DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) <br/> |[CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 方法  <br/> |
||[GetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.GetNamedNodeProperty.aspx) 方法  <br/> |
||[SetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.SetNamedNodeProperty.aspx) 方法  <br/> |
|[EmailSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.EmailSubmitConnection.aspx) <br/> |[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.EmailSubmitConnection.Execute.aspx) 方法  <br/> |
|[FileQueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileQueryConnection.aspx) <br/> |[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileQueryConnection.Execute.aspx) 方法  <br/> |
|[FileSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileSubmitConnection.aspx) <br/> |[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileSubmitConnection.Execute.aspx) 方法  <br/> |
|[FormError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.aspx) <br/> |[Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.Site.aspx) 属性  <br/> |
|[FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) <br/> |[Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Add.aspx) 方法  <br/> |
|[FormTemplate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.aspx) <br/> |[Manifest](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.Manifest.aspx) 属性  <br/> |
|[MergeEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.MergeEventArgs.aspx) <br/> |[Xml](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.MergeEventArgs.Xml.aspx) 属性  <br/> |
|[SharepointListQueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SharepointListQueryConnection.aspx) <br/> |[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SharepointListQueryConnection.Execute.aspx) 方法  <br/> |
|[Signature](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) <br/> |[SignatureBlockXmlNode](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.SignatureBlockXmlNode.aspx) 属性  <br/> |
|[SignedDataBlock](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) <br/> |[SignatureContainer](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.SignatureContainer.aspx) 属性  <br/> |
|[View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) <br/> |[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法  <br/> |
||[SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法  <br/> |
||[SelectText](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法  <br/> |
|[WebServiceConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.aspx) <br/> |[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.Execute.aspx) 方法  <br/> |
||[GenerateDataSetDiffGram](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.GenerateDataSetDiffGram.aspx) 方法  <br/> |
|[XmlEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.aspx) <br/> |[OldParent](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.OldParent.aspx) 属性  <br/> |
||[Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.Site.aspx) 属性  <br/> |
|[XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) <br/> |[MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) 属性，该属性返回一个 **DataSource** 对象，接着该对象提供 **CreateNavigator** 方法，用于创建位于表单的基础 XML 文档（主数据源）的根节点处的 **XPathNavigator** 对象。  <br/> |
||[MergeForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MergeForm.aspx) 方法  <br/> |
|[XmlFormCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.aspx) <br/> |[NewFromFormTemplate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.NewFromFormTemplate.aspx) 方法  <br/> |
|[XmlValidatingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.aspx) <br/> |[ReportError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.ReportError.aspx) 方法  <br/> |
   
除了返回或接受 **XPathNavigator** 对象的 InfoPath 对象模型成员外，以下方法返回 **System.Xml.XPath** 命名空间的 **XPathNodeIterator** 类的实例，用来迭代在视图中指定或选择的项的 XML 节点。 
  
|**父类**|**成员**|
|:-----|:-----|
|[View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) <br/> |[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法  <br/> |
||[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetSelectedNodes.aspx) 方法  <br/> |
   
## <a name="using-the-xpathnavigator-and-xpathnodeiterator-classes-to-work-with-data-selected-in-a-view"></a>使用 XPathNavigator 和 XPathNodeIterator 类处理在视图中选择的数据
<a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a>

下面的示例使用 **XPathNavigator** 和 **XPathNodeIterator** 类的成员按照以下顺序处理表单数据： 
  
1. 使用 **DataSource** 类的 **CreateNavigator** 方法创建一个名为 repeatingTableRow1 的 **XPathNavigator** 对象变量，默认情况下该对象变量位于表单的基础 XML 文档（主数据源）的根节点处。
    
2. 使用 **XPathNavigator** 类的 **SelectSingleNode** 方法将 **XPathNavigator** 对象的位置移到“重复表”**** 控件的第一行，该控件绑定到数据源中的 group2。 
    
3. 将 repeatingTableRow1 对象变量传递到 **View** 类的 **SelectNodes** 方法，以选择该行中的节点。 
    
4. 声明一个名为 selectedNodes 的 **XPathNodeIterator** 对象变量，并使用 **View** 类的 **GetSelectedNodes** 方法用所选的节点填充 **XPathNodeIterator** 对象。 
    
5. 使用 **XPathNodeIterator** 类的 **Count** 属性显示包含在 selectedNodes 对象变量中的节点数。 
    
6. 使用 For/Each 循环迭代 selectedNodes 对象变量中的节点，并使用 **XPathNavigator** 类的 **Name**、 **InnerXml** 和 **Value** 属性显示有关每个节点的信息。 
    
```cs
// Create XPathNavigator and specify XPath for nodes.
XPathNavigator repeatingTableRow1 = 
   this.CreateNavigator().SelectSingleNode(
   "/my:myFields/my:group1/my:group2[1]", NamespaceManager);
// Select nodes in specified XPathNavigator.
CurrentView.SelectNodes(repeatingTableRow1);
// Get selected nodes.
XPathNodeIterator selectedNodes = 
   CurrentView.GetSelectedNodes();
// Display the count of selected nodes.
MessageBox.Show(selectedNodes.Count.ToString());
// Loop through collection and display information.
foreach (XPathNavigator selectedNode in selectedNodes)
{
   MessageBox.Show(selectedNode.Name);
   MessageBox.Show(selectedNode.InnerXml);
   MessageBox.Show(selectedNode.Value);
}
```

```vb
' Create XPathNavigator and specify XPath for nodes.
Dim repeatingTableRow1 As XPathNavigator  = _
   Me.CreateNavigator().SelectSingleNode( _
   "/my:myFields/my:group1/my:group2[1]", NamespaceManager)
' Select nodes in specified XPathNavigator.
CurrentView.SelectNodes(repeatingTableRow1)
' Get selected nodes.
Dim selectedNodes As XPathNodeIterator = _
   CurrentView.GetSelectedNodes()
' Display the count of selected nodes.
MessageBox.Show(selectedNodes.Count.ToString())
' Loop through collection and display information.
Dim selectedNode As XPathNavigator
For Each selectedNode In selectedNodes
   MessageBox.Show(selectedNode.Name)
   MessageBox.Show(selectedNode.InnerXml)
   MessageBox.Show(selectedNode.Value)
Next
```

有关如何处理 InfoPath 表单模板中的 XML 数据的详细信息，请参阅使用 InfoPath 2007 表单模板中的 XPathNavigator 类处理 XML 数据。
  

