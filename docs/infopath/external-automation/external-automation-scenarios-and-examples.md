---
title: 外部自动化方案和示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- 自动化 infopath 2007, 表单 [infopath 2007], 以编程方式添加数据, 自动化 [infopath 2007], 外部方案
localization_priority: Normal
ms.assetid: dfa880e6-de23-41c4-b80b-6935e0c8563d
description: Microsoft Office InfoPath 主互操作程序集 (如 "microsoft. .dll") 和 infopath XML 互操作程序集 ("microsoft. web.xml") 提供的成员支持编写托管代码以实现自动化InfoPath.
ms.openlocfilehash: af8bfbb0322b9d70fb85ba21a757a581ba423a44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310197"
---
# <a name="external-automation-scenarios-and-examples"></a>外部自动化方案和示例

Microsoft Office InfoPath 主互操作程序集 (如 "microsoft. .dll") 和 infopath XML 互操作程序集 ("microsoft. web.xml") 提供的成员支持编写托管代码以实现自动化InfoPath. 
  
## <a name="establishing-references-to-the-microsoft-office-infopath-primary-interop-and-infopath-xml-interop-assemblies"></a>建立对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用

若要编写托管代码以自动化 InfoPath, 您必须建立对 Microsoft InfoPath 主互操作和 infopath XML 互操作程序集的引用。 Microsoft InfoPath 主互操作程序集为与 IPEDITOR 公开的 COM 对象模型的互操作性提供支持。DLL 命名空间的成员使用的[](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx) DLL。 infopath XML 互操作程序集支持与通过 microsoft XML Core Services (MSXML) 公开的 COM 对象模型的互操作性, 具体方法是使用[microsoft](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml) xml Core Services (MSXML) 命名空间的成员。 
  
> [!IMPORTANT]
> 自动化 infopath 的托管代码应用程序的用户必须在其计算机上安装 infopath、Microsoft Office InfoPath 主互操作程序集和 infopath XML 互操作程序集。 infopath 安装程序中的 " **.net 可编程性支持**" 选项设置为 "**从本机运行**", 以便安装 infopath 的典型安装。
>  
> 因此, 只要安装了 .net framework 1.1 可再发行版或 .net framework 1.1 软件开发工具包 (SDK) 或更高版本, 默认情况下也会安装这些互操作程序集。 如果这些互操作程序集在用户计算机上不可用, 则必须确认已安装 .net Framework 1.1 或更高版本, 然后运行 "**控制面板**" 中的 "**程序和功能**" 更改安装程序并设置 **.net 可编程性****从 "我的电脑" 运行**的 InfoPath 支持选项。 
  
以下过程介绍如何在 Visual Studio 项目中设置对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用。
  
若要设置对 microsoft infopath 的主互操作程序集的引用, 请在 "**添加引用**" 对话框的 " **COM** " 选项卡上设置对**microsoft InfoPath 3.0 类型库**的引用。 即使您从 " **COM** " 选项卡中设置了引用, 也会为 infopath 安装程序在全局程序集缓存 (GAC) 中安装的 Microsoft. .dll 主互操作程序集建立一个引用。 
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopath-primary-interop-assembly"></a>设置对 Microsoft. InfoPath 主互操作程序集的引用

1. 打开 Visual Studio 托管代码项目。
    
2. 在“解决方案资源管理器”**** 中，右键单击“引用”****，然后单击“添加引用”****。
    
3. 在 " **COM** " 选项卡上, 双击 " **Microsoft InfoPath 3.0 类型库**", 然后单击 **"确定"**。
    
若要设置对 microsoft. xml 互操作程序集的引用, 请浏览到默认情况下在 < _drive_>: \Program Files\Microsoft Office\OFFICE14 文件夹中安装的 Microsoft. .xml .dll 文件。. 即使您在本地文件系统中指定了程序集的副本, 此过程也会建立对 infopath 安装程序安装在全局程序集缓存 (GAC) 中的 Microsoft. .xml .dll 程序集的引用。
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopathxml-interop-assembly"></a>设置对 Microsoft. web.xml 互操作程序集的引用

1. 打开或创建一个 Visual Studio 托管代码项目, 如**控制台应用程序**或**Windows 应用程序**。
    
2. 在“解决方案资源管理器”**** 中，右键单击“引用”****，然后单击“添加引用”****。
    
3. 在 " **.net** " 选项卡上, 单击 "**浏览**", 导航到 < _drive_>: \Program Files\Microsoft Office\OFFICE14 文件夹, 然后单击 ""。
    
4. 单击“**确定**”。
    
## <a name="automate-changing-the-value-of-a-field"></a>自动更改字段的值

