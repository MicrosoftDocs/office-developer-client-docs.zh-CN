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
# <a name="use-microsoftofficeinteropinfopathsemitrust-members-not-compatible-with-infopath"></a><span data-ttu-id="07990-104">使用 Microsoft。Office.Interop.InfoPath.SemiTrust 成员与 InfoPath 不兼容</span><span class="sxs-lookup"><span data-stu-id="07990-104">Use Microsoft.Office.Interop.InfoPath.SemiTrust members not compatible with InfoPath</span></span>

<span data-ttu-id="07990-105">将代码添加到使用 Microsoft Office InfoPath 2003 Toolkit 创建的 表单模板 或创建与 InfoPath 2003 兼容对象模型 (（如使用[InfoPath 2003](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)对象模型创建表单模板) 中所述）的新 表单模板 时， 默认情况下，Microsoft InfoPath 将使用[Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx)命名空间提供的一部分对象和成员，这些对象和成员与 InfoPath 2003 使用的命名空间相同。</span><span class="sxs-lookup"><span data-stu-id="07990-105">When you add code to a form template that was created with the Microsoft Office InfoPath 2003 Toolkit or create a new form template that works with the InfoPath 2003-compatible object model (as described in [Create a Form Template Using the InfoPath 2003 Object Model](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)), by default, Microsoft InfoPath will use a subset of the objects and members provided by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace that are identical to those used by InfoPath 2003.</span></span> <span data-ttu-id="07990-106">这是为了实现与 InfoPath 2003 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="07990-106">This is done to provide compatibility with InfoPath 2003.</span></span> <span data-ttu-id="07990-107">但是[，Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx)命名空间提供的对象模型包括其他对象和成员，这些对象和成员提供已添加到 Office InfoPath 2007 和 InfoPath 的新功能。</span><span class="sxs-lookup"><span data-stu-id="07990-107">However, the object model provided by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace includes additional objects and members that provide new functionality that was added to Office InfoPath 2007 and InfoPath.</span></span> 
  
<span data-ttu-id="07990-108">例如 [，PermissionObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.PermissionObject.aspx) 和 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.aspx) 接口提供在 InfoPath 2003 中不可用的新信息权限管理功能。</span><span class="sxs-lookup"><span data-stu-id="07990-108">For example, the [PermissionObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.PermissionObject.aspx) and [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.aspx) interfaces provide new information rights management functionality that is not available in InfoPath 2003.</span></span> <span data-ttu-id="07990-109">默认情况下，在您打开或创建使用 InfoPath 2003 兼容对象模型的托管代码表单模板时，该新功能以及添加到 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间的其他新对象将不可用。</span><span class="sxs-lookup"><span data-stu-id="07990-109">This, and other new objects added to the Microsoft.Office.Interop.InfoPath.SemiTrust namespace are not available by default when you open or create managed code form template with InfoPath 2003-compatible object model.</span></span> 
  
<span data-ttu-id="07990-110">同样，虽然[_XDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.aspx)接口提供的功能与 InfoPath 2003 相同;_XDocument3 [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.aspx)接口已经过版本控制，以包括 Office InfoPath 2007 中添加的其他属性和方法，并且[对 _XDocument4](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument4.aspx)进行了版本控制，以包括 InfoPath 中添加的其他属性和方法。</span><span class="sxs-lookup"><span data-stu-id="07990-110">Similarly, while the [_XDocument2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.aspx) interface provides the same functionality as InfoPath 2003; the [_XDocument3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.aspx) interface has been versioned to include additional properties and methods that were added in Office InfoPath 2007, and the [_XDocument4](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument4.aspx) has been versioned to include additional properties and methods that were added in InfoPath.</span></span> 
  
<span data-ttu-id="07990-111">如果要在使用 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的对象模型创建的 表单模板 项目中使用在 Office InfoPath 2007 或 InfoPath 中添加的对象和成员，可以这样做，但使用这些成员的代码将不能与 InfoPath 2003 兼容。</span><span class="sxs-lookup"><span data-stu-id="07990-111">If you want to use objects and members that were added in Office InfoPath 2007 or InfoPath in a form template project created using the object model provided by the **Microsoft.Office.Interop.InfoPath.SemiTrust** namespace, you can do so, but code that uses these members will not be compatible with InfoPath 2003.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="07990-112">部署到 Microsoft SharePoint Server 2010 Microsoft SharePoint Server 2010 with InfoPath Forms Services 的启用浏览器功能的表单模板不支持具有使用 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的对象模型创建的业务逻辑的所有表单模板（无论它们是否使用与 InfoPath 兼容的对象和成员）。</span><span class="sxs-lookup"><span data-stu-id="07990-112">All form templates with business logic created using the object model provided by the **Microsoft.Office.Interop.InfoPath.SemiTrust** namespace, whether they use objects and members compatible with InfoPath or not, are not supported for browser-enabled form templates deployed to Microsoft SharePoint Server 2010 with InfoPath Forms Services.</span></span> <span data-ttu-id="07990-113">启用浏览器功能的表单模板的业务逻辑必须使用 Microsoft.Office 提供的新 InfoPath[托管代码对象模型。InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx)命名空间。</span><span class="sxs-lookup"><span data-stu-id="07990-113">Business logic for browser-enabled form templates must use the new InfoPath managed code object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace.</span></span> 
  
