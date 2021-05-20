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
# <a name="external-automation-scenarios-and-examples"></a><span data-ttu-id="8d439-104">外部自动化方案和示例</span><span class="sxs-lookup"><span data-stu-id="8d439-104">External automation scenarios and examples</span></span>

<span data-ttu-id="8d439-105">InfoPath 主互操作程序集 Microsoft Office 和 InfoPath XML 互操作程序集 (Microsoft.Office.Interop.InfoPath.dll) 这些成员 (Microsoft.Office.Interop.InfoPath.Xml.dll) 编写用于自动执行 InfoPath 的托管代码。</span><span class="sxs-lookup"><span data-stu-id="8d439-105">The members provided by the Microsoft Office InfoPath primary interop assembly (Microsoft.Office.Interop.InfoPath.dll) and the InfoPath XML interop assembly (Microsoft.Office.Interop.InfoPath.Xml.dll) support writing managed code for automating InfoPath.</span></span> 
  
## <a name="establishing-references-to-the-microsoft-office-infopath-primary-interop-and-infopath-xml-interop-assemblies"></a><span data-ttu-id="8d439-106">建立对 InfoPath 主互Microsoft Office InfoPath XML 互操作程序集的引用</span><span class="sxs-lookup"><span data-stu-id="8d439-106">Establishing references to the Microsoft Office InfoPath Primary Interop and InfoPath XML Interop assemblies</span></span>

<span data-ttu-id="8d439-107">若要编写用于自动执行 InfoPath 的托管代码，必须建立对 Microsoft InfoPath 主互操作和 InfoPath XML 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8d439-107">To write managed code for automating InfoPath, you must establish references to the Microsoft InfoPath primary interop and the InfoPath XML interop assemblies.</span></span> <span data-ttu-id="8d439-108">Microsoft InfoPath 主互操作程序集通过使用[Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx)命名空间的成员来支持与 IPEDITOR.DLL 公开的 COM 对象模型的互操作性。</span><span class="sxs-lookup"><span data-stu-id="8d439-108">The Microsoft InfoPath primary interop assembly provides support for interoperability with the COM object model exposed by IPEDITOR.DLL by using the members of the [Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx) namespace.</span></span> <span data-ttu-id="8d439-109">InfoPath XML 互操作程序集通过使用Microsoft.Office.Interop.InfoPath.Xml命名空间的成员来支持与由 Microsoft XML Core Services (MSXML)  (MSXML) 公开的 COM 对象[模型的](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml)互操作性。</span><span class="sxs-lookup"><span data-stu-id="8d439-109">The InfoPath XML interop assembly provides support for interoperability with the COM object model exposed by Microsoft XML Core Services (MSXML) by using the members of the [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml) namespace.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8d439-110">自动化 InfoPath 的托管代码应用程序的用户必须在其计算机上安装 InfoPath、Microsoft Office InfoPath 主互操作程序集和 InfoPath XML 互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="8d439-110">Users of managed-code applications that automate InfoPath must have InfoPath, the Microsoft Office InfoPath primary interop assembly, and the InfoPath XML interop assembly installed on their computers.</span></span> <span data-ttu-id="8d439-111">InfoPath **安装程序中的 .NET 可编程** 性支持选项设置为"从我的计算机运行 **"，以** 执行 InfoPath 的典型安装。</span><span class="sxs-lookup"><span data-stu-id="8d439-111">The **.NET Programmability Support** option in the InfoPath setup program is set to **Run from My Computer** for a typical installation of InfoPath.</span></span>
>  
> <span data-ttu-id="8d439-112">因此，只要安装了 .NET Framework 1.1 可再发行软件包或 .NET Framework 1.1 软件开发工具包 (SDK) 或更高版本，就会默认安装这些互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="8d439-112">As a result, as long as the .NET Framework 1.1 Redistributable or .NET Framework 1.1 Software Development Kit (SDK) or later is installed, these interop assemblies will also be installed by default.</span></span> <span data-ttu-id="8d439-113">如果这些互操作程序集在用户计算机上不可用，则必须确认已安装 .NET Framework 1.1 或更高版本，然后从控制面板运行"程序和功能"以更改安装程序，然后将InfoPath 的 **.NET 可编程** 性支持选项设置为"从我的计算机运行 **"。**</span><span class="sxs-lookup"><span data-stu-id="8d439-113">If these interop assemblies are not available on a user's computer, you must confirm that the .NET Framework 1.1 or later is installed, and then run **Programs and Features** from the **Control Panel** to change setup and set the **.NET Programmability Support** option of InfoPath to **Run from My Computer**.</span></span> 
  
