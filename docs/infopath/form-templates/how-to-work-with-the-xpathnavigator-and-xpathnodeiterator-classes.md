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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393038"
---
# <a name="work-with-the-xpathnavigator-and-xpathnodeiterator-classes"></a><span data-ttu-id="2a1df-105">使用 XPathNavigator 和 XPathNodeIterator 类</span><span class="sxs-lookup"><span data-stu-id="2a1df-105">Work with the XPathNavigator and XPathNodeIterator Classes</span></span>

<span data-ttu-id="2a1df-p102">为了访问和操作表单模板数据源中的 XML 数据，可以让 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的许多托管代码对象模型成员创建 **System.Xml.XPath** 命名空间的 **XPathNavigator** 类的一个实例，或者可以向它们传递一个这样的实例。在您具有 InfoPath 对象模型成员所返回的 **XPathNavigator** 对象的访问权限后，可以使用 **XPathNavigator** 类的属性和方法处理数据。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p102">To access and manipulate the XML data in form template data sources, many members of the managed code object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace either create or can be passed an instance of the **XPathNavigator** class of the **System.Xml.XPath** namespace. After you have access to an **XPathNavigator** object returned by an InfoPath object model member, you can use the properties and methods of the **XPathNavigator** class to work with the data.</span></span> 
  