假设 InfoPath sales report 表单模板的用户之一的客户最近将其名称从 "company A" 更改为 "company B"。 要求开发人员编写代码, 以自动更新从该表单模板保存的销售报告表单, 以反映名称的变化。 下面的方案假定表单中包含一个绑定到名为 customerName 的字段的文本框。
  
### <a name="create-the-sample-form-template-and-form"></a>创建示例表单模板和表单

1. 打开 InfoPath 并创建一个空白表单模板。
    
2. 将 "**文本框**" 控件添加到窗体中, 并将绑定到控件 customerName 的字段命名。
    
3. 在 "**域**" 任务窗格中, 右键单击 " **myFields** " 文件夹, 然后单击 "**属性**"。
    
4. 在 "**详细信息**" 选项卡上, 选择并复制**命名空间**后面的值:, 然后将其粘贴到记事本或其他可在其中进行检索的位置。 稍后将需要此值, 以便在代码中设置**SelectionNamespaces**属性的值。 
    
5. 将表单模板发布到名为 C:\Test 的文件夹, 并接受默认名称 Template1。 
    
6. 打开表单模板, 将名称 "Company A" 添加到绑定到 customerName 域的文本框, 然后将该表单另存为 "Form1"。 
    
### <a name="create-a-managed-code-console-application-to-change-the-name-from-company-a-to-company-b"></a>创建托管代码控制台应用程序以将名称从 "company a" 更改为 "company B"

1. 打开 visual Studio, 创建一个名为 UpdateCustomer 的新 visual c # 或 visual Basic 控制台应用程序。
    
2. 按照上述说明, 建立对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用。
    
3. 将以下代码添加到 Program.cs 或 Module1 文件, 确保使用创建示例表单时复制的值来更新**SelectionNamespaces**属性的设置中的命名空间的值。 
    
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

4. 单击 "**调试**" 菜单上的 "**启动调试**" 以编译并运行控制台应用程序。 
    
   应用程序打开另存为 Form1 的窗体, 并循环访问包含价值公司 A 的所有 customerName 元素, 并将该值更改为 company B。操作完成后, 将表单的新副本保存为 C:\Test 文件夹中的 Form2. xml。 
    
## <a name="automate-opening-a-form-and-populating-field-values"></a>自动打开表单和填充字段值

下面的示例自动打开一个空白窗体, 并在窗体中填充名、姓和地址字段。 此方案假定表单中包含三个文本框, 这些文本框绑定到名为 "名字"、"姓氏" 和 "地址" 的域。
  
### <a name="create-the-sample-form-template-and-form"></a>创建示例表单模板和表单

1. 打开 InfoPath 并创建一个空白表单。
    
2. 向窗体中添加三个文本框控件, 并将绑定到控件的字段命名为: FirstName、LastName 和 Address。 添加所需的任何其他字段。
    
3. 在 "**域**" 任务窗格中, 右键单击 " **myFields** " 文件夹, 然后单击 "**属性**"。
    
4. 在 "**详细信息**" 选项卡上, 选择并复制**命名空间**后面的值:, 然后将其粘贴到记事本或其他可在其中进行检索的位置。 稍后将需要此值, 以便在代码中设置**SelectionNamespaces**属性的值。 
    
5. 将表单模板发布到名为 C:\Temp 的文件夹, 并接受默认名称 Template1。
    
6. 打开表单模板并将空白表单另存为 "Form1" 到 c:\temp。
    
### <a name="create-a-managed-code-console-application-to-open-the-form-and-populate-the-fields"></a>创建托管代码控制台应用程序以打开表单并填充字段

1. 打开 visual Studio, 创建一个新的 visual c # 或 visual Basic 控制台应用程序 (名为 OpenForm)。
    
2. 按照上述说明, 建立对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用。
    
3. 将以下代码添加到 Program.cs 或 Module1 文件, 确保使用创建示例表单时复制的值来更新**SelectionNamespaces**属性的设置中的命名空间的值。 
    
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

4. 在 "**调试**" 菜单上, 单击 "**启动调试**" 以编译并运行控制台应用程序。 
    
   应用程序将打开保存为 Form1 .xml 的表单, 并使用代码中指定的值填充 "名字"、"姓氏" 和 "地址" 字段, 然后保存该表单, 使 InfoPath 保持打开状态。 
    
## <a name="see-also"></a>另请参阅

- [关于 Microsoft Office InfoPath 主互操作程序集](about-the-microsoft-office-infopath-primary-interop-assembly.md)
- [关于 InfoPath XML 互操作程序集](about-the-infopath-xml-interop-assembly.md)