<span data-ttu-id="8d439-114">以下过程介绍如何设置对项目Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集Visual Studio引用。</span><span class="sxs-lookup"><span data-stu-id="8d439-114">The following procedures describe how to set references to the Microsoft Office InfoPath primary interop and the InfoPath XML interop assemblies in a Visual Studio project.</span></span>
  
<span data-ttu-id="8d439-115">设置对 Microsoft 的引用。Office.Interop.InfoPath 主互操作程序集，在"添加引用"对话框的 **"COM"** 选项卡上设置对 **Microsoft InfoPath 3.0** 类型库的引用。 </span><span class="sxs-lookup"><span data-stu-id="8d439-115">To set a reference to the Microsoft.Office.Interop.InfoPath primary interop assembly, set a reference to **Microsoft InfoPath 3.0 Type Library** on the **COM** tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="8d439-116">即使您从 **"COM"** 选项卡设置引用，也建立了对由 InfoPath 安装程序安装在全局程序集缓存 (GAC) 中的 Microsoft.Office.Interop.InfoPath.dll 主互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8d439-116">Even though you set a reference from the **COM** tab, a reference is established to the Microsoft.Office.Interop.InfoPath.dll primary interop assembly that is installed in the Global Assembly Cache (GAC) by the InfoPath setup program.</span></span> 
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopath-primary-interop-assembly"></a><span data-ttu-id="8d439-117">设置对 Microsoft 的引用。Office.Interop.InfoPath 主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="8d439-117">Set a reference to the Microsoft.Office.Interop.InfoPath primary interop assembly</span></span>

1. <span data-ttu-id="8d439-118">打开一Visual Studio托管代码项目。</span><span class="sxs-lookup"><span data-stu-id="8d439-118">Open a Visual Studio managed code project.</span></span>
    
2. <span data-ttu-id="8d439-119">在“解决方案资源管理器”中，右键单击“引用”，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="8d439-119">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>
    
3. <span data-ttu-id="8d439-120">在 **"COM"** 选项卡上，双击 **"Microsoft InfoPath 3.0 类型库"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="8d439-120">On the **COM** tab, double-click **Microsoft InfoPath 3.0 Type Library**, and then click **OK**.</span></span>
    
<span data-ttu-id="8d439-121">若要设置对 Microsoft.Office.Interop.InfoPath.Xml 互操作程序集的引用，请浏览到默认情况下安装在 <_驱动器_>：\Program Files\Microsoft Office\OFFICE14 文件夹中的 Microsoft.Office.Interop.InfoPath.Xml.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="8d439-121">To set a reference to the Microsoft.Office.Interop.InfoPath.Xml interop assembly, browse to the Microsoft.Office.Interop.InfoPath.Xml.dll file that is installed by default in the < _drive_>:\Program Files\Microsoft Office\OFFICE14 folder.</span></span> <span data-ttu-id="8d439-122">即使在本地文件系统中指定程序集的副本，此过程也建立了对 InfoPath 安装程序在全局程序集缓存 (GAC) 中安装的 Microsoft.Office.Interop.InfoPath.Xml.dll 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8d439-122">Even though you specify the copy of the assembly in the local file system, this procedure establishes a reference to the Microsoft.Office.Interop.InfoPath.Xml.dll assembly that is installed in the Global Assembly Cache (GAC) by the InfoPath setup program.</span></span>
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopathxml-interop-assembly"></a><span data-ttu-id="8d439-123">设置对互操作Microsoft.Office.Interop.InfoPath.Xml的引用</span><span class="sxs-lookup"><span data-stu-id="8d439-123">Set a reference to the Microsoft.Office.Interop.InfoPath.Xml interop assembly</span></span>

