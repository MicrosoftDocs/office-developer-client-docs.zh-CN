---
title: 外部自动化方案和示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- 自动化 infopath 2007, 表单 [InfoPath 2007], 以编程方式添加数据, 自动化 [InfoPath 2007], 外部方案
localization_priority: Normal
ms.assetid: dfa880e6-de23-41c4-b80b-6935e0c8563d
description: Microsoft Office InfoPath 主互操作程序集 (如 "Microsoft. .dll") 和 InfoPath XML 互操作程序集 ("Microsoft. Web.xml") 提供的成员支持编写托管代码以实现自动化InfoPath.
ms.openlocfilehash: 79fbc56033ffce639b5007874dabf56e8e286edb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537813"
---
# <a name="external-automation-scenarios-and-examples"></a><span data-ttu-id="84271-104">外部自动化方案和示例</span><span class="sxs-lookup"><span data-stu-id="84271-104">External automation scenarios and examples</span></span>

<span data-ttu-id="84271-105">Microsoft Office InfoPath 主互操作程序集 (如 "Microsoft. .dll") 和 InfoPath XML 互操作程序集 ("Microsoft. Web.xml") 提供的成员支持编写托管代码以实现自动化InfoPath.</span><span class="sxs-lookup"><span data-stu-id="84271-105">The members provided by the Microsoft Office InfoPath primary interop assembly (Microsoft.Office.Interop.InfoPath.dll) and the InfoPath XML interop assembly (Microsoft.Office.Interop.InfoPath.Xml.dll) support writing managed code for automating InfoPath.</span></span> 
  
## <a name="establishing-references-to-the-microsoft-office-infopath-primary-interop-and-infopath-xml-interop-assemblies"></a><span data-ttu-id="84271-106">建立对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用</span><span class="sxs-lookup"><span data-stu-id="84271-106">Establishing references to the Microsoft Office InfoPath Primary Interop and InfoPath XML Interop assemblies</span></span>

<span data-ttu-id="84271-107">若要编写托管代码以自动化 InfoPath, 您必须建立对 Microsoft InfoPath 主互操作和 InfoPath XML 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="84271-107">To write managed code for automating InfoPath, you must establish references to the Microsoft InfoPath primary interop and the InfoPath XML interop assemblies.</span></span> <span data-ttu-id="84271-108">Microsoft InfoPath 主互操作程序集为与 IPEDITOR 公开的 COM 对象模型的互操作性提供支持。DLL 命名空间的成员使用的[](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx) DLL。</span><span class="sxs-lookup"><span data-stu-id="84271-108">The Microsoft InfoPath primary interop assembly provides support for interoperability with the COM object model exposed by IPEDITOR.DLL by using the members of the [Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx) namespace.</span></span> <span data-ttu-id="84271-109">InfoPath XML 互操作程序集支持与通过 microsoft XML Core Services (MSXML) 公开的 COM 对象模型的互操作性, 具体方法是使用[microsoft](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml) Xml Core Services (MSXML) 命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="84271-109">The InfoPath XML interop assembly provides support for interoperability with the COM object model exposed by Microsoft XML Core Services (MSXML) by using the members of the [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml) namespace.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="84271-110">自动化 InfoPath 的托管代码应用程序的用户必须在其计算机上安装 InfoPath、Microsoft Office InfoPath 主互操作程序集和 InfoPath XML 互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="84271-110">Users of managed-code applications that automate InfoPath must have InfoPath, the Microsoft Office InfoPath primary interop assembly, and the InfoPath XML interop assembly installed on their computers.</span></span> <span data-ttu-id="84271-111">InfoPath 安装程序中的 " **.Net 可编程性支持**" 选项设置为 "**从本机运行**", 以便安装 infopath 的典型安装。</span><span class="sxs-lookup"><span data-stu-id="84271-111">The **.NET Programmability Support** option in the InfoPath setup program is set to **Run from My Computer** for a typical installation of InfoPath.</span></span>
>  
> <span data-ttu-id="84271-112">因此, 只要安装了 .NET Framework 1.1 可再发行版或 .NET Framework 1.1 软件开发工具包 (SDK) 或更高版本, 默认情况下也会安装这些互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="84271-112">As a result, as long as the .NET Framework 1.1 Redistributable or .NET Framework 1.1 Software Development Kit (SDK) or later is installed, these interop assemblies will also be installed by default.</span></span> <span data-ttu-id="84271-113">如果这些互操作程序集在用户计算机上不可用, 则必须确认已安装 .NET Framework 1.1 或更高版本, 然后运行 "**控制面板**" 中的 "**程序和功能**" 更改安装程序并设置 **.net 可编程性\*\*\*\*从 "我的电脑" 运行**的 InfoPath 支持选项。</span><span class="sxs-lookup"><span data-stu-id="84271-113">If these interop assemblies are not available on a user's computer, you must confirm that the .NET Framework 1.1 or later is installed, and then run **Programs and Features** from the **Control Panel** to change setup and set the **.NET Programmability Support** option of InfoPath to **Run from My Computer**.</span></span> 
  
