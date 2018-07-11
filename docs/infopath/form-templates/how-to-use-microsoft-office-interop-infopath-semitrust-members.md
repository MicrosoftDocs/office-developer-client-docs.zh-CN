---
title: 使用与 InfoPath 不兼容的 Microsoft.Office.Interop.InfoPath.SemiTrust 成员
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, using infopath 2007 features
localization_priority: Normal
ms.assetid: d082f3a3-387a-4db1-bbad-495c326b8ee3
description: 由 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间提供的对象模型包括对象提供已添加到 Office InfoPath 2007 和 InfoPath 的新功能的成员。
ms.openlocfilehash: 3d0e9b450dab6a821af1f698d9859b21e85abf81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773992"
---
# <a name="use-microsoftofficeinteropinfopathsemitrust-members-not-compatible-with-infopath"></a>使用与 InfoPath 不兼容的 Microsoft.Office.Interop.InfoPath.SemiTrust 成员

当您将代码添加到使用 Microsoft Office InfoPath 2003 Toolkit 已创建的表单模板，或创建使用 InfoPath 2003 兼容对象模型 （中所述[创建表单模板使用 InfoPath 2003 对象的新表单模板建模](how-to-create-a-form-template-using-the-infopath-2003-object-model.md))、 默认情况下，Microsoft InfoPath 将使用对象的一个子集和[Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx)命名空间，与使用 InfoPath 2003 提供的成员。 这是为了实现与 InfoPath 2003 的兼容性。 但是， [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的对象模型包含附加的对象和成员，它们可提供已添加到 Office InfoPath 2007 和 InfoPath 中的新功能。 
  
例如，[PermissionObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.PermissionObject.aspx) 和 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.aspx) 接口提供 InfoPath 2003 中不具备的新的信息权限管理功能。默认情况下，在您打开或创建使用 InfoPath 2003 兼容对象模型的托管代码表单模板时，该新功能以及添加到 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间的其他新对象将不可用。 
  
同样，虽然 [_XDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.aspx) 接口提供与 InfoPath 2003 相同的功能，但 [_XDocument3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.aspx) 接口的版本已经过管理，现在包含添加到 Office InfoPath 2007 中的附加属性和方法， [_XDocument4](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument4.aspx) 也已经过版本管理，现在包含添加到 InfoPath 中的附加属性和方法。 
  
对于使用由 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的对象模型创建的表单模板项目，如果您想在其中使用已添加到 Office InfoPath 2007 或 InfoPath 中的对象和成员，可尽管使用，但使用这些成员的代码将与 InfoPath 2003 不兼容。 
  
> [!NOTE]
> [!注释] 对于所有表单模板，只要它们包含使用 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的对象模型创建的业务逻辑，那么无论它们是否使用与 InfoPath 兼容的对象和成员，都不会受部署到 Microsoft SharePoint Server 2010（带有 InfoPath Forms Services）的启用浏览器功能的表单模板支持。启用浏览器功能的表单模板的业务逻辑必须使用 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的新的 InfoPath 托管代码对象模型。 
  
## <a name="example"></a>示例

### <a name="creating-an-xdocument-or-application-object-variable-to-access-new-object-model-members"></a>创建 XDocument 或 Application 对象变量以访问新对象模型成员

要访问 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间中可用的新对象和成员，您必须声明对象变量并将其强制转换为实现这些成员的接口的正确版本。默认情况下，  `thisXDocument` 和  `thisApplication` 变量访问相应 **_XDocument2** 和 [_Application2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.aspx) 接口的 InfoPath 2003 兼容版本。要访问提供对新功能的访问的 **_XDocument3** 和 [_Application3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application3.aspx) 接口，您必须声明一个 **_XDocument3** 或 **_Application3** 类型的对象变量，然后将  `thisXDocument` 或  `thisApplication` 变量返回的对象强制转换为该类型，如下面的示例所示。 
  
