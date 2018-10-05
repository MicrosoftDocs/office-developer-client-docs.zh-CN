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
# <a name="external-automation-scenarios-and-examples"></a><span data-ttu-id="ac012-104">外部自动化方案和示例</span><span class="sxs-lookup"><span data-stu-id="ac012-104">External automation scenarios and examples</span></span>

<span data-ttu-id="ac012-105">Microsoft Office InfoPath 主互操作程序集 (Microsoft.Office.Interop.InfoPath.dll) 和 InfoPath XML 互操作程序集 (Microsoft.Office.Interop.InfoPath.Xml.dll) 用于自动执行支持编写托管代码提供的成员InfoPath。</span><span class="sxs-lookup"><span data-stu-id="ac012-105">The members provided by the Microsoft Office InfoPath primary interop assembly (Microsoft.Office.Interop.InfoPath.dll) and the InfoPath XML interop assembly (Microsoft.Office.Interop.InfoPath.Xml.dll) support writing managed code for automating InfoPath.</span></span> 
  
## <a name="establishing-references-to-the-microsoft-office-infopath-primary-interop-and-infopath-xml-interop-assemblies"></a><span data-ttu-id="ac012-106">建立对 Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集参考</span><span class="sxs-lookup"><span data-stu-id="ac012-106">Establishing references to the Microsoft Office InfoPath Primary Interop and InfoPath XML Interop assemblies</span></span>

<span data-ttu-id="ac012-107">若要编写用于自动执行 InfoPath 托管的代码，必须建立对 Microsoft InfoPath 主互操作和 InfoPath XML 互操作程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="ac012-107">To write managed code for automating InfoPath, you must establish references to the Microsoft InfoPath primary interop and the InfoPath XML interop assemblies.</span></span> <span data-ttu-id="ac012-108">Microsoft InfoPath 主互操作程序集提供与 COM 对象模型公开 IPEDITOR 互操作性支持。通过使用[Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx)命名空间的成员的 DLL。</span><span class="sxs-lookup"><span data-stu-id="ac012-108">The Microsoft InfoPath primary interop assembly provides support for interoperability with the COM object model exposed by IPEDITOR.DLL by using the members of the [Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.aspx) namespace.</span></span> <span data-ttu-id="ac012-109">InfoPath XML 互操作程序集提供支持的互操作性与 COM 对象模型公开由 Microsoft XML Core Services (MSXML) 使用[Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml)命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="ac012-109">The InfoPath XML interop assembly provides support for interoperability with the COM object model exposed by Microsoft XML Core Services (MSXML) by using the members of the [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/library/microsoft.office.interop.infopath.xml) namespace.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ac012-110">自动执行 InfoPath 托管代码应用程序的用户必须具有 InfoPath、 Microsoft Office InfoPath 主互操作程序集和 InfoPath XML 互操作程序集安装在其计算机上。</span><span class="sxs-lookup"><span data-stu-id="ac012-110">Users of managed-code applications that automate InfoPath must have InfoPath, the Microsoft Office InfoPath primary interop assembly, and the InfoPath XML interop assembly installed on their computers.</span></span> <span data-ttu-id="ac012-111">InfoPath 的典型安装的情况下，InfoPath 安装程序中的 **.NET 可编程性支持**选项设置为**从本机运行**。</span><span class="sxs-lookup"><span data-stu-id="ac012-111">The **.NET Programmability Support** option in the InfoPath setup program is set to **Run from My Computer** for a typical installation of InfoPath.</span></span>
>  
> <span data-ttu-id="ac012-112">因此，如已安装长为.NET Framework 1.1 版可再发行组件或.NET Framework 1.1 软件开发工具包 (SDK) 或更高版本，将也默认情况下安装这些互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="ac012-112">As a result, as long as the .NET Framework 1.1 Redistributable or .NET Framework 1.1 Software Development Kit (SDK) or later is installed, these interop assemblies will also be installed by default.</span></span> <span data-ttu-id="ac012-113">如果这些互操作程序集不在用户的计算机上可用，您必须确认.NET Framework 1.1 或更高版本是安装，然后从**控制面板**以更改安装程序并设置 **.NET 可编程性运行**程序和功能**支持**到**从本机运行**的 InfoPath 的选项。</span><span class="sxs-lookup"><span data-stu-id="ac012-113">If these interop assemblies are not available on a user's computer, you must confirm that the .NET Framework 1.1 or later is installed, and then run **Programs and Features** from the **Control Panel** to change setup and set the **.NET Programmability Support** option of InfoPath to **Run from My Computer**.</span></span> 
  