<span data-ttu-id="84271-114">以下过程介绍如何在 Visual Studio 项目中设置对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="84271-114">The following procedures describe how to set references to the Microsoft Office InfoPath primary interop and the InfoPath XML interop assemblies in a Visual Studio project.</span></span>
  
<span data-ttu-id="84271-115">若要设置对 Microsoft InfoPath 的主互操作程序集的引用, 请在 "**添加引用**" 对话框的 " **COM** " 选项卡上设置对**microsoft InfoPath 3.0 类型库**的引用。</span><span class="sxs-lookup"><span data-stu-id="84271-115">To set a reference to the Microsoft.Office.Interop.InfoPath primary interop assembly, set a reference to **Microsoft InfoPath 3.0 Type Library** on the **COM** tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="84271-116">即使您从 " **COM** " 选项卡中设置了引用, 也会为 infopath 安装程序在全局程序集缓存 (GAC) 中安装的 Microsoft. .dll 主互操作程序集建立一个引用。</span><span class="sxs-lookup"><span data-stu-id="84271-116">Even though you set a reference from the **COM** tab, a reference is established to the Microsoft.Office.Interop.InfoPath.dll primary interop assembly that is installed in the Global Assembly Cache (GAC) by the InfoPath setup program.</span></span> 
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopath-primary-interop-assembly"></a><span data-ttu-id="84271-117">设置对 Microsoft. InfoPath 主互操作程序集的引用</span><span class="sxs-lookup"><span data-stu-id="84271-117">Set a reference to the Microsoft.Office.Interop.InfoPath primary interop assembly</span></span>

1. <span data-ttu-id="84271-118">打开 Visual Studio 托管代码项目。</span><span class="sxs-lookup"><span data-stu-id="84271-118">Open a Visual Studio managed code project.</span></span>
    
2. <span data-ttu-id="84271-119">在“解决方案资源管理器”\*\*\*\* 中，右键单击“引用”\*\*\*\*，然后单击“添加引用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84271-119">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>
    
3. <span data-ttu-id="84271-120">在 " **COM** " 选项卡上, 双击 " **Microsoft InfoPath 3.0 类型库**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="84271-120">On the **COM** tab, double-click **Microsoft InfoPath 3.0 Type Library**, and then click **OK**.</span></span>
    
<span data-ttu-id="84271-121">若要设置对 Microsoft. Xml 互操作程序集的引用, 请浏览到默认情况下在 < _drive_>: \Program Files\Microsoft Office\OFFICE14 文件夹中安装的 Microsoft. .xml .dll 文件。.</span><span class="sxs-lookup"><span data-stu-id="84271-121">To set a reference to the Microsoft.Office.Interop.InfoPath.Xml interop assembly, browse to the Microsoft.Office.Interop.InfoPath.Xml.dll file that is installed by default in the < _drive_>:\Program Files\Microsoft Office\OFFICE14 folder.</span></span> <span data-ttu-id="84271-122">即使您在本地文件系统中指定了程序集的副本, 此过程也会建立对 InfoPath 安装程序安装在全局程序集缓存 (GAC) 中的 Microsoft. .Xml .dll 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="84271-122">Even though you specify the copy of the assembly in the local file system, this procedure establishes a reference to the Microsoft.Office.Interop.InfoPath.Xml.dll assembly that is installed in the Global Assembly Cache (GAC) by the InfoPath setup program.</span></span>
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopathxml-interop-assembly"></a><span data-ttu-id="84271-123">设置对 Microsoft. Web.xml 互操作程序集的引用</span><span class="sxs-lookup"><span data-stu-id="84271-123">Set a reference to the Microsoft.Office.Interop.InfoPath.Xml interop assembly</span></span>