<span data-ttu-id="2a1df-p103">使用 **XPathNavigator** 类的 **Microsoft.Office.InfoPath** 命名空间的最常用的成员是 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 类的 [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 方法，您可以通过该方法处理 **DataSource** 对象代表的存储数据。 **CreateNavigator** 方法创建一个 **XPathNavigator** 对象，该对象位于 **DataSource** 对象代表的数据源的根节点处。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p103">The most frequently used member of the **Microsoft.Office.InfoPath** namespace that uses the **XPathNavigator** class is the [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) method of the [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) class, which enables you to work with the stored data represented by a **DataSource** object. The **CreateNavigator** method creates an **XPathNavigator** object positioned at the root of the data source represented by the **DataSource** object.</span></span> 
  
> [!TIP]
> <span data-ttu-id="2a1df-110">如果您熟悉在脚本中使用 MSXML5 处理 Microsoft InfoPath 2003 中的数据，就可以将 **CreateNavigator** 方法视为 **DataObject** 的 **DOM** 属性的替代者。</span><span class="sxs-lookup"><span data-stu-id="2a1df-110">If you are familiar with using MSXML5 from script to work with data in Microsoft InfoPath 2003, you can think of the **CreateNavigator** method as the replacement for the **DOM** property of the **DataObject**.</span></span> 
  
## <a name="using-the-xpathnavigator-class-to-access-the-main-data-source-of-the-form"></a><span data-ttu-id="2a1df-111">使用 XPathNavigator 类访问表单的主数据源</span><span class="sxs-lookup"><span data-stu-id="2a1df-111">Using the XPathNavigator Class to Access the Main Data Source of the Form</span></span>

<span data-ttu-id="2a1df-p104">若要访问表单的主数据源，请直接通过 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) (C#) 或 **Me** (Visual Basic) 关键字调用 **CreateNavigator** 方法。下面的示例使用 **CreateNavigator** 方法创建一个位于主数据源的根节点处的 **XPathNavigator** 对象，然后使用 **XPathNavigator** 类的 **OuterXml** 属性，在一个消息框中显示返回的 XML。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p104">To access the main data source of the form, call the [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) method directly from the **this** (C#) or **Me** (Visual Basic) keyword. The following example creates an **XPathNavigator** object positioned at the root of the main data source by using the **CreateNavigator** method, and then uses the **OuterXml** property of the **XPathNavigator** class to display the XML returned in a message box.</span></span> 
  
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
> <span data-ttu-id="2a1df-114">直接通过 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 或 **Me** 关键字调用 **CreateNavigator** 方法等同于：通过使用 [MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 属性 (  [](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx)) 或通过向 `this.MainDataSource.CreateNavigator()` 类 (  [](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx)) 的 [DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性传递一个空字符串来调用 `this.DataSources[""].CreateNavigator()` 方法。</span><span class="sxs-lookup"><span data-stu-id="2a1df-114">Calling the [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) method directly from the **this** or **Me** keyword is equivalent to calling [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) method by using the [MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) property (  `this.MainDataSource.CreateNavigator()`) or by passing an empty string to the [DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class (  `this.DataSources[""].CreateNavigator()`).</span></span> 
  
## <a name="selecting-and-setting-the-xml-nodes-for-fields-in-the-main-data-source"></a><span data-ttu-id="2a1df-115">选择和设置主数据源中的域的 XML 节点</span><span class="sxs-lookup"><span data-stu-id="2a1df-115">Selecting and Setting the XML Nodes for Fields in the Main Data Source</span></span>
<span data-ttu-id="2a1df-116"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a1df-116"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span></span>

<span data-ttu-id="2a1df-p105">若要选择数据源中的某个域的单一 XML 节点，请使用 **XPathNavigator** 类的 **SelectSingleNode(String,IXmlNamespaceResolver)** 方法。若要处理一组重复域或重复组，请使用 **XPathNavigator** 类的 **Select(String,IXmlNamespaceResolver)** 方法。此方法返回一个表示节点集合的 **XPathNodeIterator** 对象。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p105">To select the single XML node for a field in a data source, use the **SelectSingleNode(String,IXmlNamespaceResolver)** method of the **XPathNavigator** class. If you want to work with a set of repeating fields or repeating groups, use the **Select(String,IXmlNamespaceResolver)** method of the **XPathNavigator** class. This method returns an **XPathNodeIterator** object that represents a collection of nodes.</span></span> 
  
### <a name="selecting-and-setting-the-value-of-a-single-node"></a><span data-ttu-id="2a1df-120">选择和设置单一节点的值</span><span class="sxs-lookup"><span data-stu-id="2a1df-120">Selecting and Setting the Value of a Single Node</span></span>

<span data-ttu-id="2a1df-p106">您必须使用的重载的 **SelectSingleNode** 方法具有以下两个参数：一个采用 XPath 表达式作为字符串的  _xpath_ 参数，以及一个采用 _XmlNamespaceManager_ 对象来解析命名空间前缀的  **resolver** 参数。若要选择表单的主数据源中的单个节点，请为  _xpath_ 参数传入指定要选择的域或组的 XPath 表达式，以及由 **XmlForm** 对象的 [NamespaceManager](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.NamespaceManager.aspx) 属性返回的 **XmlNamespaceManager** 对象。返回的 **XmlNamespaceManager** 对象在加载时通过表单模板的表单定义文件 (.xsf) 所定义的所有命名空间进行初始化。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p106">The overloaded **SelectSingleNode** method that you must use has an  _xpath_ parameter that takes an XPath expression as a string, and a  _resolver_ parameter that takes an **XmlNamespaceManager** object for resolving namespace prefixes. To select a single node in the form's main data source, pass in an XPath expression that specifies the field or group that you want to select for the  _xpath_ parameter, together with the **XmlNamespaceManager** object that is returned by the [NamespaceManager](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.NamespaceManager.aspx) property of the **XmlForm** object. The returned **XmlNamespaceManager** object is initialized at load time with all the namespaces that are defined by the form template's form definition file (.xsf).</span></span> 
  
> [!TIP]
> <span data-ttu-id="2a1df-p107">创建用于在表单数据源中选择节点的 XPath 表达式的最简单方法是：在“域”\*\*\*\* 任务窗格中右键单击相应域或组，然后单击“复制 XPath”\*\*\*\*。若要创建和测试手动编辑的 XPath 表达式，以访问复杂或重重嵌套的 XML 架构中的节点，请将一个“表达式框”\*\*\*\* 控件添加到表单中，为该控件指定 XPath 表达式，然后预览表单以显示结果。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p107">The easiest way to create an XPath expression for selecting a node in the form's data source is to right-click the field or group in the **Fields** task pane, and then click **Copy XPath**. To create and test hand-edited XPath expressions for accessing nodes in a complex or heavily nested XML schema, add an **Expression Box** control to the form, specify the XPath expression for the control, and then preview the form to display the results.</span></span> 
  
<span data-ttu-id="2a1df-p108">下面的示例使用 **SelectSingleNode** 方法选择  `EmailAlias` 域的单一节点。然后，它使用 **XPathNavigator** 类的 **SetValue** 方法和 [User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) 类的 [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) 属性将该域的值设置为当前用户的别名。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p108">The following example uses the **SelectSingleNode** method to select the single node for the  `EmailAlias` field. Then it uses the **SetValue** method of the **XPathNavigator** class and the [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) property of the [User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) class to set the value of the field to the current user's alias.</span></span> 
  
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

<span data-ttu-id="2a1df-128">有关如何创建 XPath 表达式的信息，请参阅 MSDN 上的 XPath 参考和 [XML Path 语言 (XPath) 版本 1.0 W3C 建议](https://www.w3.org/TR/xpath)。</span><span class="sxs-lookup"><span data-stu-id="2a1df-128">For information about how to create XPath expressions, see the XPath Reference on MSDN, and the [XML Path Language (XPath) Version 1.0 W3C Recommendation](https://www.w3.org/TR/xpath).</span></span>
  
### <a name="setting-the-value-of-a-node-that-has-the-xsinil-attribute"></a><span data-ttu-id="2a1df-129">设置具有 xsi:nil 属性的节点的值</span><span class="sxs-lookup"><span data-stu-id="2a1df-129">Setting the Value of a Node That Has the xsi:nil Attribute</span></span>

<span data-ttu-id="2a1df-p109">对于某些数据类型，尝试以编程方式设置空白域的值时将引发"架构验证过程发现非数据类型错误"错误。导致出现此错误的原因通常是，元素的 [xsi:nil](https://www.w3.org/TR/2001/REC-xmlschema-1-20010502/#xsi_nil) 属性设置为 **true**。如果您检查表单中空白域的基础 XML 元素，您会看到此设置。例如，以下空白日期域的 XML 段的 **xsi:nil** 属性设置为 **true**。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p109">For certain data types, trying to set the value of a blank field programmatically raises the error "Schema validation found non-data type errors." Typically the cause of this error is that the element has the [xsi:nil](https://www.w3.org/TR/2001/REC-xmlschema-1-20010502/#xsi_nil) attribute set to **true**. If you examine the underlying XML element for the blank field in the form, you can see this setting. For example, the XML fragment for the following blank Date field has the **xsi:nil** attribute set to **true**.</span></span>
  
```XML
<my:myDate xsi:nil="true"></my:myDate>
```

<span data-ttu-id="2a1df-p110">如果 **xsi:nil** 属性设置为 **true**，则表示相应元素存在但没有值，或者换句话说就是元素为 null。如果您尝试以编程方式设置这样一个节点的值，InfoPath 将显示"架构验证过程发现非数据类型错误"消息，原因是元素当前标记为 null。InfoPath 将以下数据类型的 null 域的 **xsi:nil** 属性设置为 **true**：</span><span class="sxs-lookup"><span data-stu-id="2a1df-p110">If the **xsi:nil** attribute is set to **true**, it indicates that the element is present but has no value, or in other words, is null . If you try to programmatically set the value of such a node, InfoPath displays the "Schema validation found non-data type errors" message because the element is currently flagged as being null . InfoPath sets the **xsi:nil** attribute to **true** for null fields of the following data types:</span></span> 
  
- <span data-ttu-id="2a1df-137">**Whole Number (integer)**</span><span class="sxs-lookup"><span data-stu-id="2a1df-137">**Whole Number (integer)**</span></span>
    
- <span data-ttu-id="2a1df-138">**Decimal (double)**</span><span class="sxs-lookup"><span data-stu-id="2a1df-138">**Decimal (double)**</span></span>
    
- <span data-ttu-id="2a1df-139">**Date (date)**</span><span class="sxs-lookup"><span data-stu-id="2a1df-139">**Date (date)**</span></span>
    
- <span data-ttu-id="2a1df-140">**Time (time)**</span><span class="sxs-lookup"><span data-stu-id="2a1df-140">**Time (time)**</span></span>
    
- <span data-ttu-id="2a1df-141">**Date and Time (dateTime)**</span><span class="sxs-lookup"><span data-stu-id="2a1df-141">**Date and Time (dateTime)**</span></span>
    
<span data-ttu-id="2a1df-p111">为了防止发生此错误，您的代码必须测试 **xsi:nil** 属性。如果该属性存在，则在设置节点值前删除该属性。下面的子例程采用一个位于您要设置的节点上的 **XpathNavigator** 对象，检查 **nil** 属性，然后将其删除（如果它存在）。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p111">To prevent this error, your code must test for the **xsi:nil** attribute, and if it is present, remove it before setting the value of the node. The following subroutine takes an **XpathNavigator** object positioned on the node that you want to set, checks for the **nil** attribute, and then deletes it, if it exists.</span></span> 
  
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

<span data-ttu-id="2a1df-144">在尝试设置可能具有 **xsi:nil** 属性的某数据类型的域之前，您可以调用此子例程，如以下设置日期域的示例所示。</span><span class="sxs-lookup"><span data-stu-id="2a1df-144">You can call this subroutine before you try to set a field of a data type that might have the **xsi:nil** attribute, as shown in the following example that sets a Date field.</span></span> 
  
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
> <span data-ttu-id="2a1df-p112">尽管 InfoPath 中的 **XPathNavigator** 对象实现可公开 **SetTypedValue** 方法（用于设置使用特定类型值的节点），但是 InfoPath 不会实现该方法。您必须改用 **SetValue** 方法，并为节点的数据类型传递一个正确格式的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p112">Although the implementation of the **XPathNavigator** object in InfoPath exposes the **SetTypedValue** method—which is used to set a node using a value of a specific type—InfoPath does not implement that method. You must use the **SetValue** method instead, and pass a string value of the correct format for the data type of the node.</span></span> 
  
### <a name="selecting-and-setting-a-set-of-repeating-nodes"></a><span data-ttu-id="2a1df-147">选择和设置一组重复节点</span><span class="sxs-lookup"><span data-stu-id="2a1df-147">Selecting and Setting a Set of Repeating Nodes</span></span>

<span data-ttu-id="2a1df-p113">若要指定一组不定数量的重复域或组，请使用 **XPathNavigator** 类的 **Select** 方法。此方法返回一个 XPathNodeIterator 对象，您可使用该对象来循环访问指定的节点集合。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p113">To specify a set of repeating fields or groups that are of an indeterminate number, use the **Select** method of the **XPathNavigator** class. This method returns an XPathNodeIterator object that you can use to iterate over the specified collection of nodes.</span></span> 
  
<span data-ttu-id="2a1df-150">下面的示例假定你的表单模板包含一个绑定到名为 `field1` 的重复元素的**项目符号列表**或类似的重复控件。</span><span class="sxs-lookup"><span data-stu-id="2a1df-150">The following example assumes that your form template contains a **Bulleted List** or similar repeating control that is bound to a repeating element named  `field1`.</span></span> <span data-ttu-id="2a1df-151">字段的 XPath 传递给 **Select** 方法，返回的 **XPathNodeIterator** 分配给 `nodes` 变量。</span><span class="sxs-lookup"><span data-stu-id="2a1df-151">The XPath of the field is passed to the **Select** method, and the returned **XPathNodeIterator** is assigned to the  `nodes` variable.</span></span> <span data-ttu-id="2a1df-152">使用 MoveNext 方法迭代节点集合，使用 Current 属性返回位于当前节点上的 **XPathNavigator** 对象。</span><span class="sxs-lookup"><span data-stu-id="2a1df-152">You use the MoveNext method to iterate over the collection of nodes, and the Current property to return an **XPathNavigator** object positioned on the current node.</span></span> <span data-ttu-id="2a1df-153">最后，使用 **Value** 属性检索并显示每个重复字段的值。</span><span class="sxs-lookup"><span data-stu-id="2a1df-153">Finally, use the **Value** property to retrieve and display the value of each repeating field.</span></span> 
  
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

<span data-ttu-id="2a1df-p115">前面的示例使用指定的重复域中的字符串值。但是，如果该域包含数值，则可使用类似代码循环访问该域中的值以进行算术运算，如计算值的总计或平均数。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p115">The previous example works with string values in the specified repeating field. However, if the field contains numeric values, you can use similar code to iterate over the values in the field to perform arithmetic, such as calculating the total or average of the values.</span></span>
  
<span data-ttu-id="2a1df-156">同样，不必使用 **Value** 属性来检索重复域的每个实例的值，您可以改为使用 **SetValue** 方法来循环访问各个域并设置它们的值，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2a1df-156">Similarly, instead of using the **Value** property to retrieve the value of each instance of the repeating field, you can use the **SetValue** method to iterate over the fields and set their values, as shown in the following example.</span></span> 
  
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

## <a name="using-the-xpathnavigator-class-to-access-an-external-data-source"></a><span data-ttu-id="2a1df-157">使用 XPathNavigator 类访问外部数据源</span><span class="sxs-lookup"><span data-stu-id="2a1df-157">Using the XPathNavigator Class to Access an External Data Source</span></span>
<span data-ttu-id="2a1df-158"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a1df-158"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span></span>

<span data-ttu-id="2a1df-159">若要访问与表单关联的外部数据源，请将数据源的名称传递给 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 类的 [DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx) 属性。</span><span class="sxs-lookup"><span data-stu-id="2a1df-159">To access an external data source associated with the form, pass the name of the data source to the [DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class.</span></span> <span data-ttu-id="2a1df-160">若要创建与新外部数据源的连接，或查看现有外部数据源连接的名称列表，请单击功能区的“数据”\*\*\*\* 选项卡上的“数据连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a1df-160">To create a connection to a new external data source, or to view a list of the names of existing external data source connections, click **Data Connections** on the **Data** tab of the ribbon.</span></span> 
  
<span data-ttu-id="2a1df-p117">下面的代码示例演示如何使用 **CreateNavigator** 方法创建一个位于名为"CityList"的外部数据源的根节点处的 **XPathNavigator** 对象，然后使用 **XPathNavigator** 类的 **OuterXml** 属性在一个消息框中显示返回的 XML。该代码示例假定您创建了一个与存储在外部数据源（如 XML 文档或 SharePoint 列表）中的城市名称列表的连接，并将该数据连接命名为"CityList"。</span><span class="sxs-lookup"><span data-stu-id="2a1df-p117">The following code sample shows how to create an **XPathNavigator** object positioned at the root of an external data source named "CityList" by using the **CreateNavigator** method, and then uses the **OuterXml** property of the **XPathNavigator** class to display the XML returned in a message box. This code sample assumes that you created a data connection to a list of city names that are stored in an external data source, such as an XML document or a SharePoint list, and named that data connection "CityList."</span></span> 
  
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

<span data-ttu-id="2a1df-163">在您具有对位于外部数据源的根节点处的 **XPathNavigator** 对象的访问权限后，您可以使用 **XPathNavigator** 类的成员（如 **SelectSingleNode** 和 **SetValue** 方法）处理该对象包含的数据。</span><span class="sxs-lookup"><span data-stu-id="2a1df-163">After you have access to an **XPathNavigator** object positioned at the root of an external data source, you can use members of the **XPathNavigator** class such as the **SelectSingleNode** and **SetValue** methods to work with the data it contains.</span></span> 
  
## <a name="infopath-object-model-members-that-use-the-xpathnavigator-and-xpathnodeiterator-classes"></a><span data-ttu-id="2a1df-164">使用 XPathNavigator 和 XPathNodeIterator 类的 InfoPath 对象模型成员</span><span class="sxs-lookup"><span data-stu-id="2a1df-164">InfoPath Object Model Members That Use the XPathNavigator and XPathNodeIterator Classes</span></span>
<span data-ttu-id="2a1df-165"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a1df-165"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span></span>

<span data-ttu-id="2a1df-166">下表汇总了 **Microsoft.Office.InfoPath** 命名空间中所有使用 **XPathNavigator** 类访问、操作或提交 XML 数据的成员。</span><span class="sxs-lookup"><span data-stu-id="2a1df-166">The following table provides a summary of all of the members of the **Microsoft.Office.InfoPath** namespace that use the **XPathNavigator** class to access, manipulate, or submit XML data.</span></span> 
  
|<span data-ttu-id="2a1df-167">**父类**</span><span class="sxs-lookup"><span data-stu-id="2a1df-167">**Parent Class**</span></span>|<span data-ttu-id="2a1df-168">**成员**</span><span class="sxs-lookup"><span data-stu-id="2a1df-168">**Member**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2a1df-169">AdoQueryConnection</span><span class="sxs-lookup"><span data-stu-id="2a1df-169">AdoQueryConnection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoQueryConnection.aspx) <br/> |<span data-ttu-id="2a1df-170">[BuildSqlFromXmlNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoQueryConnection.BuildSqlFromXmlNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-170">[BuildSqlFromXmlNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoQueryConnection.BuildSqlFromXmlNodes.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-171">AdoSubmitConnection</span><span class="sxs-lookup"><span data-stu-id="2a1df-171">AdoSubmitConnection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoSubmitConnection.aspx) <br/> |<span data-ttu-id="2a1df-172">[BuildSqlFromXmlNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoSubmitConnection.BuildSqlFromXmlNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-172">[BuildSqlFromXmlNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoSubmitConnection.BuildSqlFromXmlNodes.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-173">ClickedEventArgs</span><span class="sxs-lookup"><span data-stu-id="2a1df-173">ClickedEventArgs</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ClickedEventArgs.aspx) <br/> |<span data-ttu-id="2a1df-174">[Source](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ClickedEventArgs.Source.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-174">[Source](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ClickedEventArgs.Source.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-175">ContextChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="2a1df-175">ContextChangedEventArgs</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ContextChangedEventArgs.aspx) <br/> |<span data-ttu-id="2a1df-176">[Context](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ContextChangedEventArgs.Context.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-176">[Context](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ContextChangedEventArgs.Context.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-177">DataSource</span><span class="sxs-lookup"><span data-stu-id="2a1df-177">DataSource</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) <br/> |<span data-ttu-id="2a1df-178">[CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-178">[CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) method</span></span>  <br/> |
||<span data-ttu-id="2a1df-179">[GetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.GetNamedNodeProperty.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-179">[GetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.GetNamedNodeProperty.aspx) method</span></span>  <br/> |
||<span data-ttu-id="2a1df-180">[SetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.SetNamedNodeProperty.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-180">[SetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.SetNamedNodeProperty.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-181">EmailSubmitConnection</span><span class="sxs-lookup"><span data-stu-id="2a1df-181">EmailSubmitConnection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.EmailSubmitConnection.aspx) <br/> |<span data-ttu-id="2a1df-182">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.EmailSubmitConnection.Execute.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-182">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.EmailSubmitConnection.Execute.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-183">FileQueryConnection</span><span class="sxs-lookup"><span data-stu-id="2a1df-183">FileQueryConnection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileQueryConnection.aspx) <br/> |<span data-ttu-id="2a1df-184">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileQueryConnection.Execute.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-184">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileQueryConnection.Execute.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-185">FileSubmitConnection</span><span class="sxs-lookup"><span data-stu-id="2a1df-185">FileSubmitConnection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileSubmitConnection.aspx) <br/> |<span data-ttu-id="2a1df-186">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileSubmitConnection.Execute.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-186">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileSubmitConnection.Execute.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-187">FormError</span><span class="sxs-lookup"><span data-stu-id="2a1df-187">FormError</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.aspx) <br/> |<span data-ttu-id="2a1df-188">[Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.Site.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-188">[Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.Site.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-189">FormErrorCollection</span><span class="sxs-lookup"><span data-stu-id="2a1df-189">FormErrorCollection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) <br/> |<span data-ttu-id="2a1df-190">[Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Add.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-190">[Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Add.aspx) methods</span></span>  <br/> |
|[<span data-ttu-id="2a1df-191">FormTemplate</span><span class="sxs-lookup"><span data-stu-id="2a1df-191">FormTemplate</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.aspx) <br/> |<span data-ttu-id="2a1df-192">[Manifest](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.Manifest.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-192">[Manifest](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormTemplate.Manifest.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-193">MergeEventArgs</span><span class="sxs-lookup"><span data-stu-id="2a1df-193">MergeEventArgs</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.MergeEventArgs.aspx) <br/> |<span data-ttu-id="2a1df-194">[Xml](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.MergeEventArgs.Xml.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-194">[Xml](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.MergeEventArgs.Xml.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-195">SharepointListQueryConnection</span><span class="sxs-lookup"><span data-stu-id="2a1df-195">SharepointListQueryConnection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SharepointListQueryConnection.aspx) <br/> |<span data-ttu-id="2a1df-196">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SharepointListQueryConnection.Execute.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-196">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SharepointListQueryConnection.Execute.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-197">Signature</span><span class="sxs-lookup"><span data-stu-id="2a1df-197">Signature</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.aspx) <br/> |<span data-ttu-id="2a1df-198">[SignatureBlockXmlNode](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.SignatureBlockXmlNode.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-198">[SignatureBlockXmlNode](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Signature.SignatureBlockXmlNode.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-199">SignedDataBlock</span><span class="sxs-lookup"><span data-stu-id="2a1df-199">SignedDataBlock</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.aspx) <br/> |<span data-ttu-id="2a1df-200">[SignatureContainer](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.SignatureContainer.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-200">[SignatureContainer](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignedDataBlock.SignatureContainer.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-201">View</span><span class="sxs-lookup"><span data-stu-id="2a1df-201">View</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) <br/> |<span data-ttu-id="2a1df-202">[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-202">[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) methods</span></span>  <br/> |
||<span data-ttu-id="2a1df-203">[SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-203">[SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) methods</span></span>  <br/> |
||<span data-ttu-id="2a1df-204">[SelectText](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-204">[SelectText](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) methods</span></span>  <br/> |
|[<span data-ttu-id="2a1df-205">WebServiceConnection</span><span class="sxs-lookup"><span data-stu-id="2a1df-205">WebServiceConnection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.aspx) <br/> |<span data-ttu-id="2a1df-206">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.Execute.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-206">[Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.Execute.aspx) method</span></span>  <br/> |
||<span data-ttu-id="2a1df-207">[GenerateDataSetDiffGram](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.GenerateDataSetDiffGram.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-207">[GenerateDataSetDiffGram](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.GenerateDataSetDiffGram.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-208">XmlEventArgs</span><span class="sxs-lookup"><span data-stu-id="2a1df-208">XmlEventArgs</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.aspx) <br/> |<span data-ttu-id="2a1df-209">[OldParent](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.OldParent.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-209">[OldParent](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.OldParent.aspx) property</span></span>  <br/> |
||<span data-ttu-id="2a1df-210">[Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.Site.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2a1df-210">[Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.Site.aspx) property</span></span>  <br/> |
|[<span data-ttu-id="2a1df-211">XmlForm</span><span class="sxs-lookup"><span data-stu-id="2a1df-211">XmlForm</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) <br/> |<span data-ttu-id="2a1df-212">[MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) 属性，该属性返回一个 **DataSource** 对象，接着该对象提供 **CreateNavigator** 方法，用于创建位于表单的基础 XML 文档（主数据源）的根节点处的 **XPathNavigator** 对象。</span><span class="sxs-lookup"><span data-stu-id="2a1df-212">[MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) property, which returns a **DataSource** object that in turn provides the **CreateNavigator** method for creating an **XPathNavigator** object positioned at the root of the form's underlying XML document (main data source).</span></span>  <br/> |
||<span data-ttu-id="2a1df-213">[MergeForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MergeForm.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-213">[MergeForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MergeForm.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-214">XmlFormCollection</span><span class="sxs-lookup"><span data-stu-id="2a1df-214">XmlFormCollection</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.aspx) <br/> |<span data-ttu-id="2a1df-215">[NewFromFormTemplate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.NewFromFormTemplate.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-215">[NewFromFormTemplate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCollection.NewFromFormTemplate.aspx) method</span></span>  <br/> |
|[<span data-ttu-id="2a1df-216">XmlValidatingEventArgs</span><span class="sxs-lookup"><span data-stu-id="2a1df-216">XmlValidatingEventArgs</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.aspx) <br/> |<span data-ttu-id="2a1df-217">[ReportError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.ReportError.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-217">[ReportError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.ReportError.aspx) methods</span></span>  <br/> |
   
<span data-ttu-id="2a1df-218">除了返回或接受 **XPathNavigator** 对象的 InfoPath 对象模型成员外，以下方法返回 **System.Xml.XPath** 命名空间的 **XPathNodeIterator** 类的实例，用来迭代在视图中指定或选择的项的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="2a1df-218">In addition to the InfoPath object model members that return or accept an **XPathNavigator** object, the following methods return an instance of the **XPathNodeIterator** class of the **System.Xml.XPath** namespace for iterating over the XML nodes of items that are specified or selected in a view.</span></span> 
  
|<span data-ttu-id="2a1df-219">**父类**</span><span class="sxs-lookup"><span data-stu-id="2a1df-219">**Parent Class**</span></span>|<span data-ttu-id="2a1df-220">**成员**</span><span class="sxs-lookup"><span data-stu-id="2a1df-220">**Member**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2a1df-221">View</span><span class="sxs-lookup"><span data-stu-id="2a1df-221">View</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) <br/> |<span data-ttu-id="2a1df-222">[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-222">[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) methods</span></span>  <br/> |
||<span data-ttu-id="2a1df-223">[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetSelectedNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2a1df-223">[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetSelectedNodes.aspx) method</span></span>  <br/> |
   
## <a name="using-the-xpathnavigator-and-xpathnodeiterator-classes-to-work-with-data-selected-in-a-view"></a><span data-ttu-id="2a1df-224">使用 XPathNavigator 和 XPathNodeIterator 类处理在视图中选择的数据</span><span class="sxs-lookup"><span data-stu-id="2a1df-224">Using the XPathNavigator and XPathNodeIterator Classes to Work with Data Selected in a View</span></span>
<span data-ttu-id="2a1df-225"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a1df-225"><a name="InfoPath2007XPathNavigatorClassFormTemplates_SelectingXMLNodes"> </a></span></span>

<span data-ttu-id="2a1df-226">下面的示例使用 **XPathNavigator** 和 **XPathNodeIterator** 类的成员按照以下顺序处理表单数据：</span><span class="sxs-lookup"><span data-stu-id="2a1df-226">The following example uses members of both the **XPathNavigator** and **XPathNodeIterator** classes to work with form data in the following sequence:</span></span> 
  
1. <span data-ttu-id="2a1df-227">使用 **DataSource** 类的 **CreateNavigator** 方法创建一个名为 repeatingTableRow1 的 **XPathNavigator** 对象变量，默认情况下该对象变量位于表单的基础 XML 文档（主数据源）的根节点处。</span><span class="sxs-lookup"><span data-stu-id="2a1df-227">The **CreateNavigator** method of the **DataSource** class is used to create an **XPathNavigator** object variable named repeatingTableRow1, which by default is positioned at the root of the underlying XML document of the form (the main data source).</span></span>
    
2. <span data-ttu-id="2a1df-228">使用 **XPathNavigator** 类的 **SelectSingleNode** 方法将 **XPathNavigator** 对象的位置移到“重复表”\*\*\*\* 控件的第一行，该控件绑定到数据源中的 group2。</span><span class="sxs-lookup"><span data-stu-id="2a1df-228">The **SelectSingleNode** method of the **XPathNavigator** class is used to move the position of the **XPathNavigator** object to the first row of a **Repeating Table** control bound to group2 in the data source.</span></span> 
    
3. <span data-ttu-id="2a1df-229">将 repeatingTableRow1 对象变量传递到 **View** 类的 **SelectNodes** 方法，以选择该行中的节点。</span><span class="sxs-lookup"><span data-stu-id="2a1df-229">The repeatingTableRow1 object variable is passed to the **SelectNodes** method of the **View** class to select the nodes in that row.</span></span> 
    
4. <span data-ttu-id="2a1df-230">声明一个名为 selectedNodes 的 **XPathNodeIterator** 对象变量，并使用 **View** 类的 **GetSelectedNodes** 方法用所选的节点填充 **XPathNodeIterator** 对象。</span><span class="sxs-lookup"><span data-stu-id="2a1df-230">An **XPathNodeIterator** object variable named selectedNodes is declared and the **GetSelectedNodes** method of the **View** class is used populate the **XPathNodeIterator** object with the selected nodes.</span></span> 
    
5. <span data-ttu-id="2a1df-231">使用 **XPathNodeIterator** 类的 **Count** 属性显示包含在 selectedNodes 对象变量中的节点数。</span><span class="sxs-lookup"><span data-stu-id="2a1df-231">The **Count** property of the **XPathNodeIterator** class is used to display the number of nodes contained in the selectedNodes object variable.</span></span> 
    
6. <span data-ttu-id="2a1df-232">使用 For/Each 循环迭代 selectedNodes 对象变量中的节点，并使用 **XPathNavigator** 类的 **Name**、 **InnerXml** 和 **Value** 属性显示有关每个节点的信息。</span><span class="sxs-lookup"><span data-stu-id="2a1df-232">A For/Each loop is used to iterate over the nodes in the selectedNodes object variable and display information about each node using the **Name**, **InnerXml**, and **Value** properties of the **XPathNavigator** class.</span></span> 
    
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

<span data-ttu-id="2a1df-233">有关如何处理 InfoPath 表单模板中的 XML 数据的详细信息，请参阅使用 InfoPath 2007 表单模板中的 XPathNavigator 类处理 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="2a1df-233">For more information about how to work with XML data from InfoPath form templates, see Working with XML Data Using the XPathNavigator Class in InfoPath 2007 Form Templates.</span></span>
  