<span data-ttu-id="ac012-114">以下过程介绍如何设置 Visual Studio 项目中的 Microsoft Office InfoPath 主互操作和 InfoPath XML 引用互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="ac012-114">The following procedures describe how to set references to the Microsoft Office InfoPath primary interop and the InfoPath XML interop assemblies in a Visual Studio project.</span></span>
  
<span data-ttu-id="ac012-115">若要设置对 Microsoft.Office.Interop.InfoPath 主互操作程序集的引用，请将在**添加引用**对话框的**COM**选项卡上设置对**Microsoft InfoPath 3.0 类型库**的引用。</span><span class="sxs-lookup"><span data-stu-id="ac012-115">To set a reference to the Microsoft.Office.Interop.InfoPath primary interop assembly, set a reference to **Microsoft InfoPath 3.0 Type Library** on the **COM** tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="ac012-116">即使设置从**COM**选项卡的引用，请参考对 Microsoft.Office.Interop.InfoPath.dll 主互操作程序集由 InfoPath 安装程序安装在全局程序集缓存 (GAC) 中的建立。</span><span class="sxs-lookup"><span data-stu-id="ac012-116">Even though you set a reference from the **COM** tab, a reference is established to the Microsoft.Office.Interop.InfoPath.dll primary interop assembly that is installed in the Global Assembly Cache (GAC) by the InfoPath setup program.</span></span> 
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopath-primary-interop-assembly"></a><span data-ttu-id="ac012-117">设置对 Microsoft.Office.Interop.InfoPath 主互操作程序集的引用</span><span class="sxs-lookup"><span data-stu-id="ac012-117">Set a reference to the Microsoft.Office.Interop.InfoPath primary interop assembly</span></span>

1. <span data-ttu-id="ac012-118">打开 Visual Studio 托管的代码项目。</span><span class="sxs-lookup"><span data-stu-id="ac012-118">Open a Visual Studio managed code project.</span></span>
    
2. <span data-ttu-id="ac012-119">在**解决方案资源管理器**中，右键单击**引用**，，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="ac012-119">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>
    
3. <span data-ttu-id="ac012-120">**COM**选项卡中，双击**Microsoft InfoPath 3.0 类型库**中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ac012-120">On the **COM** tab, double-click **Microsoft InfoPath 3.0 Type Library**, and then click **OK**.</span></span>
    
<span data-ttu-id="ac012-121">要设置对 Microsoft.Office.Interop.InfoPath.Xml 互操作程序集的引用，请浏览到 <_驱动器_> 中默认情况下安装的 Microsoft.Office.Interop.InfoPath.Xml.dll 文件： \Program Files\Microsoft Office\OFFICE14 文件夹.</span><span class="sxs-lookup"><span data-stu-id="ac012-121">To set a reference to the Microsoft.Office.Interop.InfoPath.Xml interop assembly, browse to the Microsoft.Office.Interop.InfoPath.Xml.dll file that is installed by default in the < _drive_>:\Program Files\Microsoft Office\OFFICE14 folder.</span></span> <span data-ttu-id="ac012-122">即使本地文件系统中指定的程序集的副本，此过程将建立对由 InfoPath 安装程序安装在全局程序集缓存 (GAC) 中的 Microsoft.Office.Interop.InfoPath.Xml.dll 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="ac012-122">Even though you specify the copy of the assembly in the local file system, this procedure establishes a reference to the Microsoft.Office.Interop.InfoPath.Xml.dll assembly that is installed in the Global Assembly Cache (GAC) by the InfoPath setup program.</span></span>
  
### <a name="set-a-reference-to-the-microsoftofficeinteropinfopathxml-interop-assembly"></a><span data-ttu-id="ac012-123">设置对 Microsoft.Office.Interop.InfoPath.Xml 互操作程序集的引用</span><span class="sxs-lookup"><span data-stu-id="ac012-123">Set a reference to the Microsoft.Office.Interop.InfoPath.Xml interop assembly</span></span>

