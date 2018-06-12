---
title: 有关 Microsoft Office InfoPath 主互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2007 主互操作程序集，InfoPath 主互操作程序集，Pia [InfoPath 2007]，主互操作程序集 [InfoPath 2007]
localization_priority: Normal
ms.assetid: 1b3ae03c-6951-49e4-a489-4712d3f7ba72
description: 若要支持使用托管代码如 Visual C# 和 Visual Basic 的语言的 InfoPath 解决方案的创建，InfoPath 安装程序中的.NET 可编程性支持选项，请安装三个互操作程序集。
ms.openlocfilehash: b6b37254773d758dc064e22045d68f29febe7bbe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773881"
---
# <a name="about-the-microsoft-office-infopath-primary-interop-assembly"></a><span data-ttu-id="999a4-104">有关 Microsoft Office InfoPath 主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="999a4-104">About the Microsoft Office InfoPath Primary Interop Assembly</span></span>

<span data-ttu-id="999a4-105">作为公开作为 COM 接口的外部自动化其可编程性接口的组件对象模型 (COM) 应用程序生成 InfoPath 应用程序。</span><span class="sxs-lookup"><span data-stu-id="999a4-105">The InfoPath application is built as a Component Object Model (COM) application that exposes its programmability interfaces for external automation as COM interfaces.</span></span> <span data-ttu-id="999a4-106">若要支持使用托管代码如 Visual C# 和 Visual Basic 的语言的 InfoPath 解决方案的创建，InfoPath 安装程序中的 **.NET 可编程性支持**选项，请安装三个互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="999a4-106">To support the creation of InfoPath solutions that use managed-code languages such as Visual C# and Visual Basic, the **.NET Programmability Support** option in the InfoPath setup program installs three interop assemblies.</span></span> <span data-ttu-id="999a4-107">互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。</span><span class="sxs-lookup"><span data-stu-id="999a4-107">Interop assemblies are .NET assemblies that act as a bridge between managed and unmanaged code, mapping COM object members to equivalent .NET managed members.</span></span> 
  
<span data-ttu-id="999a4-108">InfoPath 安装的三个互操作程序集的文件命名为：</span><span class="sxs-lookup"><span data-stu-id="999a4-108">The files for the three interop assemblies installed by InfoPath are named:</span></span>
  
- <span data-ttu-id="999a4-109">Microsoft.Office.Interop.InfoPath.dll</span><span class="sxs-lookup"><span data-stu-id="999a4-109">Microsoft.Office.Interop.InfoPath.dll</span></span>
    
- <span data-ttu-id="999a4-110">Microsoft.Office.Interop.InfoPath.SemiTrust.dll</span><span class="sxs-lookup"><span data-stu-id="999a4-110">Microsoft.Office.Interop.InfoPath.SemiTrust.dll</span></span>
    
- <span data-ttu-id="999a4-111">Microsoft.Office.Interop.InfoPath.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="999a4-111">Microsoft.Office.Interop.InfoPath.Xml.dll</span></span>
    
