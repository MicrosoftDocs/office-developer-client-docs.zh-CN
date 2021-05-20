---
title: 外部自动化方案和示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- 自动化 infopath 2007，forms [InfoPath 2007]，以编程方式添加数据，自动化 [InfoPath 2007]，外部方案
localization_priority: Normal
ms.assetid: dfa880e6-de23-41c4-b80b-6935e0c8563d
description: InfoPath 主互操作程序集 Microsoft Office 和 InfoPath XML 互操作程序集 (Microsoft.Office.Interop.InfoPath.dll) 这些成员 (Microsoft.Office.Interop.InfoPath.Xml.dll) 编写用于自动执行 InfoPath 的托管代码。
ms.openlocfilehash: 79fbc56033ffce639b5007874dabf56e8e286edb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537813"
---
# <a name="external-automation-scenarios-and-examples"></a>外部自动化方案和示例

InfoPath 主互操作程序集 Microsoft Office 和 InfoPath XML 互操作程序集 (Microsoft.Office.Interop.InfoPath.dll) 这些成员 (Microsoft.Office.Interop.InfoPath.Xml.dll) 编写用于自动执行 InfoPath 的托管代码。 
  
## <a name="establishing-references-to-the-microsoft-office-infopath-primary-interop-and-infopath-xml-interop-assemblies"></a>建立对 InfoPath 主互Microsoft Office InfoPath XML 互操作程序集的引用

若要编写用于自动执行 InfoPath 的托管代码，必须建立对 Microsoft InfoPath 主互操作和 InfoPath XML 互操作程序集的引用。 Microsoft InfoPath 主互操作程序集通过使用[Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx)命名空间的成员来支持与 IPEDITOR.DLL 公开的 COM 对象模型的互操作性。 InfoPath XML 互操作程序集通过使用Microsoft.Office.Interop.InfoPath.Xml命名空间的成员来支持与由 Microsoft XML Core Services (MSXML)  (MSXML) 公开的 COM 对象[模型的](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml)互操作性。 
  
> [!IMPORTANT]
> 自动化 InfoPath 的托管代码应用程序的用户必须在其计算机上安装 InfoPath、Microsoft Office InfoPath 主互操作程序集和 InfoPath XML 互操作程序集。 InfoPath **安装程序中的 .NET 可编程** 性支持选项设置为"从我的计算机运行 **"，以** 执行 InfoPath 的典型安装。
>  
> 因此，只要安装了 .NET Framework 1.1 可再发行软件包或 .NET Framework 1.1 软件开发工具包 (SDK) 或更高版本，就会默认安装这些互操作程序集。 如果这些互操作程序集在用户计算机上不可用，则必须确认已安装 .NET Framework 1.1 或更高版本，然后从控制面板运行"程序和功能"以更改安装程序，然后将InfoPath 的 **.NET 可编程** 性支持选项设置为"从我的计算机运行 **"。** 
  
以下过程介绍如何设置对项目Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集Visual Studio引用。
  
设置对 Microsoft 的引用。Office.Interop.InfoPath 主互操作程序集，在"添加引用"对话框的 **"COM"** 选项卡上设置对 **Microsoft InfoPath 3.0** 类型库的引用。  即使您从 **"COM"** 选项卡设置引用，也建立了对由 InfoPath 安装程序安装在全局程序集缓存 (GAC) 中的 Microsoft.Office.Interop.InfoPath.dll 主互操作程序集的引用。 
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopath-primary-interop-assembly"></a>设置对 Microsoft 的引用。Office.Interop.InfoPath 主互操作程序集

1. 打开一Visual Studio托管代码项目。
    
2. 在“解决方案资源管理器”中，右键单击“引用”，然后单击“添加引用”。
    
3. 在 **"COM"** 选项卡上，双击 **"Microsoft InfoPath 3.0 类型库"，** 然后单击"确定 **"。**
    
若要设置对 Microsoft.Office.Interop.InfoPath.Xml 互操作程序集的引用，请浏览到默认情况下安装在 <_驱动器_>：\Program Files\Microsoft Office\OFFICE14 文件夹中的 Microsoft.Office.Interop.InfoPath.Xml.dll 文件。 即使在本地文件系统中指定程序集的副本，此过程也建立了对 InfoPath 安装程序在全局程序集缓存 (GAC) 中安装的 Microsoft.Office.Interop.InfoPath.Xml.dll 程序集的引用。
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopathxml-interop-assembly"></a>设置对互操作Microsoft.Office.Interop.InfoPath.Xml的引用