1. <span data-ttu-id="8d439-124">打开或创建Visual Studio代码项目，如控制台 **应用程序或Windows\*\*\*\*应用程序**。</span><span class="sxs-lookup"><span data-stu-id="8d439-124">Open or create a Visual Studio managed code project, such as a **Console Application** or **Windows Application**.</span></span>
    
2. <span data-ttu-id="8d439-125">在“解决方案资源管理器”中，右键单击“引用”，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="8d439-125">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>
    
3. <span data-ttu-id="8d439-126">在 **".NET"** 选项卡上，单击"浏览"，导航到 <_驱动器_>：\Program Files\Microsoft Office\OFFICE14 文件夹，然后单击"Microsoft.Office.Interop.InfoPath.Xml.dll"。</span><span class="sxs-lookup"><span data-stu-id="8d439-126">On the **.NET** tab, click **Browse**, navigate to the < _drive_>:\Program Files\Microsoft Office\OFFICE14 folder, and then click Microsoft.Office.Interop.InfoPath.Xml.dll.</span></span>
    
4. <span data-ttu-id="8d439-127">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="8d439-127">Click **OK**.</span></span>
    
## <a name="automate-changing-the-value-of-a-field"></a><span data-ttu-id="8d439-128">自动更改字段值</span><span class="sxs-lookup"><span data-stu-id="8d439-128">Automate changing the value of a field</span></span>

<span data-ttu-id="8d439-129">假设 InfoPath 销售报表用户的一表单模板最近将公司名称从"公司 A"更改为"公司 B"。</span><span class="sxs-lookup"><span data-stu-id="8d439-129">Suppose one of the customers of the user of an InfoPath sales report form template recently changed its name from "Company A" to "Company B."</span></span> <span data-ttu-id="8d439-130">要求开发人员编写代码，以自动更新从该表单保存的销售报表表单模板以反映名称更改。</span><span class="sxs-lookup"><span data-stu-id="8d439-130">A developer is asked to write code that will automatically update the sales report forms saved from this form template to reflect the name change.</span></span> <span data-ttu-id="8d439-131">以下方案假定表单包含绑定到名为 customerName 的字段的文本框。</span><span class="sxs-lookup"><span data-stu-id="8d439-131">The following scenario assumes a form that contains a text box that is bound to a field named customerName.</span></span>
  
### <a name="create-the-sample-form-template-and-form"></a><span data-ttu-id="8d439-132">创建示例表单模板表单</span><span class="sxs-lookup"><span data-stu-id="8d439-132">Create the sample form template and form</span></span>

1. <span data-ttu-id="8d439-133">打开 InfoPath 并创建一个空白表单模板。</span><span class="sxs-lookup"><span data-stu-id="8d439-133">Open InfoPath and create a blank form template.</span></span>
    
2. <span data-ttu-id="8d439-134">向 **窗体中添加一** 个文本框控件，并命名绑定到控件 customerName 的字段。</span><span class="sxs-lookup"><span data-stu-id="8d439-134">Add a **Text Box** control to the form, and name the field bound to the control customerName.</span></span>
    
3. <span data-ttu-id="8d439-135">在"**字段**"任务窗格中，右键单击 **"myFields"** 文件夹，然后单击"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="8d439-135">In the **Fields** task pane, right-click the **myFields** folder, and then click **Properties**.</span></span>
    
4. <span data-ttu-id="8d439-136">在"**详细信息**"选项卡上，选择并复制以下 **Namespace：** 值，然后将其粘贴到记事本或其他可以检索它的位置。</span><span class="sxs-lookup"><span data-stu-id="8d439-136">On the **Details** tab, select and copy the value following **Namespace:**, and then paste this into Notepad or some other location where you can retrieve it.</span></span> <span data-ttu-id="8d439-137">稍后将需要此值来设置代码中 **SelectionNamespaces** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="8d439-137">You will need this value later for setting the value of the **SelectionNamespaces** property in your code.</span></span> 
    
5. <span data-ttu-id="8d439-138">将表单模板到名为 C：\Test 的文件夹并接受默认名称 Template1。</span><span class="sxs-lookup"><span data-stu-id="8d439-138">Publish the form template to a folder named C:\Test and accept the default name, Template1.</span></span> 
    
