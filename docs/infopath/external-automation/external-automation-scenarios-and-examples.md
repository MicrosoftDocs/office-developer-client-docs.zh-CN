---
title: 外部自动化方案和示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- 自动执行 infopath 2007 表单 [InfoPath 2007]，以编程方式添加数据、 自动化 [InfoPath 2007]、 外部方案
localization_priority: Normal
ms.assetid: dfa880e6-de23-41c4-b80b-6935e0c8563d
description: Microsoft Office InfoPath 主互操作程序集 (Microsoft.Office.Interop.InfoPath.dll) 和 InfoPath XML 互操作程序集 (Microsoft.Office.Interop.InfoPath.Xml.dll) 用于自动执行支持编写托管代码提供的成员InfoPath。
ms.openlocfilehash: af8bfbb0322b9d70fb85ba21a757a581ba423a44
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383161"
---
# <a name="external-automation-scenarios-and-examples"></a>外部自动化方案和示例

Microsoft Office InfoPath 主互操作程序集 (Microsoft.Office.Interop.InfoPath.dll) 和 InfoPath XML 互操作程序集 (Microsoft.Office.Interop.InfoPath.Xml.dll) 用于自动执行支持编写托管代码提供的成员InfoPath。 
  
## <a name="establishing-references-to-the-microsoft-office-infopath-primary-interop-and-infopath-xml-interop-assemblies"></a>建立对 Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集参考

若要编写用于自动执行 InfoPath 托管的代码，必须建立对 Microsoft InfoPath 主互操作和 InfoPath XML 互操作程序集的引用。 Microsoft InfoPath 主互操作程序集提供与 COM 对象模型公开 IPEDITOR 互操作性支持。通过使用[Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx)命名空间的成员的 DLL。 InfoPath XML 互操作程序集提供支持的互操作性与 COM 对象模型公开由 Microsoft XML Core Services (MSXML) 使用[Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml)命名空间的成员。 
  
> [!IMPORTANT]
> 自动执行 InfoPath 托管代码应用程序的用户必须具有 InfoPath、 Microsoft Office InfoPath 主互操作程序集和 InfoPath XML 互操作程序集安装在其计算机上。 InfoPath 的典型安装的情况下，InfoPath 安装程序中的 **.NET 可编程性支持**选项设置为**从本机运行**。
>  
> 因此，如已安装长为.NET Framework 1.1 版可再发行组件或.NET Framework 1.1 软件开发工具包 (SDK) 或更高版本，将也默认情况下安装这些互操作程序集。 如果这些互操作程序集不在用户的计算机上可用，您必须确认.NET Framework 1.1 或更高版本是安装，然后从**控制面板**以更改安装程序并设置 **.NET 可编程性运行**程序和功能**支持**到**从本机运行**的 InfoPath 的选项。 
  
以下过程介绍如何设置 Visual Studio 项目中的 Microsoft Office InfoPath 主互操作和 InfoPath XML 引用互操作程序集。
  
若要设置对 Microsoft.Office.Interop.InfoPath 主互操作程序集的引用，请将在**添加引用**对话框的**COM**选项卡上设置对**Microsoft InfoPath 3.0 类型库**的引用。 即使设置从**COM**选项卡的引用，请参考对 Microsoft.Office.Interop.InfoPath.dll 主互操作程序集由 InfoPath 安装程序安装在全局程序集缓存 (GAC) 中的建立。 
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopath-primary-interop-assembly"></a>设置对 Microsoft.Office.Interop.InfoPath 主互操作程序集的引用

1. 打开 Visual Studio 托管的代码项目。
    
2. 在**解决方案资源管理器**中，右键单击**引用**，，然后单击**添加引用**。
    
3. **COM**选项卡中，双击**Microsoft InfoPath 3.0 类型库**中，，然后单击**确定**。
    
要设置对 Microsoft.Office.Interop.InfoPath.Xml 互操作程序集的引用，请浏览到 <_驱动器_> 中默认情况下安装的 Microsoft.Office.Interop.InfoPath.Xml.dll 文件： \Program Files\Microsoft Office\OFFICE14 文件夹. 即使本地文件系统中指定的程序集的副本，此过程将建立对由 InfoPath 安装程序安装在全局程序集缓存 (GAC) 中的 Microsoft.Office.Interop.InfoPath.Xml.dll 程序集的引用。
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopathxml-interop-assembly"></a>设置对 Microsoft.Office.Interop.InfoPath.Xml 互操作程序集的引用

1. 打开或创建 Visual Studio 托管的代码项目，如**控制台应用程序**或**Windows 应用程序**。
    
2. 在**解决方案资源管理器**中，右键单击**引用**，，然后单击**添加引用**。
    
3. 在 **.NET**选项卡上，单击**浏览**，导航到 <_驱动器_>: \Program Files\Microsoft Office\OFFICE14 文件夹，然后单击 Microsoft.Office.Interop.InfoPath.Xml.dll。
    
4. 单击“确定”****。
    
