---
title: 关于 Microsoft Office InfoPath 主互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2007、主互操作程序集、InfoPath 主互操作程序集、pia [InfoPath 2007]、主互操作程序集 [InfoPath 2007]
localization_priority: Normal
ms.assetid: 1b3ae03c-6951-49e4-a489-4712d3f7ba72
description: '若要支持创建使用托管代码语言 (如 visual c # 和 visual Basic) 的 infopath 解决方案, infopath 安装程序中的 .net 可编程性支持选项将安装三个互操作程序集。'
ms.openlocfilehash: 51773ad46b1371c410c4249e13a489f0c5550cd1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310134"
---
# <a name="about-the-microsoft-office-infopath-primary-interop-assembly"></a><span data-ttu-id="ca080-104">关于 Microsoft Office InfoPath 主互操作程序集</span><span class="sxs-lookup"><span data-stu-id="ca080-104">About the Microsoft Office InfoPath Primary Interop Assembly</span></span>

<span data-ttu-id="ca080-105">InfoPath 应用程序构建为组件对象模型 (COM) 应用程序, 该应用程序公开其作为 COM 接口的外部自动化的可编程性接口。</span><span class="sxs-lookup"><span data-stu-id="ca080-105">The InfoPath application is built as a Component Object Model (COM) application that exposes its programmability interfaces for external automation as COM interfaces.</span></span> <span data-ttu-id="ca080-106">若要支持创建使用托管代码语言 (如 visual c # 和 visual Basic) 的 infopath 解决方案, infopath 安装程序中的 **.net 可编程性支持**选项将安装三个互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="ca080-106">To support the creation of InfoPath solutions that use managed-code languages such as Visual C# and Visual Basic, the **.NET Programmability Support** option in the InfoPath setup program installs three interop assemblies.</span></span> <span data-ttu-id="ca080-107">互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。</span><span class="sxs-lookup"><span data-stu-id="ca080-107">Interop assemblies are .NET assemblies that act as a bridge between managed and unmanaged code, mapping COM object members to equivalent .NET managed members.</span></span> 
  
<span data-ttu-id="ca080-108">InfoPath 安装的三个互操作程序集的文件命名为：</span><span class="sxs-lookup"><span data-stu-id="ca080-108">The files for the three interop assemblies installed by InfoPath are named:</span></span>
  
- <span data-ttu-id="ca080-109">Microsoft.Office.Interop.InfoPath.dll</span><span class="sxs-lookup"><span data-stu-id="ca080-109">Microsoft.Office.Interop.InfoPath.dll</span></span>
    
- <span data-ttu-id="ca080-110">Microsoft.Office.Interop.InfoPath.SemiTrust.dll</span><span class="sxs-lookup"><span data-stu-id="ca080-110">Microsoft.Office.Interop.InfoPath.SemiTrust.dll</span></span>
    
- <span data-ttu-id="ca080-111">Microsoft.Office.Interop.InfoPath.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="ca080-111">Microsoft.Office.Interop.InfoPath.Xml.dll</span></span>
    
<span data-ttu-id="ca080-112">本主题讨论通过 Microsoft. InfoPath 互操作程序集公开的对象模型, 专门用于外部自动化代码。</span><span class="sxs-lookup"><span data-stu-id="ca080-112">This topic discusses the object model exposed through the Microsoft.Office.Interop.InfoPath interop assembly, which is used exclusively for external automation code.</span></span> <span data-ttu-id="ca080-113">有关 SemiTrust 程序集 (专门用于编写和运行在 InfoPath 表单模板 (.xsn) 中运行的托管代码) 的信息, 请参阅[InfoPath 2003 兼容对象模型](https://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca080-113">For information on the Microsoft.Office.Interop.InfoPath.SemiTrust assembly, which is used exclusively for writing and running managed code that runs from within InfoPath form templates (.xsn), see [InfoPath 2003 Compatible Object Models](https://msdn.microsoft.com/library/e4511af6-d7e7-44ad-a50d-1b7ee04f8215%28Office.15%29.aspx).</span></span>
  
## <a name="important-installation-information"></a><span data-ttu-id="ca080-114">重要安装信息</span><span class="sxs-lookup"><span data-stu-id="ca080-114">Important Installation Information</span></span>

<span data-ttu-id="ca080-115">infopath 安装程序的默认安装选项将在全局程序集缓存 (GAC) 中安装 C:\Windows\Assembly 程序集, 可以从 "" 文件夹 (或在 C:\Windows\assembly\GAC_ 中查看该程序集的内容)。直接查看文件系统时的 MSIL)。</span><span class="sxs-lookup"><span data-stu-id="ca080-115">The default installation option of the InfoPath setup program installs the Microsoft.Office.Interop.InfoPath assembly in the Global Assembly Cache (GAC), the contents of which can be viewed from the C:\Windows\Assembly folder (or in C:\Windows\assembly\GAC_MSIL when viewing the file system directly).</span></span> <span data-ttu-id="ca080-116">此程序集称为 "microsoft office InfoPath 主互操作程序集", 通常与位于 GAC 中的 "microsoft. Xml 程序集" 一起使用, 以自动执行 InfoPath 应用程序使用托管代码的外部应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca080-116">This assembly is referred to as the "Microsoft Office InfoPath Primary Interop Assembly" and is often used in conjunction with the Microsoft.Office.Interop.InfoPath.Xml assembly, which is also installed in the GAC, to automate the InfoPath application from external applications that use managed code.</span></span> <span data-ttu-id="ca080-117">有关 Microsoft. Xml 程序集的信息, 请参阅[关于 InfoPath Xml 互操作程序集](about-the-infopath-xml-interop-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="ca080-117">For information about the Microsoft.Office.Interop.InfoPath.Xml assembly, see [About the InfoPath XML Interop Assembly](about-the-infopath-xml-interop-assembly.md).</span></span>
  
<span data-ttu-id="ca080-118">如果 GAC 中不显示 "Microsoft.. infopath 程序集", 则应确认已正确安装 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="ca080-118">If the Microsoft.Office.Interop.InfoPath assembly is not visible in the GAC, you should confirm that InfoPath was installed correctly.</span></span> <span data-ttu-id="ca080-119">默认情况下, 安装程序中的 **.net 可编程性支持**选项设置为 "**从本机运行**", 只要 .net framework 1.1 可再发行的 .net framework 1.1 软件开发工具包 (SDK) 或 .net framework 的更高版本。在运行安装程序之前已安装。</span><span class="sxs-lookup"><span data-stu-id="ca080-119">By default, the **.NET Programmability Support** option in the setup program is set to **Run from My Computer** as long as the .NET Framework 1.1 Redistributable, .NET Framework 1.1 Software Development Kit (SDK), or a later version of the .NET Framework is installed before running setup.</span></span> <span data-ttu-id="ca080-120">如果这些互操作程序集在您的计算机上不可用, 则必须确认已安装 .net Framework 1.1 或更高版本, 然后使用 "**控制面板**" 中的 "**程序和功能**" 通过设置 .net 可编程性更改安装程序\*\*\*\*" **Microsoft Office InfoPath** " 下的 "支持 **" 选项从 "我的电脑" 运行**。</span><span class="sxs-lookup"><span data-stu-id="ca080-120">If these interop assemblies are not available on your computer, you must confirm that .NET Framework 1.1 or later is installed, and then use **Programs and Features** from the **Control Panel** to change setup by setting the **.NET Programmability Support** option under **Microsoft Office InfoPath** to **Run from My Computer**.</span></span>
  
<span data-ttu-id="ca080-121">有关下载 .net framework 1.1 可再发行组件的信息, 请参阅[.net framework 1.1 可再发行组件](https://www.microsoft.com/en-us/download/details.aspx?id=26)。</span><span class="sxs-lookup"><span data-stu-id="ca080-121">For information about downloading the .NET Framework 1.1 Redistributable, see [.NET Framework 1.1 Redistributable](https://www.microsoft.com/en-us/download/details.aspx?id=26).</span></span>
  
## <a name="the-microsoftofficeinteropinfopath-namespace"></a><span data-ttu-id="ca080-122">Microsoft. InfoPath 命名空间</span><span class="sxs-lookup"><span data-stu-id="ca080-122">The Microsoft.Office.Interop.InfoPath Namespace</span></span>

<span data-ttu-id="ca080-123">尽管为给定任务编写托管代码的过程非常类似于使用 Visual Basic for Applications 或 JScript 等语言执行相同的任务, 但在查看**Microsoft. InfoPath**时公开的对象模型来自 Microsoft Visual Studio 中的**对象浏览器**的命名空间看起来更复杂。</span><span class="sxs-lookup"><span data-stu-id="ca080-123">Although the process of writing managed code for a given task is very similar to performing the same task using a language such as Visual Basic for Applications or JScript, the object model exposed when viewing the **Microsoft.Office.Interop.InfoPath** namespace from the **Object Browser** in Microsoft Visual Studio looks more complex.</span></span> <span data-ttu-id="ca080-124">这是因为与 .net framework 的互操作性要求 COM 服务器公开其所有公共接口以及 .net Framework 本身所需的其他一些构造。</span><span class="sxs-lookup"><span data-stu-id="ca080-124">This is because interoperability with the .NET Framework requires a COM server to expose all of its public interfaces, as well as some additional constructs required by the .NET Framework itself.</span></span> <span data-ttu-id="ca080-125">有关互操作程序集公开的对象模型的方式和原因的详细信息, 请参阅[InfoPath 2003 兼容对象模型](../form-templates/infopath-2003-compatible-object-models.md)主题中的 "如何将 COM 对象公开给托管代码" 部分。</span><span class="sxs-lookup"><span data-stu-id="ca080-125">For more information on how and why the object model exposed by an interop assembly appears more complex, see the "How COM Objects are Exposed to Managed Code" section of the [InfoPath 2003 Compatible Object Models](../form-templates/infopath-2003-compatible-object-models.md) topic.</span></span> 
  
### <a name="using-intellisense"></a><span data-ttu-id="ca080-126">使用 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="ca080-126">Using IntelliSense</span></span>

<span data-ttu-id="ca080-127">本节中的示例假定您已建立对 "microsoft. infopath" 和 "microsoft. Xml 程序集" 的引用。</span><span class="sxs-lookup"><span data-stu-id="ca080-127">The examples in this section assume that you have established references to the Microsoft.Office.Interop.InfoPath and Microsoft.Office.Interop.InfoPath.Xml assemblies.</span></span> <span data-ttu-id="ca080-128">若要了解如何设置引用和其他外部自动化示例, 请参阅[外部自动化方案和示例](external-automation-scenarios-and-examples.md)。</span><span class="sxs-lookup"><span data-stu-id="ca080-128">For information on how to set references and additional external automation examples, see [External Automation Scenarios and Examples](external-automation-scenarios-and-examples.md).</span></span>
  
<span data-ttu-id="ca080-129">在外部自动化代码中使用 Microsoft IntelliSense 语句完成功能之前, 必须为[Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx)类的实例创建一个对象变量, 如以下代码行所示。</span><span class="sxs-lookup"><span data-stu-id="ca080-129">Before you can use Microsoft IntelliSense statement completion in external automation code, you must create an object variable for an instance of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx) class as shown in the following line of code.</span></span> 
  
```cs
Application myApp = 
    new Microsoft.Office.Interop.InfoPath.Application();
```

```vb
Dim myApp As Application = _
    New Microsoft.Office.Interop.InfoPath.Application()
```

<span data-ttu-id="ca080-130">创建对象变量后, 当您键入变量名称后跟一个句点时, 将显示一个下拉列表, 其中包含**应用程序**类的成员以选择。</span><span class="sxs-lookup"><span data-stu-id="ca080-130">After creating the object variable, when you type the variable name followed by a period, a drop-down list is displayed with members of the **Application** class to select.</span></span> 
  
<span data-ttu-id="ca080-131">若要使用 InfoPath 表单, 请声明[XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocument.aspx)类型的对象变量, 然后通过从**Application**对象变量的[XDocuments](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocuments.aspx)集合中打开该窗体来对其进行初始化, 如以下代码行所示。</span><span class="sxs-lookup"><span data-stu-id="ca080-131">To work with an InfoPath form, declare an object variable of type [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocument.aspx) , and then initialize it by opening the form from the [XDocuments](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.XDocuments.aspx) collection of the **Application** object variable as shown in the following line of code.</span></span> 
  
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

<span data-ttu-id="ca080-132">当您键入变量的名称后跟一个句点时, 将显示**XDocument**类的成员的智能感知语句完成下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ca080-132">The IntelliSense statement completion drop-down list for members of the **XDocument** class will be displayed when you type the name of the variable followed by a period.</span></span> 
  
<span data-ttu-id="ca080-133">若要使用 Microsoft XML Core Services (MSXML) 对表单的基础 XML 文档的内容进行操作, 必须创建一个类型为[IXMLDOMDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Xml.IXMLDOMDocument2.aspx)的变量, 然后使用**XDocument**类的[DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._XDocument2.DOM.aspx)属性将 XML 分配给将表单的文档对象模型 (DOM) 到该变量。</span><span class="sxs-lookup"><span data-stu-id="ca080-133">To work with the contents of the underlying XML document for the form using Microsoft XML Core Services (MSXML), you must create a variable of type [IXMLDOMDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Xml.IXMLDOMDocument2.aspx) , and then use the [DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._XDocument2.DOM.aspx) property of the **XDocument** class to assign the XML Document Object Model (DOM) of the form to that variable.</span></span> 
  
```cs
IXMLDOMDocument2 doc= myXDoc.DOM as IXMLDOMDocument2;
```

```vb
Dim doc As IXMLDOMDocument2 = myXDoc.DOM
```

<span data-ttu-id="ca080-134">当您键入变量的名称后跟一个句点时, 将显示**IXMLDOMDocument2**类的成员的智能感知语句完成下拉列表, 这样您就可以使用 MSXML 来处理 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="ca080-134">The IntelliSense statement completion drop-down list for members of the **IXMLDOMDocument2** class will be displayed when you type the name of the variable followed by a period, which allows you to use MSXML to work with the XML document.</span></span> 
  
### <a name="using-the-class-library-reference-documentation"></a><span data-ttu-id="ca080-135">使用类库引用文档</span><span class="sxs-lookup"><span data-stu-id="ca080-135">Using the Class Library Reference Documentation</span></span>

<span data-ttu-id="ca080-136">[Microsoft. InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.aspx)命名空间类库参考文档的组织反映 coclass 接口与它们实现的继承接口之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ca080-136">The organization of the [Microsoft.Office.Interop.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.aspx) namespace Class Library reference documentation reflects the relationships between coclass interfaces and the inherited interfaces they implement.</span></span> 
  
<span data-ttu-id="ca080-137">当您打开组件类接口的主题 (如[Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx) ) 时, 指向主题开头的接口说明后面的组件类接口的成员的链接将显示一个空主题。</span><span class="sxs-lookup"><span data-stu-id="ca080-137">When you open a topic for a coclass interface, such as [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.Application.aspx) , the link to the members of the coclass interface following the description of the interface at the beginning of the topic displays an empty topic.</span></span> <span data-ttu-id="ca080-138">若要显示由 coclass 接口实现的成员的列表，必须打开由 coclass 继承的最新接口的主题，然后打开其成员表。</span><span class="sxs-lookup"><span data-stu-id="ca080-138">To display the list of members that are implemented by the coclass interface, you must open the topic for the most recent interface that is inherited by the coclass, and then open the table of its members.</span></span> <span data-ttu-id="ca080-139">将在 coclass 接口主题中"备注"一节的开头提供指向继承接口的链接。</span><span class="sxs-lookup"><span data-stu-id="ca080-139">A link to the inherited interface is provided at the beginning of the Remarks section in the coclass interface topic.</span></span> 
  
<span data-ttu-id="ca080-140">在 Visual Studio Code 编辑器中按 F1 时, 行为与此类似, 但调用 F1 帮助的成员将直接显示, 因为您最常使用接口的成员。</span><span class="sxs-lookup"><span data-stu-id="ca080-140">When you press F1 in the Visual Studio Code Editor, the behavior is similar, except that the member on which you invoke F1 Help will be displayed directly, because you are most typically working with members of an interface.</span></span> <span data-ttu-id="ca080-141">但实际上可以从版本控制接口实现成员，第一次遇到这种情况时可能容易混淆。</span><span class="sxs-lookup"><span data-stu-id="ca080-141">However, the fact that a member can be implemented from a versioned interface may be confusing the first time you encounter it.</span></span> <span data-ttu-id="ca080-142">例如，如果键入  `myXDocument.UI.Alert`，然后将光标放在  `Alert` 上并按 F1，则将显示标题为"UI2.Alert 方法"的主题。</span><span class="sxs-lookup"><span data-stu-id="ca080-142">For example, if you type  `myXDocument.UI.Alert` and place the cursor on  `Alert` and press F1, a topic titled "UI2.Alert Method" is displayed.</span></span> <span data-ttu-id="ca080-143">这是因为 **Alert** 方法是 **UI2** 接口的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="ca080-143">This is because the **Alert** method is an implementation of a member of the **UI2** interface.</span></span> 
  
### <a name="passing-optional-parameters-to-infopath-object-model-members"></a><span data-ttu-id="ca080-144">将可选参数传递给 InfoPath 对象模型成员</span><span class="sxs-lookup"><span data-stu-id="ca080-144">Passing Optional Parameters to InfoPath Object Model Members</span></span>

<span data-ttu-id="ca080-145">如果 InfoPath 对象模型成员包含一个可选参数, 而您没有为该参数指定值, 则必须为该参数传递**类型。缺少**对应于该参数的 field。</span><span class="sxs-lookup"><span data-stu-id="ca080-145">If an InfoPath object model member contains an optional parameter, and you do not specify a value for that parameter, you must pass the **Type.Missing** field for that parameter.</span></span> <span data-ttu-id="ca080-146">如果在忽略实际值时未能传递 **Type.Missing** 域，将会导致生成错误。</span><span class="sxs-lookup"><span data-stu-id="ca080-146">Failure to pass the **Type.Missing** field when an actual value is omitted will result in a build error.</span></span> <span data-ttu-id="ca080-147">对于以 c # 和 Visual Basic 编写的代码, 都是如此。</span><span class="sxs-lookup"><span data-stu-id="ca080-147">This is true for code written in both C# and Visual Basic.</span></span> <span data-ttu-id="ca080-148">例如， [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.View2.SelectNodes.aspx) 接口的 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ViewObject.aspx) 方法包含两个可选参数：  _varEndNode_ 和  _varViewContext_。</span><span class="sxs-lookup"><span data-stu-id="ca080-148">For example, the [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.View2.SelectNodes.aspx) method of the [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ViewObject.aspx) interface includes two optional parameters:  _varEndNode_ and  _varViewContext_.</span></span> <span data-ttu-id="ca080-149">如果某代码行未指定这些可选参数的实际值，则会发生类似如下示例的情况。</span><span class="sxs-lookup"><span data-stu-id="ca080-149">A line of code that does not specify actual values for these optional parameters should look like the following examples.</span></span>
  
```cs
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing);
```

```vb
myXDocument.View.SelectNodes(group1, Type.Missing, Type.Missing)
```

## <a name="see-also"></a><span data-ttu-id="ca080-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca080-150">See also</span></span>

- [<span data-ttu-id="ca080-151">外部自动化方案和示例</span><span class="sxs-lookup"><span data-stu-id="ca080-151">External automation scenarios and examples</span></span>](external-automation-scenarios-and-examples.md)