6. <span data-ttu-id="8d439-139">打开表单模板，将名称"Company A"添加到绑定到 customerName 字段的文本框中，然后将表单另存为"Form1"。</span><span class="sxs-lookup"><span data-stu-id="8d439-139">Open the form template, add the name "Company A" to text box bound to the customerName field, and then save the form as "Form1".</span></span> 
    
### <a name="create-a-managed-code-console-application-to-change-the-name-from-company-a-to-company-b"></a><span data-ttu-id="8d439-140">创建托管代码控制台应用程序以将名称从"Company A"更改为"Company B"</span><span class="sxs-lookup"><span data-stu-id="8d439-140">Create a managed code console application to change the name from 'Company A' to 'Company B'</span></span>

1. <span data-ttu-id="8d439-141">打开Visual Studio，然后新建一个名为 UpdateCustomer C#或Visual Basic控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d439-141">Open Visual Studio and create a new Visual C# or Visual Basic Console Application named UpdateCustomer.</span></span>
    
2. <span data-ttu-id="8d439-142">建立对 InfoPath Microsoft Office互操作和 InfoPath XML 互操作程序集的引用，如上所述。</span><span class="sxs-lookup"><span data-stu-id="8d439-142">Establish references to the Microsoft Office InfoPath primary interop and InfoPath XML interop assemblies as described above.</span></span>
    
3. <span data-ttu-id="8d439-143">将以下代码添加到 Program.cs 或 Module1.vb 文件中，确保使用创建示例表单时复制的值更新 **SelectionNamespaces** 属性设置中的命名空间值。</span><span class="sxs-lookup"><span data-stu-id="8d439-143">Add the following code to the Program.cs or Module1.vb file, making sure to update the value of the namespace in the setting for the **SelectionNamespaces** property with the value you copied when you created the sample form.</span></span> 
    
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

4. <span data-ttu-id="8d439-144">单击 **"调试"菜单** 上的"开始调试"以编译并运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d439-144">Click **Start Debugging** on the **Debug** menu to compile and run the console application.</span></span> 
    
   <span data-ttu-id="8d439-145">应用程序打开另存为Form1.xml并循环访问包含值 Company A 的所有 customerName 元素，将该值更改为公司 B。操作完成后，表单的新副本将另存为Form2.xml C：\Test 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8d439-145">The application opens the form saved as Form1.xml and loops through all customerName elements that contain the value Company A and changes that value to Company B. When the operation is complete, a new copy of the form is saved as Form2.xml in the C:\Test folder.</span></span> 
    
## <a name="automate-opening-a-form-and-populating-field-values"></a><span data-ttu-id="8d439-146">自动打开表单并填充字段值</span><span class="sxs-lookup"><span data-stu-id="8d439-146">Automate opening a form and populating field values</span></span>

<span data-ttu-id="8d439-147">下面的示例自动打开一个空白窗体，并填充窗体中的名字、姓氏和地址字段。</span><span class="sxs-lookup"><span data-stu-id="8d439-147">The following example automates opening a blank form and populating the first name, last name, and address fields in the form.</span></span> <span data-ttu-id="8d439-148">此方案假定窗体包含三个文本框，这些文本框绑定到名为 FirstName、LastName 和 Address 的字段。</span><span class="sxs-lookup"><span data-stu-id="8d439-148">This scenario assumes a form that contains three text boxes that are bound to fields named FirstName, LastName, and Address.</span></span>
  
### <a name="create-the-sample-form-template-and-form"></a><span data-ttu-id="8d439-149">创建示例表单模板表单</span><span class="sxs-lookup"><span data-stu-id="8d439-149">Create the sample form template and form</span></span>

1. <span data-ttu-id="8d439-150">打开 InfoPath 并创建一个空白表单。</span><span class="sxs-lookup"><span data-stu-id="8d439-150">Open InfoPath and create a blank form.</span></span>
    
2. <span data-ttu-id="8d439-151">向窗体中添加三个文本框控件，并命名绑定到控件的字段：FirstName、LastName 和 Address。</span><span class="sxs-lookup"><span data-stu-id="8d439-151">Add three text box controls to the form, and name the fields bound to the controls: FirstName, LastName, and Address.</span></span> <span data-ttu-id="8d439-152">添加任何其他需要的字段。</span><span class="sxs-lookup"><span data-stu-id="8d439-152">Add any other fields you want.</span></span>
    
