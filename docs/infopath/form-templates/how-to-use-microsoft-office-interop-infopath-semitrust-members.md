---
title: 使用 Microsoft。Office.Interop.InfoPath.SemiTrust 成员与 InfoPath 不兼容
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates， using infopath 2007 features
localization_priority: Normal
ms.assetid: d082f3a3-387a-4db1-bbad-495c326b8ee3
description: Microsoft 提供的对象模型。Office.Interop.InfoPath.SemiTrust 命名空间包括提供已添加到 InfoPath 2007 和 InfoPath Office新功能的对象和成员。
ms.openlocfilehash: 45f7607aec8ccfd653780a550df0823730835a86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415339"
---
# <a name="use-microsoftofficeinteropinfopathsemitrust-members-not-compatible-with-infopath"></a>使用 Microsoft。Office.Interop.InfoPath.SemiTrust 成员与 InfoPath 不兼容

将代码添加到使用 Microsoft Office InfoPath 2003 Toolkit 创建的 表单模板 或创建与 InfoPath 2003 兼容对象模型 (（如使用[InfoPath 2003](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)对象模型创建表单模板) 中所述）的新 表单模板 时， 默认情况下，Microsoft InfoPath 将使用[Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx)命名空间提供的一部分对象和成员，这些对象和成员与 InfoPath 2003 使用的命名空间相同。 这是为了实现与 InfoPath 2003 的兼容性。 但是[，Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx)命名空间提供的对象模型包括其他对象和成员，这些对象和成员提供已添加到 Office InfoPath 2007 和 InfoPath 的新功能。 
  
例如 [，PermissionObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.PermissionObject.aspx) 和 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.aspx) 接口提供在 InfoPath 2003 中不可用的新信息权限管理功能。 默认情况下，在您打开或创建使用 InfoPath 2003 兼容对象模型的托管代码表单模板时，该新功能以及添加到 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间的其他新对象将不可用。 
  
同样，虽然[_XDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.aspx)接口提供的功能与 InfoPath 2003 相同;_XDocument3 [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.aspx)接口已经过版本控制，以包括 Office InfoPath 2007 中添加的其他属性和方法，并且[对 _XDocument4](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument4.aspx)进行了版本控制，以包括 InfoPath 中添加的其他属性和方法。 
  
如果要在使用 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的对象模型创建的 表单模板 项目中使用在 Office InfoPath 2007 或 InfoPath 中添加的对象和成员，可以这样做，但使用这些成员的代码将不能与 InfoPath 2003 兼容。 
  
> [!NOTE]
> 部署到 Microsoft SharePoint Server 2010 Microsoft SharePoint Server 2010 with InfoPath Forms Services 的启用浏览器功能的表单模板不支持具有使用 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的对象模型创建的业务逻辑的所有表单模板（无论它们是否使用与 InfoPath 兼容的对象和成员）。 启用浏览器功能的表单模板的业务逻辑必须使用 Microsoft.Office 提供的新 InfoPath[托管代码对象模型。InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx)命名空间。 
  
## <a name="example"></a>示例

### <a name="creating-an-xdocument-or-application-object-variable-to-access-new-object-model-members"></a>创建 XDocument 或 Application 对象变量以访问新对象模型成员

要访问 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间中可用的新对象和成员，您必须声明对象变量并将其强制转换为实现这些成员的接口的正确版本。 默认情况下，和 `thisXDocument` `thisApplication` 变量访问与 InfoPath  2003 兼容的相应 _XDocument2 和[_Application2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.aspx)版本。 若要访问 **提供** 对新功能的访问的 [_XDocument3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application3.aspx)和 _Application3 接口，必须声明 **_XDocument3** 或 **_Application3** 类型的对象变量，然后将 或 变量返回的对象强制转换到相同的类型，如以下示例所示。 `thisXDocument` `thisApplication` 
  
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

创建更高版本 _ **XDocument3** 或 **_Application3** 类型的变量后，可以使用它访问提供新 InfoPath 功能的对象或成员。 
  
以下示例演示如何使用类型为 _ **XDocument3** 的对象变量和 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.Permission.aspx) 访问器属性来访问新的 **Permission** 接口及其 [Enabled](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.Enabled.aspx) 属性，以确定是否对表单启用了权限设置。 
  
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
  
例如 [，ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.aspx) 对象不提供对仅在使用版本控制 [ViewInfo2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.aspx) 对象时可用的两个新属性的访问权限 [：Caption](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.Caption.aspx) 和 [HideName](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.HideName.aspx) 属性。 
  
若要访问这些属性，必须声明一个类型为 **ViewInfo2** 的对象变量，将 _ **XDocument3** 对象变量的 [ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.ViewInfos.aspx)属性返回的对象强制转换到 **ViewInfo2** 类型，如以下示例所示。 
  
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


