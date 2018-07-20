---
title: 访问应用程序数据
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- application names [infopath 2007],accessing application name [InfoPath 2007],InfoPath 2007, accessing application data,accessing application version [InfoPath 2007],application versions [InfoPath 2007],language IDs [InfoPath 2007],LCID [InfoPath 2007],application data [InfoPath 2007],accessing language ID [InfoPath 2007]
localization_priority: Normal
ms.assetid: 2698d059-9955-4eec-85a6-79defb64e07e
description: InfoPath 托管代码对象模型所提供的对象和集合可以用来访问有关 InfoPath 应用程序的信息，其中包括有关表单的基础 XML 文档以及表单定义 (.xsf) 文件的信息。这些数据通过 InfoPath 对象模型分层结构的顶级对象（该对象通过使用 Application 类来实例化）来访问。
ms.openlocfilehash: 3c3f6be4e90e292eb572da836bca0a8dcf1883cd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773968"
---
# <a name="access-application-data"></a><span data-ttu-id="974b5-105">访问应用程序数据</span><span class="sxs-lookup"><span data-stu-id="974b5-105">Access Application Data?</span></span>

<span data-ttu-id="974b5-p102">InfoPath 托管代码对象模型所提供的对象和集合可以用来访问有关 InfoPath 应用程序的信息，其中包括有关表单的基础 XML 文档以及表单定义 (.xsf) 文件的信息。这些数据通过 InfoPath 对象模型分层结构的顶级对象（该对象通过使用 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类来实例化）来访问。</span><span class="sxs-lookup"><span data-stu-id="974b5-p102">The InfoPath managed code object model provides objects and collections that can be used to gain access to information about the InfoPath application, including information related to a form's underlying XML document and the form definition (.xsf) file. This data is accessed through the top-level object in the InfoPath object model hierarchy, which is instantiated by using the [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) class.</span></span> 
  
<span data-ttu-id="974b5-108">在使用 Visual Studio 2008 创建的 InfoPath 托管代码表单模板项目中，您可以使用 **this** (C#) 或 **Me** (Visual Basic) 关键字来访问表示当前 InfoPath 应用程序的 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类的实例，然后可使用该应用程序来访问 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="974b5-108">In an InfoPath managed code form template project created using Visual Studio 2012, you can use the **this** (C#) or **Me** (Visual Basic) keyword to access an instance of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) class that represents the current InfoPath application, which can then be used to access the properties and methods of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) class.</span></span> 
  
## <a name="example"></a><span data-ttu-id="974b5-109">示例</span><span class="sxs-lookup"><span data-stu-id="974b5-109">Example</span></span>

### <a name="displaying-the-application-name-version-and-language-id"></a><span data-ttu-id="974b5-110">显示应用程序名称、版本和语言 ID</span><span class="sxs-lookup"><span data-stu-id="974b5-110">Displaying the Application Name, Version, and Language ID</span></span>

<span data-ttu-id="974b5-p103">在以下示例中，[Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Name.aspx) 类的 [Name](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Version.aspx) 和 [Version](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 属性用于返回 InfoPath 运行实例的名称和版本号。然后， [LanguageSettings](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.LanguageSettings.aspx) 属性可用于返回 **LanguageSettings** 对象，该对象进而又可以返回 InfoPath 用户界面当前所用语言的 LCID（一个四位数字）。最后，所有这些信息都显示在一个消息框中。</span><span class="sxs-lookup"><span data-stu-id="974b5-p103">In the following example, the [Name](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Name.aspx) and [Version](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Version.aspx) properties of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) class are used to return the name and version number of the running instance of InfoPath. The [LanguageSettings](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.LanguageSettings.aspx) property is then used to return a **LanguageSettings** object, which in turn is used to return the LCID (a four-digit number) for the language that is currently being used for the InfoPath user interface language. Finally, all of this information is displayed in a message box.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="974b5-114">要使 **LanguageSettings** 属性正常工作，必须在 Visual Studio 2012 中的“添加引用”**** 对话框的 COM **** 选项卡中建立对 Microsoft Office 14.0 对象库的引用。</span><span class="sxs-lookup"><span data-stu-id="974b5-114">For the **LanguageSettings** property to work, you must establish a reference to the Microsoft Office 14.0 Object Library from the **COM** tab of the **Add Reference** dialog box in vsta14. This will establish a reference to the Microsoft.Office.Core namespace, which contains the LanguageSettings class. Additionally, the form must be running as Full Trust.</span></span> <span data-ttu-id="974b5-115">这样会建立对 **Microsoft.Office.Core** 命名空间的引用，其中包含 **LanguageSettings** 类。</span><span class="sxs-lookup"><span data-stu-id="974b5-115">This will establish a reference to the **Microsoft.Office.Core** namespace, which contains the **LanguageSettings** class.</span></span> <span data-ttu-id="974b5-116">此外，还必须将此表单作为完全信任的表单运行。</span><span class="sxs-lookup"><span data-stu-id="974b5-116">Additionally, the form must be running as Full Trust.</span></span> 
  
<span data-ttu-id="974b5-117">此示例要求在表单代码模块的声明部分中使用 **Microsoft.Office.Core** 命名空间的 **using** 或 **Imports** 指令。</span><span class="sxs-lookup"><span data-stu-id="974b5-117">This example requires a **using** or **Imports** directive for the **Microsoft.Office.Core** namespace in the declarations section of the form code module.</span></span> 
  
```cs
string appName = this.Application.Name;
string appVersion = this.Application.Version;
LanguageSettings langSettings = 
   (LanguageSettings)this.Application.LanguageSettings;
int langID = 
   langSettings.get_LanguageID(MsoAppLanaguageID.msoLanguageIDUI);
MessageBox.Show(
   "Name: " + appName + System.Environment.NewLine +
   "Version: " + appVersion + System.Environment.NewLine +
   "Language ID: " + langID);
```

```vb
Dim appName As String appName = Me.Application.Name
Dim appVersion As String = Me.Application.Version
Dim langSettings As LanguageSettings = _
   DirectCast(Me.Application.LanguageSettings, LanguageSettings)
Dim langID As Integer = _
   langSettings.LanguageID(MsoAppLanaguageID.msoLanguageIDUI)
MessageBox.Show( _
   "Name: " + appName + System.Environment.NewLine + _
   "Version: " + appVersion + System.Environment.NewLine + _
   "Language ID: " + langID)
```


