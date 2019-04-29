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
ms.openlocfilehash: 8da72313807584ee599d65701d009786dd631979
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417229"
---
# <a name="access-application-data"></a>访问应用程序数据

InfoPath 托管代码对象模型所提供的对象和集合可以用来访问有关 InfoPath 应用程序的信息，其中包括有关表单的基础 XML 文档以及表单定义 (.xsf) 文件的信息。这些数据通过 InfoPath 对象模型分层结构的顶级对象（该对象通过使用 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类来实例化）来访问。 
  
在使用 Visual Studio 2008 创建的 InfoPath 托管代码表单模板项目中，您可以使用 **this** (C#) 或 **Me** (Visual Basic) 关键字来访问表示当前 InfoPath 应用程序的 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类的实例，然后可使用该应用程序来访问 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类的属性和方法。 
  
## <a name="example"></a>示例

### <a name="displaying-the-application-name-version-and-language-id"></a>显示应用程序名称、版本和语言 ID

在以下示例中，[Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Name.aspx) 类的 [Name](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Version.aspx) 和 [Version](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 属性用于返回 InfoPath 运行实例的名称和版本号。然后， [LanguageSettings](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.LanguageSettings.aspx) 属性可用于返回 **LanguageSettings** 对象，该对象进而又可以返回 InfoPath 用户界面当前所用语言的 LCID（一个四位数字）。最后，所有这些信息都显示在一个消息框中。 
  
> [!IMPORTANT]
> For the **LanguageSettings** property to work, you must establish a reference to the Microsoft Office 14.0 Object Library from the **COM** tab of the **Add Reference** dialog box in Visual Studio 2012. This will establish a reference to the **Microsoft.Office.Core** namespace, which contains the **LanguageSettings** class. Additionally, the form must be running as Full Trust. 
  
此示例要求在表单代码模块的声明部分中使用 **Microsoft.Office.Core** 命名空间的 **using** 或 **Imports** 指令。 
  
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