1. 打开或创建Visual Studio代码项目，如控制台 **应用程序或Windows****应用程序**。
    
2. 在“解决方案资源管理器”中，右键单击“引用”，然后单击“添加引用”。
    
3. 在 **".NET"** 选项卡上，单击"浏览"，导航到 <_驱动器_>：\Program Files\Microsoft Office\OFFICE14 文件夹，然后单击"Microsoft.Office.Interop.InfoPath.Xml.dll"。
    
4. 单击“**确定**”。
    
## <a name="automate-changing-the-value-of-a-field"></a>自动更改字段值

假设 InfoPath 销售报表用户的一表单模板最近将公司名称从"公司 A"更改为"公司 B"。 要求开发人员编写代码，以自动更新从该表单保存的销售报表表单模板以反映名称更改。 以下方案假定表单包含绑定到名为 customerName 的字段的文本框。
  
### <a name="create-the-sample-form-template-and-form"></a>创建示例表单模板表单

1. 打开 InfoPath 并创建一个空白表单模板。
    
2. 向 **窗体中添加一** 个文本框控件，并命名绑定到控件 customerName 的字段。
    
3. 在"**字段**"任务窗格中，右键单击 **"myFields"** 文件夹，然后单击"属性 **"。**
    
4. 在"**详细信息**"选项卡上，选择并复制以下 **Namespace：** 值，然后将其粘贴到记事本或其他可以检索它的位置。 稍后将需要此值来设置代码中 **SelectionNamespaces** 属性的值。 
    
5. 将表单模板到名为 C：\Test 的文件夹并接受默认名称 Template1。 
    
6. 打开表单模板，将名称"Company A"添加到绑定到 customerName 字段的文本框中，然后将表单另存为"Form1"。 
    
### <a name="create-a-managed-code-console-application-to-change-the-name-from-company-a-to-company-b"></a>创建托管代码控制台应用程序以将名称从"Company A"更改为"Company B"

1. 打开Visual Studio，然后新建一个名为 UpdateCustomer C#或Visual Basic控制台应用程序。
    
2. 建立对 InfoPath Microsoft Office互操作和 InfoPath XML 互操作程序集的引用，如上所述。
    