## <a name="example"></a><span data-ttu-id="07990-114">示例</span><span class="sxs-lookup"><span data-stu-id="07990-114">Example</span></span>

### <a name="creating-an-xdocument-or-application-object-variable-to-access-new-object-model-members"></a><span data-ttu-id="07990-115">创建 XDocument 或 Application 对象变量以访问新对象模型成员</span><span class="sxs-lookup"><span data-stu-id="07990-115">Creating an XDocument or Application Object Variable to Access New Object Model Members</span></span>

<span data-ttu-id="07990-116">要访问 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间中可用的新对象和成员，您必须声明对象变量并将其强制转换为实现这些成员的接口的正确版本。</span><span class="sxs-lookup"><span data-stu-id="07990-116">To access the new objects and members that are available in the **Microsoft.Office.Interop.InfoPath.SemiTrust** namespace, you must declare and cast object variables to the correct version of the interface that implements these members.</span></span> <span data-ttu-id="07990-117">默认情况下，和 `thisXDocument` `thisApplication` 变量访问与 InfoPath  2003 兼容的相应 _XDocument2 和[_Application2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.aspx)版本。</span><span class="sxs-lookup"><span data-stu-id="07990-117">By default, the  `thisXDocument` and  `thisApplication` variables access the InfoPath 2003-compatible versions of the corresponding **_XDocument2** and [_Application2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.aspx) interfaces.</span></span> <span data-ttu-id="07990-118">若要访问 **提供** 对新功能的访问的 [_XDocument3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application3.aspx)和 _Application3 接口，必须声明 **_XDocument3** 或 **_Application3** 类型的对象变量，然后将 或 变量返回的对象强制转换到相同的类型，如以下示例所示。 `thisXDocument` `thisApplication`</span><span class="sxs-lookup"><span data-stu-id="07990-118">To access the **_XDocument3** and [_Application3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application3.aspx) interfaces that provide access to new functionality, you must declare an object variable of the **_XDocument3** or **_Application3** type, and then cast the object returned by the  `thisXDocument` or  `thisApplication` variable to the same type as shown in the following examples.</span></span> 
  
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

### <a name="accessing-a-new-object-from-the-xdocument-or-application-object-variable-using-an-accessor-property"></a><span data-ttu-id="07990-119">使用访问器属性从 XDocument 或 Application 对象变量访问新对象</span><span class="sxs-lookup"><span data-stu-id="07990-119">Accessing a New Object From The XDocument or Application Object Variable Using an Accessor Property</span></span>

<span data-ttu-id="07990-120">创建更高版本 _ **XDocument3** 或 **_Application3** 类型的变量后，可以使用它访问提供新 InfoPath 功能的对象或成员。</span><span class="sxs-lookup"><span data-stu-id="07990-120">After you have created a variable of the later version _ **XDocument3** or **_Application3** type, you can use it to access an object or member that provides new InfoPath functionality.</span></span> 
  
<span data-ttu-id="07990-121">以下示例演示如何使用类型为 _ **XDocument3** 的对象变量和 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.Permission.aspx) 访问器属性来访问新的 **Permission** 接口及其 [Enabled](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.Enabled.aspx) 属性，以确定是否对表单启用了权限设置。</span><span class="sxs-lookup"><span data-stu-id="07990-121">The following example shows how to use an object variable of type _ **XDocument3** with the [Permission](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.Permission.aspx) accessor property to access the new **Permission** interface and its [Enabled](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Permission.Enabled.aspx) property to determine if permission settings are enabled for the form.</span></span> 
  
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

### <a name="accessing-a-versioned-object-and-casting-to-the-versioned-type"></a><span data-ttu-id="07990-122">访问新版本的对象并强制转换为新版本的类型</span><span class="sxs-lookup"><span data-stu-id="07990-122">Accessing a Versioned Object and Casting to the Versioned Type</span></span>

<span data-ttu-id="07990-123">如果 InfoPath 2003 对象模型中的现有对象添加了新的属性或方法，则实现这些新成员的对象将具有新版本的名称。</span><span class="sxs-lookup"><span data-stu-id="07990-123">If an object that existed in the InfoPath 2003 object model has new properties or methods added to it, the object that implements those new members will have a name that is versioned.</span></span>
  
<span data-ttu-id="07990-124">例如 [，ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.aspx) 对象不提供对仅在使用版本控制 [ViewInfo2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.aspx) 对象时可用的两个新属性的访问权限 [：Caption](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.Caption.aspx) 和 [HideName](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.HideName.aspx) 属性。</span><span class="sxs-lookup"><span data-stu-id="07990-124">For example, the [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.aspx) object does not provide access to two new properties that are only available when using the versioned [ViewInfo2](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.aspx) object: the [Caption](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.Caption.aspx) and [HideName](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo2.HideName.aspx) properties.</span></span> 
  
<span data-ttu-id="07990-125">若要访问这些属性，必须声明一个类型为 **ViewInfo2** 的对象变量，将 _ **XDocument3** 对象变量的 [ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.ViewInfos.aspx)属性返回的对象强制转换到 **ViewInfo2** 类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="07990-125">To access these properties, you must declare an object variable of type **ViewInfo2** and cast the object returned by the [ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument3.ViewInfos.aspx) property of the _ **XDocument3** object variable to the **ViewInfo2** type as shown in the following example.</span></span> 
  
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