1. <span data-ttu-id="84271-124">打开或创建一个 Visual Studio 托管代码项目, 如**控制台应用程序**或**Windows 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="84271-124">Open or create a Visual Studio managed code project, such as a **Console Application** or **Windows Application**.</span></span>
    
2. <span data-ttu-id="84271-125">在“解决方案资源管理器”\*\*\*\* 中，右键单击“引用”\*\*\*\*，然后单击“添加引用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84271-125">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>
    
3. <span data-ttu-id="84271-126">在 " **.net** " 选项卡上, 单击 "**浏览**", 导航到 < _drive_>: \Program Files\Microsoft Office\OFFICE14 文件夹, 然后单击 ""。</span><span class="sxs-lookup"><span data-stu-id="84271-126">On the **.NET** tab, click **Browse**, navigate to the < _drive_>:\Program Files\Microsoft Office\OFFICE14 folder, and then click Microsoft.Office.Interop.InfoPath.Xml.dll.</span></span>
    
4. <span data-ttu-id="84271-127">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84271-127">Click **OK**.</span></span>
    
## <a name="automate-changing-the-value-of-a-field"></a><span data-ttu-id="84271-128">自动更改字段的值</span><span class="sxs-lookup"><span data-stu-id="84271-128">Automate changing the value of a field</span></span>

<span data-ttu-id="84271-129">假设 InfoPath sales report 表单模板的用户之一的客户最近将其名称从 "Company A" 更改为 "Company B"。</span><span class="sxs-lookup"><span data-stu-id="84271-129">Suppose one of the customers of the user of an InfoPath sales report form template recently changed its name from "Company A" to "Company B."</span></span> <span data-ttu-id="84271-130">要求开发人员编写代码, 以自动更新从该表单模板保存的销售报告表单, 以反映名称的变化。</span><span class="sxs-lookup"><span data-stu-id="84271-130">A developer is asked to write code that will automatically update the sales report forms saved from this form template to reflect the name change.</span></span> <span data-ttu-id="84271-131">下面的方案假定表单中包含一个绑定到名为 customerName 的字段的文本框。</span><span class="sxs-lookup"><span data-stu-id="84271-131">The following scenario assumes a form that contains a text box that is bound to a field named customerName.</span></span>
  
### <a name="create-the-sample-form-template-and-form"></a><span data-ttu-id="84271-132">创建示例表单模板和表单</span><span class="sxs-lookup"><span data-stu-id="84271-132">Create the sample form template and form</span></span>

1. <span data-ttu-id="84271-133">打开 InfoPath 并创建一个空白表单模板。</span><span class="sxs-lookup"><span data-stu-id="84271-133">Open InfoPath and create a blank form template.</span></span>
    
2. <span data-ttu-id="84271-134">将 "**文本框**" 控件添加到窗体中, 并将绑定到控件 customerName 的字段命名。</span><span class="sxs-lookup"><span data-stu-id="84271-134">Add a **Text Box** control to the form, and name the field bound to the control customerName.</span></span>
    
3. <span data-ttu-id="84271-135">在 "**域**" 任务窗格中, 右键单击 " **myFields** " 文件夹, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="84271-135">In the **Fields** task pane, right-click the **myFields** folder, and then click **Properties**.</span></span>
    
4. <span data-ttu-id="84271-136">在 "**详细信息**" 选项卡上, 选择并复制**命名空间**后面的值:, 然后将其粘贴到记事本或其他可在其中进行检索的位置。</span><span class="sxs-lookup"><span data-stu-id="84271-136">On the **Details** tab, select and copy the value following **Namespace:**, and then paste this into Notepad or some other location where you can retrieve it.</span></span> <span data-ttu-id="84271-137">稍后将需要此值, 以便在代码中设置**SelectionNamespaces**属性的值。</span><span class="sxs-lookup"><span data-stu-id="84271-137">You will need this value later for setting the value of the **SelectionNamespaces** property in your code.</span></span> 
    