<span data-ttu-id="999a4-112">本主题讨论通过 Microsoft.Office.Interop.InfoPath 互操作程序集，以独占方式的外部自动化代码用于公开的对象模型。</span><span class="sxs-lookup"><span data-stu-id="999a4-112">This topic discusses the object model exposed through the Microsoft.Office.Interop.InfoPath interop assembly, which is used exclusively for external automation code.</span></span> <span data-ttu-id="999a4-113">有关信息 Microsoft.Office.Interop.InfoPath.SemiTrust 程序集，用于以独占方式编写和运行托管的代码的 InfoPath 表单模板 (.xsn) 内从运行，请参阅[InfoPath 2003 兼容对象模型](http://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="999a4-113">For information on the Microsoft.Office.Interop.InfoPath.SemiTrust assembly, which is used exclusively for writing and running managed code that runs from within InfoPath form templates (.xsn), see [InfoPath 2003 Compatible Object Models](http://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx).</span></span>
  
## <a name="important-installation-information"></a><span data-ttu-id="999a4-114">重要安装信息</span><span class="sxs-lookup"><span data-stu-id="999a4-114">Important Installation Information</span></span>

<span data-ttu-id="999a4-115">InfoPath 安装程序的默认安装选项安装 Microsoft.Office.Interop.InfoPath 的程序集在全局程序集缓存 (GAC)，可以查看的内容，从 C:\Windows\Assembly 文件夹 （或在 C:\Windows\assembly\GAC_MSIL 直接查看文件系统时)。</span><span class="sxs-lookup"><span data-stu-id="999a4-115">The default installation option of the InfoPath setup program installs the Microsoft.Office.Interop.InfoPath assembly in the Global Assembly Cache (GAC), the contents of which can be viewed from the C:\Windows\Assembly folder (or in C:\Windows\assembly\GAC_MSIL when viewing the file system directly).</span></span> <span data-ttu-id="999a4-116">此程序集被称为"Microsoft Office InfoPath 主互操作程序集"这通常用于结合 Microsoft.Office.Interop.InfoPath.Xml 程序集，也在 GAC 中安装，以自动执行 InfoPath 应用程序使用托管的代码的外部应用程序。</span><span class="sxs-lookup"><span data-stu-id="999a4-116">This assembly is referred to as the "Microsoft Office InfoPath Primary Interop Assembly" and is often used in conjunction with the Microsoft.Office.Interop.InfoPath.Xml assembly, which is also installed in the GAC, to automate the InfoPath application from external applications that use managed code.</span></span> <span data-ttu-id="999a4-117">有关 Microsoft.Office.Interop.InfoPath.Xml 程序集的信息，请参阅[有关 InfoPath XML 互操作程序集](about-the-infopath-xml-interop-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="999a4-117">For information about the Microsoft.Office.Interop.InfoPath.Xml assembly, see [About the InfoPath XML Interop Assembly](about-the-infopath-xml-interop-assembly.md).</span></span>
  
<span data-ttu-id="999a4-118">如果 Microsoft.Office.Interop.InfoPath 程序集不是在 GAC 中可见的您应确认 InfoPath 已正确安装。</span><span class="sxs-lookup"><span data-stu-id="999a4-118">If the Microsoft.Office.Interop.InfoPath assembly is not visible in the GAC, you should confirm that InfoPath was installed correctly.</span></span> <span data-ttu-id="999a4-119">默认情况下，安装程序中的 **.NET 可编程性支持**选项设置为**从本机运行**只要.NET Framework 1.1 版可再发行软件包、.NET Framework 1.1 软件开发工具包 (SDK) 或更高版本的.NET framework运行安装程序之前安装。</span><span class="sxs-lookup"><span data-stu-id="999a4-119">By default, the **.NET Programmability Support** option in the setup program is set to **Run from My Computer** as long as the .NET Framework 1.1 Redistributable, .NET Framework 1.1 Software Development Kit (SDK), or a later version of the .NET Framework is installed before running setup.</span></span> <span data-ttu-id="999a4-120">如果这些互操作程序集不可用您的计算机上，您必须确认.NET Framework 1.1 或更高版本安装，则，然后使用**程序和功能**从**控制面板**通过设置 **.NET 可编程性更改安装程序支持**下为**从本机运行** **Microsoft Office InfoPath**选项。</span><span class="sxs-lookup"><span data-stu-id="999a4-120">If these interop assemblies are not available on your computer, you must confirm that .NET Framework 1.1 or later is installed, and then use **Programs and Features** from the **Control Panel** to change setup by setting the **.NET Programmability Support** option under **Microsoft Office InfoPath** to **Run from My Computer**.</span></span>
  
<span data-ttu-id="999a4-121">下载.NET Framework 1.1 版可再发行软件包的信息，请参阅[.NET Framework 1.1 版可再发行软件包](http://msdn.microsoft.com/netframework/technologyinfo/redist/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="999a4-121">For information on downloading the .NET Framework 1.1 Redistributable, see [.NET Framework 1.1 Redistributable](http://msdn.microsoft.com/netframework/technologyinfo/redist/default.aspx).</span></span>
  
## <a name="the-microsoftofficeinteropinfopath-namespace"></a><span data-ttu-id="999a4-122">Microsoft.Office.Interop.InfoPath Namespace</span><span class="sxs-lookup"><span data-stu-id="999a4-122">The Microsoft.Office.Interop.InfoPath Namespace</span></span>

<span data-ttu-id="999a4-123">尽管编写的过程管理给定任务的代码是非常类似于执行相同的应用程序或 JScript 中，查看**Microsoft.Office.Interop.InfoPath**时公开的对象模型使用如 Visual Basic 语言的任务从**对象浏览器**在 Microsoft Visual Studio 中的命名空间查找复杂。</span><span class="sxs-lookup"><span data-stu-id="999a4-123">Although the process of writing managed code for a given task is very similar to performing the same task using a language such as Visual Basic for Applications or JScript, the object model exposed when viewing the **Microsoft.Office.Interop.InfoPath** namespace from the **Object Browser** in Microsoft Visual Studio looks more complex.</span></span> <span data-ttu-id="999a4-124">这是因为使用.NET Framework 的互操作性要求公开的所有公共接口，以及所需的.NET Framework 本身某些其他构造 COM 服务器。</span><span class="sxs-lookup"><span data-stu-id="999a4-124">This is because interoperability with the .NET Framework requires a COM server to expose all of its public interfaces, as well as some additional constructs required by the .NET Framework itself.</span></span> <span data-ttu-id="999a4-125">有关如何及使用原因互操作程序集公开的对象模型显示更复杂的详细信息，请参阅[InfoPath 2003 兼容对象模型](http://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx)主题的"如何 COM 对象是公开为托管代码"部分。</span><span class="sxs-lookup"><span data-stu-id="999a4-125">For more information on how and why the object model exposed by an interop assembly appears more complex, see the "How COM Objects are Exposed to Managed Code" section of the [InfoPath 2003 Compatible Object Models](http://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx) topic.</span></span> 
  
### <a name="using-intellisense"></a><span data-ttu-id="999a4-126">使用 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="999a4-126">Using IntelliSense</span></span>

<span data-ttu-id="999a4-127">本节中的示例假定您已建立 Microsoft.Office.Interop.InfoPath 和 Microsoft.Office.Interop.InfoPath.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="999a4-127">The examples in this section assume that you have established references to the Microsoft.Office.Interop.InfoPath and Microsoft.Office.Interop.InfoPath.Xml assemblies.</span></span> <span data-ttu-id="999a4-128">有关如何设置引用和其他外部自动化示例的信息，请参阅[外部自动化方案和示例](external-automation-scenarios-and-examples.md)。</span><span class="sxs-lookup"><span data-stu-id="999a4-128">For information on how to set references and additional external automation examples, see [External Automation Scenarios and Examples](external-automation-scenarios-and-examples.md).</span></span>
  
<span data-ttu-id="999a4-129">外部自动化代码中使用 Microsoft 智能感知语句结束之前，必须创建[Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx)类的实例的对象变量，如下面的代码行所示。</span><span class="sxs-lookup"><span data-stu-id="999a4-129">Before you can use Microsoft IntelliSense statement completion in external automation code, you must create an object variable for an instance of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx) class as shown in the following line of code.</span></span> 
  
```cs
Application myApp = 
    new Microsoft.Office.Interop.InfoPath.Application();
```

```vb
Dim myApp As Application = _
    New Microsoft.Office.Interop.InfoPath.Application()
```

<span data-ttu-id="999a4-130">创建对象变量后, 键入跟一个句点，变量名称时下拉列表将显示**应用程序**类的成员的选择。</span><span class="sxs-lookup"><span data-stu-id="999a4-130">After creating the object variable, when you type the variable name followed by a period, a drop-down list is displayed with members of the **Application** class to select.</span></span> 
  
<span data-ttu-id="999a4-131">若要使用 InfoPath 表单，声明类型[XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocument.aspx) ，对象变量，然后将其初始化通过从**Application**对象的变量中下面的代码行所示的[XDocuments](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocuments.aspx)集合中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="999a4-131">To work with an InfoPath form, declare an object variable of type [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocument.aspx) , and then initialize it by opening the form from the [XDocuments](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocuments.aspx) collection of the **Application** object variable as shown in the following line of code.</span></span> 
  
```cs
XDocument myXDoc = myApp.XDocuments.Open(
    "c:\\temp\\Form1.xml",
    (int) XdDocumentVersionMode.xdFailOnVersionOlder);
```

```vb
Dim myXDoc As XDocument = myApp.XDocuments.Open( _
    "c:\\temp\\Form1.xml", _
    XdDocumentVersionMode.xdFailOnVersionOlder)
```

<span data-ttu-id="999a4-132">键入一段时间后跟变量的名称时，将显示**XDocument**类的成员的 IntelliSense 语句完成下拉列表。</span><span class="sxs-lookup"><span data-stu-id="999a4-132">The IntelliSense statement completion drop-down list for members of the **XDocument** class will be displayed when you type the name of the variable followed by a period.</span></span> 
  
<span data-ttu-id="999a4-133">若要使用的窗体使用 Microsoft XML Core Services (MSXML) 的基础 XML 文档的内容，您必须创建[IXMLDOMDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Xml.IXMLDOMDocument2.aspx) ，类型的变量，然后使用**XDocument**类的[DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._XDocument2.DOM.aspx)属性分配 XML文档对象模型 (DOM) 的窗体给该变量。</span><span class="sxs-lookup"><span data-stu-id="999a4-133">To work with the contents of the underlying XML document for the form using Microsoft XML Core Services (MSXML), you must create a variable of type [IXMLDOMDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Xml.IXMLDOMDocument2.aspx) , and then use the [DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._XDocument2.DOM.aspx) property of the **XDocument** class to assign the XML Document Object Model (DOM) of the form to that variable.</span></span> 
  
```cs
IXMLDOMDocument2 doc= myXDoc.DOM as IXMLDOMDocument2;
```

```vb
Dim doc As IXMLDOMDocument2 = myXDoc.DOM
```

<span data-ttu-id="999a4-134">当键入跟一个句点，以便您可以使用 MSXML 来处理 XML 文档变量的名称时，将显示**IXMLDOMDocument2**类的成员的 IntelliSense 语句完成下拉列表。</span><span class="sxs-lookup"><span data-stu-id="999a4-134">The IntelliSense statement completion drop-down list for members of the **IXMLDOMDocument2** class will be displayed when you type the name of the variable followed by a period, which allows you to use MSXML to work with the XML document.</span></span> 
  
### <a name="using-the-class-library-reference-documentation"></a><span data-ttu-id="999a4-135">使用类库引用文档</span><span class="sxs-lookup"><span data-stu-id="999a4-135">Using the Class Library Reference Documentation</span></span>

<span data-ttu-id="999a4-136">[Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.aspx)命名空间类库参考文档的组织反映 coclass 接口和它们实现的继承的接口之间的关系。</span><span class="sxs-lookup"><span data-stu-id="999a4-136">The organization of the [Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.aspx) namespace Class Library reference documentation reflects the relationships between coclass interfaces and the inherited interfaces they implement.</span></span> 
  
<span data-ttu-id="999a4-137">当打开一个 coclass 接口，[应用程序](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx)，如主题的链接到的主题的开头的接口说明 coclass 接口的成员将显示空主题。</span><span class="sxs-lookup"><span data-stu-id="999a4-137">When you open a topic for a coclass interface, such as [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx) , the link to the members of the coclass interface following the description of the interface at the beginning of the topic displays an empty topic.</span></span> <span data-ttu-id="999a4-138">若要显示由 coclass 接口实现的成员的列表，必须打开由 coclass 继承的最新接口的主题，然后打开其成员表。</span><span class="sxs-lookup"><span data-stu-id="999a4-138">To display the list of members that are implemented by the coclass interface, you must open the topic for the most recent interface that is inherited by the coclass, and then open the table of its members.</span></span> <span data-ttu-id="999a4-139">将在 coclass 接口主题中"备注"一节的开头提供指向继承接口的链接。</span><span class="sxs-lookup"><span data-stu-id="999a4-139">A link to the inherited interface is provided at the beginning of the Remarks section in the coclass interface topic.</span></span> 
  
<span data-ttu-id="999a4-140">当您在 Visual Studio 代码编辑器中按 F1 时，行为类似，只是在其调用 F1 帮助的成员将直接显示，因为您最常使用接口的成员。</span><span class="sxs-lookup"><span data-stu-id="999a4-140">When you press F1 in the Visual Studio Code Editor, the behavior is similar, except that the member on which you invoke F1 Help will be displayed directly, because you are most typically working with members of an interface.</span></span> <span data-ttu-id="999a4-141">但实际上可以从版本控制接口实现成员，第一次遇到这种情况时可能容易混淆。</span><span class="sxs-lookup"><span data-stu-id="999a4-141">However, the fact that a member can be implemented from a versioned interface may be confusing the first time you encounter it.</span></span> <span data-ttu-id="999a4-142">例如，如果键入  `myXDocument.UI.Alert`，然后将光标放在  `Alert` 上并按 F1，则将显示标题为"UI2.Alert 方法"的主题。</span><span class="sxs-lookup"><span data-stu-id="999a4-142">For example, if you type  `myXDocument.UI.Alert` and place the cursor on  `Alert` and press F1, a topic titled "UI2.Alert Method" is displayed.</span></span> <span data-ttu-id="999a4-143">这是因为 **Alert** 方法是 **UI2** 接口的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="999a4-143">This is because the **Alert** method is an implementation of a member of the **UI2** interface.</span></span> 
  
### <a name="passing-optional-parameters-to-infopath-object-model-members"></a><span data-ttu-id="999a4-144">将可选参数传递给 InfoPath 对象模型成员</span><span class="sxs-lookup"><span data-stu-id="999a4-144">Passing Optional Parameters to InfoPath Object Model Members</span></span>

<span data-ttu-id="999a4-145">如果 InfoPath 对象模型成员包含可选参数，并且您不指定该参数的值，您必须通过该参数的**Type.Missing**字段。</span><span class="sxs-lookup"><span data-stu-id="999a4-145">If an InfoPath object model member contains an optional parameter, and you do not specify a value for that parameter, you must pass the **Type.Missing** field for that parameter.</span></span> <span data-ttu-id="999a4-146">如果在忽略实际值时未能传递 **Type.Missing** 域，将会导致生成错误。</span><span class="sxs-lookup"><span data-stu-id="999a4-146">Failure to pass the **Type.Missing** field when an actual value is omitted will result in a build error.</span></span> <span data-ttu-id="999a4-147">这是用 C# 和 Visual Basic 编写的代码，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="999a4-147">This is true for code written in both C# and Visual Basic.</span></span> <span data-ttu-id="999a4-148">例如， [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.View2.SelectNodes.aspx) 接口的 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ViewObject.aspx) 方法包含两个可选参数：  _varEndNode_ 和  _varViewContext_。</span><span class="sxs-lookup"><span data-stu-id="999a4-148">For example, the [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.View2.SelectNodes.aspx) method of the [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ViewObject.aspx) interface includes two optional parameters:  _varEndNode_ and  _varViewContext_.</span></span> <span data-ttu-id="999a4-149">如果某代码行未指定这些可选参数的实际值，则会发生类似如下示例的情况。</span><span class="sxs-lookup"><span data-stu-id="999a4-149">A line of code that does not specify actual values for these optional parameters should look like the following examples.</span></span>
  
```cs
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing);
```

```vb
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing)
```

## <a name="see-also"></a><span data-ttu-id="999a4-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="999a4-150">See also</span></span>

- [<span data-ttu-id="999a4-151">外部自动化方案和示例</span><span class="sxs-lookup"><span data-stu-id="999a4-151">External automation scenarios and examples</span></span>](external-automation-scenarios-and-examples.md)