3. <span data-ttu-id="8d439-153">在"**字段**"任务窗格中，右键单击 **"myFields"** 文件夹，然后单击"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="8d439-153">In the **Fields** task pane, right-click the **myFields** folder, and then click **Properties**.</span></span>
    
4. <span data-ttu-id="8d439-154">在"**详细信息**"选项卡上，选择并复制以下 **Namespace：** 值，然后将其粘贴到记事本或其他可以检索它的位置。</span><span class="sxs-lookup"><span data-stu-id="8d439-154">On the **Details** tab, select and copy the value following **Namespace:**, and then paste this into Notepad or some other location where you can retrieve it.</span></span> <span data-ttu-id="8d439-155">稍后将需要此值来设置代码中 **SelectionNamespaces** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="8d439-155">You will need this value later for setting the value of the **SelectionNamespaces** property in your code.</span></span> 
    
5. <span data-ttu-id="8d439-156">将表单模板 C：\Temp 的文件夹，并接受默认名称 Template1。</span><span class="sxs-lookup"><span data-stu-id="8d439-156">Publish the form template to a folder named C:\Temp and accept the default name, Template1.</span></span>
    
6. <span data-ttu-id="8d439-157">打开表单模板，将空白表单另存为"Form1"至 C：\Temp。</span><span class="sxs-lookup"><span data-stu-id="8d439-157">Open the form template and save a blank form as "Form1" to C:\Temp.</span></span>
    
### <a name="create-a-managed-code-console-application-to-open-the-form-and-populate-the-fields"></a><span data-ttu-id="8d439-158">创建托管代码控制台应用程序以打开表单并填充字段</span><span class="sxs-lookup"><span data-stu-id="8d439-158">Create a managed code console application to open the form and populate the fields</span></span>

1. <span data-ttu-id="8d439-159">打开Visual Studio，然后新建一个名为 OpenForm C#或Visual Basic控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d439-159">Open Visual Studio and create a new Visual C# or Visual Basic Console Application named OpenForm.</span></span>
    
2. <span data-ttu-id="8d439-160">建立对 InfoPath Microsoft Office互操作和 InfoPath XML 互操作程序集的引用，如上所述。</span><span class="sxs-lookup"><span data-stu-id="8d439-160">Establish references to the Microsoft Office InfoPath primary interop and InfoPath XML interop assemblies as described above.</span></span>
    
3. <span data-ttu-id="8d439-161">将以下代码添加到 Program.cs 或 Module1.vb 文件中，确保使用创建示例表单时复制的值更新 **SelectionNamespaces** 属性设置中的命名空间值。</span><span class="sxs-lookup"><span data-stu-id="8d439-161">Add the following code to the Program.cs or Module1.vb file, making sure to update the value of the namespace in the setting for the **SelectionNamespaces** property with the value you copied when you created the sample form.</span></span> 
    
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

4. <span data-ttu-id="8d439-162">在" **调试"** 菜单上，单击" **启动调试"** 以编译并运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d439-162">On the **Debug** menu, click **Start Debugging** to compile and run the console application.</span></span> 
    
   <span data-ttu-id="8d439-163">应用程序将打开另存为 Form1.xml，然后使用代码中指定的值填充 FirstName、LastName 和 Address 字段，然后保存表单，使 InfoPath 保留打开状态。</span><span class="sxs-lookup"><span data-stu-id="8d439-163">The application will open the form saved as Form1.xml and fill in the FirstName, LastName, and Address fields with the values specified in the code, and then save the form, leaving InfoPath open.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="8d439-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d439-164">See also</span></span>

- [<span data-ttu-id="8d439-165">关于 Microsoft Office InfoPath 主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="8d439-165">About the Microsoft Office InfoPath Primary Interop Assembly</span></span>](about-the-microsoft-office-infopath-primary-interop-assembly.md)
- [<span data-ttu-id="8d439-166">关于 InfoPath XML 互操作程序集</span><span class="sxs-lookup"><span data-stu-id="8d439-166">About the InfoPath XML Interop Assembly</span></span>](about-the-infopath-xml-interop-assembly.md)