5. <span data-ttu-id="84271-138">将表单模板发布到名为 C:\Test 的文件夹, 并接受默认名称 Template1。</span><span class="sxs-lookup"><span data-stu-id="84271-138">Publish the form template to a folder named C:\Test and accept the default name, Template1.</span></span> 
    
6. <span data-ttu-id="84271-139">打开表单模板, 将名称 "Company A" 添加到绑定到 customerName 域的文本框, 然后将该表单另存为 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="84271-139">Open the form template, add the name "Company A" to text box bound to the customerName field, and then save the form as "Form1".</span></span> 
    
### <a name="create-a-managed-code-console-application-to-change-the-name-from-company-a-to-company-b"></a><span data-ttu-id="84271-140">创建托管代码控制台应用程序以将名称从 "Company A" 更改为 "Company B"</span><span class="sxs-lookup"><span data-stu-id="84271-140">Create a managed code console application to change the name from 'Company A' to 'Company B'</span></span>

1. <span data-ttu-id="84271-141">打开 Visual Studio, 创建一个名为 UpdateCustomer 的新 Visual c # 或 Visual Basic 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="84271-141">Open Visual Studio and create a new Visual C# or Visual Basic Console Application named UpdateCustomer.</span></span>
    
2. <span data-ttu-id="84271-142">按照上述说明, 建立对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="84271-142">Establish references to the Microsoft Office InfoPath primary interop and InfoPath XML interop assemblies as described above.</span></span>
    
3. <span data-ttu-id="84271-143">将以下代码添加到 Program.cs 或 Module1 文件, 确保使用创建示例表单时复制的值来更新**SelectionNamespaces**属性的设置中的命名空间的值。</span><span class="sxs-lookup"><span data-stu-id="84271-143">Add the following code to the Program.cs or Module1.vb file, making sure to update the value of the namespace in the setting for the **SelectionNamespaces** property with the value you copied when you created the sample form.</span></span> 
    
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

4. <span data-ttu-id="84271-144">单击 "**调试**" 菜单上的 "**启动调试**" 以编译并运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="84271-144">Click **Start Debugging** on the **Debug** menu to compile and run the console application.</span></span> 
    
   <span data-ttu-id="84271-145">应用程序打开另存为 Form1 的窗体, 并循环访问包含价值公司 A 的所有 customerName 元素, 并将该值更改为 Company B。操作完成后, 将表单的新副本保存为 C:\Test 文件夹中的 Form2. xml。</span><span class="sxs-lookup"><span data-stu-id="84271-145">The application opens the form saved as Form1.xml and loops through all customerName elements that contain the value Company A and changes that value to Company B. When the operation is complete, a new copy of the form is saved as Form2.xml in the C:\Test folder.</span></span> 
    
## <a name="automate-opening-a-form-and-populating-field-values"></a><span data-ttu-id="84271-146">自动打开表单和填充字段值</span><span class="sxs-lookup"><span data-stu-id="84271-146">Automate opening a form and populating field values</span></span>

<span data-ttu-id="84271-147">下面的示例自动打开一个空白窗体, 并在窗体中填充名、姓和地址字段。</span><span class="sxs-lookup"><span data-stu-id="84271-147">The following example automates opening a blank form and populating the first name, last name, and address fields in the form.</span></span> <span data-ttu-id="84271-148">此方案假定表单中包含三个文本框, 这些文本框绑定到名为 "名字"、"姓氏" 和 "地址" 的域。</span><span class="sxs-lookup"><span data-stu-id="84271-148">This scenario assumes a form that contains three text boxes that are bound to fields named FirstName, LastName, and Address.</span></span>
  
### <a name="create-the-sample-form-template-and-form"></a><span data-ttu-id="84271-149">创建示例表单模板和表单</span><span class="sxs-lookup"><span data-stu-id="84271-149">Create the sample form template and form</span></span>

1. <span data-ttu-id="84271-150">打开 InfoPath 并创建一个空白表单。</span><span class="sxs-lookup"><span data-stu-id="84271-150">Open InfoPath and create a blank form.</span></span>
    
2. <span data-ttu-id="84271-151">向窗体中添加三个文本框控件, 并将绑定到控件的字段命名为: FirstName、LastName 和 Address。</span><span class="sxs-lookup"><span data-stu-id="84271-151">Add three text box controls to the form, and name the fields bound to the controls: FirstName, LastName, and Address.</span></span> <span data-ttu-id="84271-152">添加所需的任何其他字段。</span><span class="sxs-lookup"><span data-stu-id="84271-152">Add any other fields you want.</span></span>
    