```cs
// Declare an object variable of type _XDocument3 and
// cast the object returned by the thisXDocument variable to
// the same type.
_XDocument3 thisXDocument3 = (_XDocument3)thisXDocument;
```

```vb
' Declare an object variable of type _XDocument3 and
' cast the object returned by the thisXDocument variable to
' the same type.
Dim thisXDocument3 As _XDocument3 = _
   DirectCast(thisXDocument, _XDocument3)
```

```cs
// Declare an object variable of type _Application3 and
// cast the object returned by the thisApplication variable to
// the same type.
_Application3 thisApplication3 = (_Application3)thisXDocument;
```

```vb
' Declare an object variable of type _Application3 and
' cast the object returned by the thisXApplication variable to
' the same type.
Dim thisDocument As _XDocument3 = _
   DirectCast(thisXDocument, _XDocument3)
```

### <a name="accessing-a-new-object-from-the-xdocument-or-application-object-variable-using-an-accessor-property"></a>使用访问器属性从 XDocument 或 Application 对象变量访问新对象

在创建更高版本的 **XDocument3** 或 **_Application3** 类型的变量后，可以使用该变量访问提供 InfoPath 新功能的对象或成员。 
  
以下示例显示如何使用 **XDocument3** 类型的对象变量及 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.Permission.aspx) 访问器属性来访问新的 **Permission** 接口及其 [Enabled](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.Enabled.aspx) 属性，以确定是否对表单启用了权限设置。 
  
```cs
// Declare an object variable of type _XDocument3 and
// cast the object returned by the thisXDocument variable to
// the same type.
_XDocument3 thisXDocument3 = (_XDocument3)thisXDocument;
// Use the object variable to access the later version object and
// property.
thisXDocument.UI.Alert(thisDocument3.Permission.Enabled.ToString());
```

```vb
' Declare an object variable of type _XDocument3 and
' cast the object returned by the thisXDocument variable to
' the same type.
Dim thisXDocument3 As _XDocument3 = _
   DirectCast(thisXDocument, _XDocument3)
' Use the object variable to access the later version object and
' property.
thisXDocument.UI.Alert(thisDocument3.Permission.Enabled.ToString())
```

### <a name="accessing-a-versioned-object-and-casting-to-the-versioned-type"></a>访问新版本的对象并强制转换为新版本的类型

如果 InfoPath 2003 对象模型中的现有对象添加了新的属性或方法，则实现这些新成员的对象将具有新版本的名称。
  
例如，[ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.aspx) 对象不提供对仅在使用新版本的 [ViewInfo2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.aspx) 对象时可用的两个新属性的访问： [Caption](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.Caption.aspx) 和 [HideName](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.HideName.aspx) 属性。 
  
要访问这些属性，您必须声明 **ViewInfo2** 类型的对象变量，并将由 [XDocument3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.ViewInfos.aspx) 对象变量的 **ViewInfos** 属性所返回的对象强制转换为 **ViewInfo2** 类型，如以下示例所示。 
  
```cs
// Declare an object variable of type _XDocument3 and
// cast the object returned by the thisXDocument variable to
// the same type.
_XDocument3 thisXDocument3 = (_XDocument3)thisXDocument;
// Declare an object variable of type ViewInfo2 and cast the object 
// returned by the ViewInfos property to that type.
ViewInfo2 thisView = (ViewInfo2)thisXDocument3.ViewInfos["View2"];
// Display the value of the new HideName property.
thisXDocument3.UI.Alert(thisView.HideName.ToString());
```

```vb
' Declare an object variable of type _XDocument3 and
' cast the object returned by the thisXDocument variable to
' the same type.
Dim thisXDocument3 As _XDocument3 = _
   DirectCast(thisXDocument, _XDocument3)
' Declare an object variable of type ViewInfo2 and cast the object 
' returned by the ViewInfos property to that type.
Dim thisView As ViewInfo2 = _
   DirectCast(thisXDocument3.ViewInfos("View2"), ViewInfo2)
' Display the value of the new HideName property.
thisXDocument3.UI.Alert(thisView.HideName.ToString())
```