1. <span data-ttu-id="ac012-124">打开或创建 Visual Studio 托管的代码项目，如**控制台应用程序**或**Windows 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ac012-124">Open or create a Visual Studio managed code project, such as a **Console Application** or **Windows Application**.</span></span>
    
2. <span data-ttu-id="ac012-125">在**解决方案资源管理器**中，右键单击**引用**，，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="ac012-125">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>
    
3. <span data-ttu-id="ac012-126">在 **.NET**选项卡上，单击**浏览**，导航到 <_驱动器_>: \Program Files\Microsoft Office\OFFICE14 文件夹，然后单击 Microsoft.Office.Interop.InfoPath.Xml.dll。</span><span class="sxs-lookup"><span data-stu-id="ac012-126">On the **.NET** tab, click **Browse**, navigate to the < _drive_>:\Program Files\Microsoft Office\OFFICE14 folder, and then click Microsoft.Office.Interop.InfoPath.Xml.dll.</span></span>
    
4. <span data-ttu-id="ac012-127">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac012-127">Click **OK**.</span></span>
    
## <a name="automate-changing-the-value-of-a-field"></a><span data-ttu-id="ac012-128">自动更改字段的值</span><span class="sxs-lookup"><span data-stu-id="ac012-128">Automate changing the value of a field</span></span>

<span data-ttu-id="ac012-129">假定一个 InfoPath 销售报表表单模板的用户的客户最近更改"公司 A"到"公司 B"其名称</span><span class="sxs-lookup"><span data-stu-id="ac012-129">Suppose one of the customers of the user of an InfoPath sales report form template recently changed its name from "Company A" to "Company B."</span></span> <span data-ttu-id="ac012-130">开发人员需要编写将自动更新从此表单模板，以反映名称的更改保存的销售报告表单的代码。</span><span class="sxs-lookup"><span data-stu-id="ac012-130">A developer is asked to write code that will automatically update the sales report forms saved from this form template to reflect the name change.</span></span> <span data-ttu-id="ac012-131">以下方案假定窗体包含一个文本框绑定到名为 customerName 的字段。</span><span class="sxs-lookup"><span data-stu-id="ac012-131">The following scenario assumes a form that contains a text box that is bound to a field named customerName.</span></span>
  
### <a name="create-the-sample-form-template-and-form"></a><span data-ttu-id="ac012-132">创建示例表单模板和表单</span><span class="sxs-lookup"><span data-stu-id="ac012-132">Create the sample form template and form</span></span>

1. <span data-ttu-id="ac012-133">打开 InfoPath 并创建一个空白表单模板。</span><span class="sxs-lookup"><span data-stu-id="ac012-133">Open InfoPath and create a blank form template.</span></span>
    
2. <span data-ttu-id="ac012-134">将**文本框**控件添加到窗体，并命名绑定到控件 customerName 的域。</span><span class="sxs-lookup"><span data-stu-id="ac012-134">Add a **Text Box** control to the form, and name the field bound to the control customerName.</span></span>
    
3. <span data-ttu-id="ac012-135">在**字段**任务窗格中，右键单击**myFields**文件夹，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ac012-135">In the **Fields** task pane, right-click the **myFields** folder, and then click **Properties**.</span></span>
    
4. <span data-ttu-id="ac012-136">在**详细信息**选项卡上，选择并复制值以下**Namespace:**，然后将此粘贴到记事本或其他一些您可以检索的位置。</span><span class="sxs-lookup"><span data-stu-id="ac012-136">On the **Details** tab, select and copy the value following **Namespace:**, and then paste this into Notepad or some other location where you can retrieve it.</span></span> <span data-ttu-id="ac012-137">在代码中设置**SelectionNamespaces**属性的值，将稍后需要此值。</span><span class="sxs-lookup"><span data-stu-id="ac012-137">You will need this value later for setting the value of the **SelectionNamespaces** property in your code.</span></span> 
    
5. <span data-ttu-id="ac012-138">将表单模板发布到一个名为 C:\Test 文件夹并接受默认名称，Template1。</span><span class="sxs-lookup"><span data-stu-id="ac012-138">Publish the form template to a folder named C:\Test and accept the default name, Template1.</span></span> 
    