## <a name="automate-changing-the-value-of-a-field"></a>自动更改字段的值

假定一个 InfoPath 销售报表表单模板的用户的客户最近更改"公司 A"到"公司 B"其名称 开发人员需要编写将自动更新从此表单模板，以反映名称的更改保存的销售报告表单的代码。 以下方案假定窗体包含一个文本框绑定到名为 customerName 的字段。
  
### <a name="create-the-sample-form-template-and-form"></a>创建示例表单模板和表单

1. 打开 InfoPath 并创建一个空白表单模板。
    
2. 将**文本框**控件添加到窗体，并命名绑定到控件 customerName 的域。
    
3. 在**字段**任务窗格中，右键单击**myFields**文件夹，然后单击**属性**。
    
4. 在**详细信息**选项卡上，选择并复制值以下**Namespace:**，然后将此粘贴到记事本或其他一些您可以检索的位置。 在代码中设置**SelectionNamespaces**属性的值，将稍后需要此值。 
    
5. 将表单模板发布到一个名为 C:\Test 文件夹并接受默认名称，Template1。 
    
6. 打开表单模板，添加"公司 A"到文本框绑定到 customerName 字段的名称，然后保存作为"Form1"窗体。 
    
### <a name="create-a-managed-code-console-application-to-change-the-name-from-company-a-to-company-b"></a>为公司 B' 创建托管的代码控制台应用程序，以更改公司 A 的名称

1. 打开 Visual Studio 并创建新 Visual C# 或 Visual Basic 名为 UpdateCustomer 的控制台应用程序。
    
2. 建立对 Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集的引用，如上文所述。
    
3. 将以下代码添加到 Program.cs 或 Module1.vb 文件，并确保复制创建示例表单时的值更新的命名空间中**SelectionNamespaces**属性的设置的值。 
    
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
    "xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'");
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
    "xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'")
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

4. 编译并运行控制台应用程序**调试**菜单上，单击**开始调试**。 
    
   应用程序打开该窗体保存为 Form1.xml 和循环访问包含公司 A 值的所有 customerName 元素，该值更改为公司 B完成该操作时，窗体的新副本另存为 Form2.xml C:\Test 文件夹中。 
    
## <a name="automate-opening-a-form-and-populating-field-values"></a>自动化打开窗体和填充字段值

以下示例将自动打开一个空白窗体并填充的名字、 姓氏和窗体中的地址字段。 此方案假定窗体包含三个文本框绑定到名为 FirstName、 LastName 和地址的域。
  
### <a name="create-the-sample-form-template-and-form"></a>创建示例表单模板和表单

1. 打开 InfoPath 并创建一个空白窗体。
    
2. 添加三个文本框控件的窗体，并命名字段绑定到控件： FirstName、 LastName 和地址。 添加所需的任何其他字段。
    
3. 在**字段**任务窗格中，右键单击**myFields**文件夹，然后单击**属性**。
    
4. 在**详细信息**选项卡上，选择并复制值以下**Namespace:**，然后将此粘贴到记事本或其他一些您可以检索的位置。 在代码中设置**SelectionNamespaces**属性的值，将稍后需要此值。 
    
5. 将表单模板发布到一个名为 C:\Temp 文件夹并接受默认名称，Template1。
    
6. 打开表单模板并将空白窗体另存为"Form1"为 C:\Temp。
    
### <a name="create-a-managed-code-console-application-to-open-the-form-and-populate-the-fields"></a>创建托管的代码控制台应用程序，以打开表单并填充的字段

1. 打开 Visual Studio 并创建新 Visual C# 或 Visual Basic 名为 OpenForm 的控制台应用程序。
    
2. 建立对 Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集的引用，如上文所述。
    
3. 将以下代码添加到 Program.cs 或 Module1.vb 文件，并确保复制创建示例表单时的值更新的命名空间中**SelectionNamespaces**属性的设置的值。 
    
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
            doc.setProperty("SelectionNamespaces","xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'");
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
          doc.setProperty("SelectionNamespaces", "xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2006-09-06T23:17:34'")
          ' Pre-populate the fields with specified values.
          doc.selectSingleNode("//my:FirstName").text = "My Name"
          doc.selectSingleNode("//my:LastName").text = "My LastName"
          doc.selectSingleNode("//my:Address").text = "My Address"
          ' Save the form, leaving InfoPath open.
          myXDoc.Save()
      End Sub
    End Module
    
   ```

4. 在**调试**菜单上，单击**启动调试**编译并运行控制台应用程序。 
    
   应用程序将打开窗体另存为 Form1.xml 和 FirstName、 LastName 和地址字段中填入在代码中，指定的值，然后保存表单，使 InfoPath 保持打开状态。 
    
## <a name="see-also"></a>另请参阅

- [关于 Microsoft Office InfoPath 主互操作程序集](about-the-microsoft-office-infopath-primary-interop-assembly.md)
- [关于 InfoPath XML 互操作程序集](about-the-infopath-xml-interop-assembly.md)