3. <span data-ttu-id="84271-153">在 "**域**" 任务窗格中, 右键单击 " **myFields** " 文件夹, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="84271-153">In the **Fields** task pane, right-click the **myFields** folder, and then click **Properties**.</span></span>
    
4. <span data-ttu-id="84271-154">在 "**详细信息**" 选项卡上, 选择并复制**命名空间**后面的值:, 然后将其粘贴到记事本或其他可在其中进行检索的位置。</span><span class="sxs-lookup"><span data-stu-id="84271-154">On the **Details** tab, select and copy the value following **Namespace:**, and then paste this into Notepad or some other location where you can retrieve it.</span></span> <span data-ttu-id="84271-155">稍后将需要此值, 以便在代码中设置**SelectionNamespaces**属性的值。</span><span class="sxs-lookup"><span data-stu-id="84271-155">You will need this value later for setting the value of the **SelectionNamespaces** property in your code.</span></span> 
    
5. <span data-ttu-id="84271-156">将表单模板发布到名为 C:\Temp 的文件夹, 并接受默认名称 Template1。</span><span class="sxs-lookup"><span data-stu-id="84271-156">Publish the form template to a folder named C:\Temp and accept the default name, Template1.</span></span>
    
6. <span data-ttu-id="84271-157">打开表单模板并将空白表单另存为 "Form1" 到 C:\temp。</span><span class="sxs-lookup"><span data-stu-id="84271-157">Open the form template and save a blank form as "Form1" to C:\Temp.</span></span>
    
### <a name="create-a-managed-code-console-application-to-open-the-form-and-populate-the-fields"></a><span data-ttu-id="84271-158">创建托管代码控制台应用程序以打开表单并填充字段</span><span class="sxs-lookup"><span data-stu-id="84271-158">Create a managed code console application to open the form and populate the fields</span></span>

1. <span data-ttu-id="84271-159">打开 Visual Studio, 创建一个新的 Visual c # 或 Visual Basic 控制台应用程序 (名为 OpenForm)。</span><span class="sxs-lookup"><span data-stu-id="84271-159">Open Visual Studio and create a new Visual C# or Visual Basic Console Application named OpenForm.</span></span>
    
2. <span data-ttu-id="84271-160">按照上述说明, 建立对 Microsoft Office InfoPath 主互操作性和 InfoPath XML 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="84271-160">Establish references to the Microsoft Office InfoPath primary interop and InfoPath XML interop assemblies as described above.</span></span>
    
3. <span data-ttu-id="84271-161">将以下代码添加到 Program.cs 或 Module1 文件, 确保使用创建示例表单时复制的值来更新**SelectionNamespaces**属性的设置中的命名空间的值。</span><span class="sxs-lookup"><span data-stu-id="84271-161">Add the following code to the Program.cs or Module1.vb file, making sure to update the value of the namespace in the setting for the **SelectionNamespaces** property with the value you copied when you created the sample form.</span></span> 
    
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

4. <span data-ttu-id="84271-162">在 "**调试**" 菜单上, 单击 "**启动调试**" 以编译并运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="84271-162">On the **Debug** menu, click **Start Debugging** to compile and run the console application.</span></span> 
    
   <span data-ttu-id="84271-163">应用程序将打开保存为 Form1 .xml 的表单, 并使用代码中指定的值填充 "名字"、"姓氏" 和 "地址" 字段, 然后保存该表单, 使 InfoPath 保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="84271-163">The application will open the form saved as Form1.xml and fill in the FirstName, LastName, and Address fields with the values specified in the code, and then save the form, leaving InfoPath open.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="84271-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84271-164">See also</span></span>

- [<span data-ttu-id="84271-165">关于 Microsoft Office InfoPath 主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="84271-165">About the Microsoft Office InfoPath Primary Interop Assembly</span></span>](about-the-microsoft-office-infopath-primary-interop-assembly.md)
- [<span data-ttu-id="84271-166">关于 InfoPath XML 互操作程序集</span><span class="sxs-lookup"><span data-stu-id="84271-166">About the InfoPath XML Interop Assembly</span></span>](about-the-infopath-xml-interop-assembly.md)