3. 将以下代码添加到 Program.cs 或 Module1.vb 文件中，确保使用创建示例表单时复制的值更新 **SelectionNamespaces** 属性设置中的命名空间值。 
    
   ```cs
    using System;
    using System.Collections.Generic;
    using System.Text;
    using Microsoft.Office.Interop.InfoPath;
    using Microsoft.Office.Interop.InfoPath.Xml;
    namespace UpdateCustomer
    {
      class Program
      {
          static void Main(string[] args)
          {
            // Create an InfoPath Application object.
            Application myApp = 
                new Microsoft.Office.Interop.InfoPath.Application();
            // Get a reference the XDocuments collection 
            // and open the sample form.
            XDocumentsCollection myXDocs = myApp.XDocuments;
            XDocument myXDoc = myXDocs.Open("C:\\Test\\Form1.xml",
                (int) XdDocumentVersionMode.xdFailOnVersionOlder);
            
            // Access the XML DOM for the underlying XML document using
            // the DOM property. Note that you must cast to the 
            // IXMLDOMDocument2 type from the
            // Microsoft.Office.Interop.InfoPath.Xml namespace
            // to access the XML DOM.
            IXMLDOMDocument2 myXMLDoc = myXDoc.DOM as IXMLDOMDocument2;
            // Set the MSXML SelectionNamespaces property to the my
            // namespace of the form. IMPORTANT:Replace the namespace 
            // value below with that of your sample form.
            myXMLDoc.setProperty("SelectionNamespaces",
    "xmlns:my='http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'");
            // Select all instances of customerName that contain 
            //'Company A'.
            IXMLDOMNodeList myNames = 
                myXMLDoc.selectNodes(
                "//my:customerName[. = 'Company A']");
            // Check to determine if any nodes were returned.
            if (myNames.length < 1)
            Console.WriteLine(
                "No elements containing 'Company A' were found.");
            // Loop through the list updating to 'Company B'.
            IXMLDOMNode myName = myNames.nextNode();
            while (myName != null)
            {
                myName.text = "Company B";
                myName = myNames.nextNode();
            }
            // Save the updated form as Form2.xml and close out.
            myXDoc.SaveAs("C:\\Test\\Form2.xml");
            myXDocs.Close(0);
            myApp.Quit(false);
            Console.WriteLine("Finished!");
          }
      }
    }
   ```

   ```vb
    Imports Microsoft.Office.Interop.InfoPath
    Imports Microsoft.Office.Interop.InfoPath.Xml
    Module Module1
      Sub Main()
          ' Create an InfoPath Application object.
          Dim myApp As Application = _
            New Microsoft.Office.Interop.InfoPath.Application()
          ' Get a reference the XDocuments collection 
          ' and open the sample form.
          Dim myXDocs As XDocumentsCollection = myApp.XDocuments
          Dim myXDoc As XDocument = myXDocs.Open( _
            "C:\\Test\\Form1.xml", _
            XdDocumentVersionMode.xdFailOnVersionOlder)
          ' Access the XML DOM for the underlying XML document using
          ' the DOM property. Note that you must cast to the 
          ' IXMLDOMDocument2 type from the
          ' Microsoft.Office.Interop.InfoPath.Xml namespace
          ' to access the XML DOM.
          Dim myXMLDoc As IXMLDOMDocument2 = _
            DirectCast(myXDoc.DOM, IXMLDOMDocument2)
          ' Set the MSXML SelectionNamespaces property to the my
          ' namespace of the form. IMPORTANT:Replace the namespace 
          ' value below with that of your sample form.
          myXMLDoc.setProperty("SelectionNamespaces", _
    "xmlns:my='http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'")
          ' Select all instances of customerName that contain 
          ''Company A'.
          Dim myNames As IXMLDOMNodeList = _
      myXMLDoc.selectNodes("//my:customerName[. = 'Company A']")
          ' Check to determine if any nodes were returned.
          If (myNames.length < 1) Then
            Console.WriteLine( _
                "No elements containing 'Company A' were found.")
          Else
            ' Loop through the list updating to 'Company B'.
            Dim myName As IXMLDOMNode = myNames.nextNode()
            While (myName IsNot Nothing)
                myName.text = "Company B"
                myName = myNames.nextNode()
            End While
          End If
          ' Save the updated form as Form2.xml and close out.
          myXDoc.SaveAs("C:\\Test\\Form2.xml")
          myXDocs.Close(0)
          myApp.Quit(False)
          Console.WriteLine("Finished!")
      End Sub
    End Module
    
   ```

4. 单击 **"调试"菜单** 上的"开始调试"以编译并运行控制台应用程序。 
    
   应用程序打开另存为Form1.xml并循环访问包含值 Company A 的所有 customerName 元素，将该值更改为公司 B。操作完成后，表单的新副本将另存为Form2.xml C：\Test 文件夹中。 
    
## <a name="automate-opening-a-form-and-populating-field-values"></a>自动打开表单并填充字段值

下面的示例自动打开一个空白窗体，并填充窗体中的名字、姓氏和地址字段。 此方案假定窗体包含三个文本框，这些文本框绑定到名为 FirstName、LastName 和 Address 的字段。
  
### <a name="create-the-sample-form-template-and-form"></a>创建示例表单模板表单

1. 打开 InfoPath 并创建一个空白表单。
    
2. 向窗体中添加三个文本框控件，并命名绑定到控件的字段：FirstName、LastName 和 Address。 添加任何其他需要的字段。
    
3. 在"**字段**"任务窗格中，右键单击 **"myFields"** 文件夹，然后单击"属性 **"。**
    
4. 在"**详细信息**"选项卡上，选择并复制以下 **Namespace：** 值，然后将其粘贴到记事本或其他可以检索它的位置。 稍后将需要此值来设置代码中 **SelectionNamespaces** 属性的值。 
    
5. 将表单模板 C：\Temp 的文件夹，并接受默认名称 Template1。
    