6. <span data-ttu-id="ac012-139">打开表单模板，添加"公司 A"到文本框绑定到 customerName 字段的名称，然后保存作为"Form1"窗体。</span><span class="sxs-lookup"><span data-stu-id="ac012-139">Open the form template, add the name "Company A" to text box bound to the customerName field, and then save the form as "Form1".</span></span> 
    
### <a name="create-a-managed-code-console-application-to-change-the-name-from-company-a-to-company-b"></a><span data-ttu-id="ac012-140">为公司 B' 创建托管的代码控制台应用程序，以更改公司 A 的名称</span><span class="sxs-lookup"><span data-stu-id="ac012-140">Create a managed code console application to change the name from 'Company A' to 'Company B'</span></span>

1. <span data-ttu-id="ac012-141">打开 Visual Studio 并创建新 Visual C# 或 Visual Basic 名为 UpdateCustomer 的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac012-141">Open Visual Studio and create a new Visual C# or Visual Basic Console Application named UpdateCustomer.</span></span>
    
2. <span data-ttu-id="ac012-142">建立对 Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集的引用，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="ac012-142">Establish references to the Microsoft Office InfoPath primary interop and InfoPath XML interop assemblies as described above.</span></span>
    
3. <span data-ttu-id="ac012-143">将以下代码添加到 Program.cs 或 Module1.vb 文件，并确保复制创建示例表单时的值更新的命名空间中**SelectionNamespaces**属性的设置的值。</span><span class="sxs-lookup"><span data-stu-id="ac012-143">Add the following code to the Program.cs or Module1.vb file, making sure to update the value of the namespace in the setting for the **SelectionNamespaces** property with the value you copied when you created the sample form.</span></span> 
    
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

4. <span data-ttu-id="ac012-144">编译并运行控制台应用程序**调试**菜单上，单击**开始调试**。</span><span class="sxs-lookup"><span data-stu-id="ac012-144">Click **Start Debugging** on the **Debug** menu to compile and run the console application.</span></span> 
    
   <span data-ttu-id="ac012-145">应用程序打开该窗体保存为 Form1.xml 和循环访问包含公司 A 值的所有 customerName 元素，该值更改为公司 B完成该操作时，窗体的新副本另存为 Form2.xml C:\Test 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ac012-145">The application opens the form saved as Form1.xml and loops through all customerName elements that contain the value Company A and changes that value to Company B. When the operation is complete, a new copy of the form is saved as Form2.xml in the C:\Test folder.</span></span> 
    
## <a name="automate-opening-a-form-and-populating-field-values"></a><span data-ttu-id="ac012-146">自动化打开窗体和填充字段值</span><span class="sxs-lookup"><span data-stu-id="ac012-146">Automate opening a form and populating field values</span></span>

<span data-ttu-id="ac012-147">以下示例将自动打开一个空白窗体并填充的名字、 姓氏和窗体中的地址字段。</span><span class="sxs-lookup"><span data-stu-id="ac012-147">The following example automates opening a blank form and populating the first name, last name, and address fields in the form.</span></span> <span data-ttu-id="ac012-148">此方案假定窗体包含三个文本框绑定到名为 FirstName、 LastName 和地址的域。</span><span class="sxs-lookup"><span data-stu-id="ac012-148">This scenario assumes a form that contains three text boxes that are bound to fields named FirstName, LastName, and Address.</span></span>
  
### <a name="create-the-sample-form-template-and-form"></a><span data-ttu-id="ac012-149">创建示例表单模板和表单</span><span class="sxs-lookup"><span data-stu-id="ac012-149">Create the sample form template and form</span></span>

1. <span data-ttu-id="ac012-150">打开 InfoPath 并创建一个空白窗体。</span><span class="sxs-lookup"><span data-stu-id="ac012-150">Open InfoPath and create a blank form.</span></span>
    
2. <span data-ttu-id="ac012-151">添加三个文本框控件的窗体，并命名字段绑定到控件： FirstName、 LastName 和地址。</span><span class="sxs-lookup"><span data-stu-id="ac012-151">Add three text box controls to the form, and name the fields bound to the controls: FirstName, LastName, and Address.</span></span> <span data-ttu-id="ac012-152">添加所需的任何其他字段。</span><span class="sxs-lookup"><span data-stu-id="ac012-152">Add any other fields you want.</span></span>
    