6. 打开表单模板，将空白表单另存为"Form1"至 C：\Temp。
    
### <a name="create-a-managed-code-console-application-to-open-the-form-and-populate-the-fields"></a>创建托管代码控制台应用程序以打开表单并填充字段

1. 打开Visual Studio，然后新建一个名为 OpenForm C#或Visual Basic控制台应用程序。
    
2. 建立对 InfoPath Microsoft Office互操作和 InfoPath XML 互操作程序集的引用，如上所述。
    
3. 将以下代码添加到 Program.cs 或 Module1.vb 文件中，确保使用创建示例表单时复制的值更新 **SelectionNamespaces** 属性设置中的命名空间值。 
    
   ```cs
    using System;
    using System.Collections.Generic;
    using System.Text;
    using Microsoft.Office.Interop.InfoPath;
    using Microsoft.Office.Interop.InfoPath.Xml;
    namespace OpenForm
    {
      class Program
      {
          static void Main(string[] args)
          {
            // Create an InfoPath Application object.
            Application myApp=
                new Microsoft.Office.Interop.InfoPath.Application();
            // Create an InfoPath XDocument variable and open 
            // the blank form.
            XDocument myXDoc = myApp.XDocuments.Open(
                "c:\\temp\\Form1.xml",
                (int) XdDocumentVersionMode.xdFailOnVersionOlder);
            
            // Create an IXMLDOMDocument2 variable and access 
            // the XML DOM from the underlying XML document
            // using the DOM property of the XDocument object. 
            // Note that you must cast to IXMLDOMDocument2 to do so.
            IXMLDOMDocument2 doc= myXDoc.DOM as IXMLDOMDocument2;
            // Set the MSXML SelectionNamespaces property to the my
            // namespace of the form. IMPORTANT:Replace the namespace
            // value below with that of your sample form.
            doc.setProperty("SelectionNamespaces","xmlns:my='http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'");
            // Pre-populate the fields with specified values.
            doc.selectSingleNode("//my:FirstName").text="My Name";
            doc.selectSingleNode("//my:LastName").text="My LastName";
            doc.selectSingleNode("//my:Address").text="My Address";
            // Save the form, leaving InfoPath open.
            myXDoc.Save();
            
          }
      }
    }
   ```

   ```vb
    Imports Microsoft.Office.Interop.InfoPath
    Imports Microsoft.Office.Interop.InfoPath.Xml
    Module Module1
      Sub Main()
          ' Create an InfoPath Application object.
          Dim myApp As Application = _
            New Microsoft.Office.Interop.InfoPath.Application
          ' Create an InfoPath XDocument variable and open 
          ' the blank form.
          Dim myXDoc As XDocument = myApp.XDocuments.Open( _
            "c:\\temp\\Form1.xml", _
            XdDocumentVersionMode.xdFailOnVersionOlder)
          ' Create an IXMLDOMDocument2 variable and access 
          ' the XML DOM from the underlying XML document
          ' using the DOM property of the XDocument object.
          Dim doc As IXMLDOMDocument2 = myXDoc.DOM
          ' Set the MSXML SelectionNamespaces property to the my
          ' namespace of the form. IMPORTANT:Replace the namespace
          ' value below with that of your sample form.
          doc.setProperty("SelectionNamespaces", "xmlns:my='http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'")
          ' Pre-populate the fields with specified values.
          doc.selectSingleNode("//my:FirstName").text = "My Name"
          doc.selectSingleNode("//my:LastName").text = "My LastName"
          doc.selectSingleNode("//my:Address").text = "My Address"
          ' Save the form, leaving InfoPath open.
          myXDoc.Save()
      End Sub
    End Module
    
   ```

4. 在" **调试"** 菜单上，单击" **启动调试"** 以编译并运行控制台应用程序。 
    
   应用程序将打开另存为 Form1.xml，然后使用代码中指定的值填充 FirstName、LastName 和 Address 字段，然后保存表单，使 InfoPath 保留打开状态。 
    
## <a name="see-also"></a>另请参阅

- [关于 Microsoft Office InfoPath 主互操作程序集](about-the-microsoft-office-infopath-primary-interop-assembly.md)
- [关于 InfoPath XML 互操作程序集](about-the-infopath-xml-interop-assembly.md)