3. <span data-ttu-id="ac012-153">在**字段**任务窗格中，右键单击**myFields**文件夹，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ac012-153">In the **Fields** task pane, right-click the **myFields** folder, and then click **Properties**.</span></span>
    
4. <span data-ttu-id="ac012-154">在**详细信息**选项卡上，选择并复制值以下**Namespace:**，然后将此粘贴到记事本或其他一些您可以检索的位置。</span><span class="sxs-lookup"><span data-stu-id="ac012-154">On the **Details** tab, select and copy the value following **Namespace:**, and then paste this into Notepad or some other location where you can retrieve it.</span></span> <span data-ttu-id="ac012-155">在代码中设置**SelectionNamespaces**属性的值，将稍后需要此值。</span><span class="sxs-lookup"><span data-stu-id="ac012-155">You will need this value later for setting the value of the **SelectionNamespaces** property in your code.</span></span> 
    
5. <span data-ttu-id="ac012-156">将表单模板发布到一个名为 C:\Temp 文件夹并接受默认名称，Template1。</span><span class="sxs-lookup"><span data-stu-id="ac012-156">Publish the form template to a folder named C:\Temp and accept the default name, Template1.</span></span>
    
6. <span data-ttu-id="ac012-157">打开表单模板并将空白窗体另存为"Form1"为 C:\Temp。</span><span class="sxs-lookup"><span data-stu-id="ac012-157">Open the form template and save a blank form as "Form1" to C:\Temp.</span></span>
    
### <a name="create-a-managed-code-console-application-to-open-the-form-and-populate-the-fields"></a><span data-ttu-id="ac012-158">创建托管的代码控制台应用程序，以打开表单并填充的字段</span><span class="sxs-lookup"><span data-stu-id="ac012-158">Create a managed code console application to open the form and populate the fields</span></span>

1. <span data-ttu-id="ac012-159">打开 Visual Studio 并创建新 Visual C# 或 Visual Basic 名为 OpenForm 的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac012-159">Open Visual Studio and create a new Visual C# or Visual Basic Console Application named OpenForm.</span></span>
    
2. <span data-ttu-id="ac012-160">建立对 Microsoft Office InfoPath 主互操作和 InfoPath XML 互操作程序集的引用，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="ac012-160">Establish references to the Microsoft Office InfoPath primary interop and InfoPath XML interop assemblies as described above.</span></span>
    
3. <span data-ttu-id="ac012-161">将以下代码添加到 Program.cs 或 Module1.vb 文件，并确保复制创建示例表单时的值更新的命名空间中**SelectionNamespaces**属性的设置的值。</span><span class="sxs-lookup"><span data-stu-id="ac012-161">Add the following code to the Program.cs or Module1.vb file, making sure to update the value of the namespace in the setting for the **SelectionNamespaces** property with the value you copied when you created the sample form.</span></span> 
    
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

4. <span data-ttu-id="ac012-162">在**调试**菜单上，单击**启动调试**编译并运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac012-162">On the **Debug** menu, click **Start Debugging** to compile and run the console application.</span></span> 
    
   <span data-ttu-id="ac012-163">应用程序将打开窗体另存为 Form1.xml 和 FirstName、 LastName 和地址字段中填入在代码中，指定的值，然后保存表单，使 InfoPath 保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="ac012-163">The application will open the form saved as Form1.xml and fill in the FirstName, LastName, and Address fields with the values specified in the code, and then save the form, leaving InfoPath open.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="ac012-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac012-164">See also</span></span>

- [<span data-ttu-id="ac012-165">关于 Microsoft Office InfoPath 主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="ac012-165">About the Microsoft Office InfoPath Primary Interop Assembly</span></span>](about-the-microsoft-office-infopath-primary-interop-assembly.md)
- [<span data-ttu-id="ac012-166">关于 InfoPath XML 互操作程序集</span><span class="sxs-lookup"><span data-stu-id="ac012-166">About the InfoPath XML Interop Assembly</span></span>](about-the-infopath-xml-interop-assembly.md)

