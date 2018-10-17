---
title: 在需要依赖 Outlook 的多个版本时使用晚期绑定
TOCTitle: Using late binding if depending on multiple versions of Outlook
ms:assetid: 4e5412a0-d0f8-4819-ba0f-f36ba885f8f6
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb610234(v=office.15)
ms:contentKeyID: 55119791
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 866faab04e8fcac1d91b233f801f05c023ac2164
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407070"
---
# <a name="using-late-binding-if-depending-on-multiple-versions-of-outlook"></a><span data-ttu-id="054c7-102">在需要依赖 Outlook 的多个版本时使用晚期绑定</span><span class="sxs-lookup"><span data-stu-id="054c7-102">Using Late Binding If Depending on Multiple Versions of Outlook</span></span>

<span data-ttu-id="054c7-103">使用 Outlook 主互操作程序集 (PIA) 的托管 Outlook 加载项是使用 PIA 提供的类型信息进行编译。</span><span class="sxs-lookup"><span data-stu-id="054c7-103">Managed Outlook add-ins that use the Outlook Primary Interop Assembly (PIA) are compiled with type information that the PIA provides.</span></span> <span data-ttu-id="054c7-104">借助这种提前将类型信息绑定到方法和属性的**早期绑定**，编译者可以执行类型和语法检查，从而确保能够将正确数量和类型的参数传递给方法或属性，并让返回的值为所需类型。</span><span class="sxs-lookup"><span data-stu-id="054c7-104">This early binding of type information for methods and properties allows the compiler to perform type and syntax checks to ensure that the correct number and type of parameters are passed to the method or property, and that the returned value is of the expected type.</span></span> 

<span data-ttu-id="054c7-105">但是，早期绑定也有不利之处，即如果加载项所调用的方法或属性在早期版本中具有不同的声明，则会出现版本不兼容问题。</span><span class="sxs-lookup"><span data-stu-id="054c7-105">However, early binding has the disadvantage of introducing version incompatibility if a method or property that the add-in calls has a different declaration in an earlier version.</span></span> <span data-ttu-id="054c7-106">例如，增加新方法和属性或修改某个对象的现有成员会改变该对象的二进制布局，进而导致使用较新类型信息自动化 Outlook 早期版本的托管加载项出现问题。</span><span class="sxs-lookup"><span data-stu-id="054c7-106">For example, adding new methods and properties or modifying existing members of an object can alter the binary layout of the object and cause problems with a managed add-in that uses the more recent type information to automate an earlier version of Outlook.</span></span> 

<span data-ttu-id="054c7-107">在这种情况下，**后期绑定**一直等到运行时，才将属性和方法调用绑定到自己的对象。</span><span class="sxs-lookup"><span data-stu-id="054c7-107">In such cases, late binding waits until run time to bind property and method calls to their objects.</span></span> <span data-ttu-id="054c7-108">后期绑定有助于避免因不同 Outlook 版本中不同的类型所造成的混乱，尤其在编写依赖多个 Outlook 版本的加载项时非常有用。</span><span class="sxs-lookup"><span data-stu-id="054c7-108">Late binding can help avoid complications from types that are different in different versions of Outlook, and is especially useful when writing add-ins that depend on multiple versions of Outlook.</span></span>

<span data-ttu-id="054c7-109">后期绑定涉及到调用由 Outlook 实现的 [IDispatch](https://docs.microsoft.com/windows/desktop/api/oaidl/nn-oaidl-idispatch) 接口的加载项。</span><span class="sxs-lookup"><span data-stu-id="054c7-109">Late binding involves an add-in calling the [IDispatch](https://docs.microsoft.com/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface implemented by Outlook.</span></span> <span data-ttu-id="054c7-110">若要在 Visual C\# 中使用后期绑定，请使用 [System.Type.InvokeMember](https://docs.microsoft.com/dotnet/api/system.type.invokemember?view=netframework-4.7.2) 方法。</span><span class="sxs-lookup"><span data-stu-id="054c7-110">To use late binding in Visual C\#, use the [System.Type.InvokeMember](https://docs.microsoft.com/dotnet/api/system.type.invokemember?view=netframework-4.7.2) method.</span></span> <span data-ttu-id="054c7-111">此方法调用 [IDispatch::GetIDsOfNames](https://docs.microsoft.com/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) 和 [IDispatch::Invoke](https://docs.microsoft.com/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)，以绑定到 Outlook 的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="054c7-111">This method calls [IDispatch::GetIDsOfNames](https://docs.microsoft.com/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) and [IDispatch::Invoke](https://docs.microsoft.com/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) to bind to Outlook’s methods and properties.</span></span> <span data-ttu-id="054c7-112">使用 IDispatch::GetIDsOfNames 方法，Visual C\# 可以询问对象支持哪些方法和属性。然后，使用 IDispatch::Invoke 方法，Visual C\# 可以调用这些方法和属性。</span><span class="sxs-lookup"><span data-stu-id="054c7-112">The IDispatch::GetIDsOfNames method allows Visual C\# to interrogate an object about what methods and properties it supports and the IDispatch::Invoke method then allows Visual C\# to call those methods and properties.</span></span> 

<!-- PAGES 404 
For more information about using late binding in C\#, see [KB 302902: Binding for Office Automation Servers with Visual C\# .NET](https://go.microsoft.com/fwlink/?linkid=88971). For more information about using late binding in Visual Basic, see [KB 304661: How to Use Visual Basic .NET for Binding for Office Automation Servers](https://go.microsoft.com/fwlink/?linkid=88972).

Note that late binding requires obtaining a DispID for every method or property, so late binding generally does not perform as well as early binding. For more information about how early binding compares with late binding, see [KB 245115: Using Early Binding and Late Binding in Automation](https://go.microsoft.com/fwlink/?linkid=88973). -->

## <a name="see-also"></a><span data-ttu-id="054c7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="054c7-113">See also</span></span>

- [<span data-ttu-id="054c7-114">COM 和 .NET 之间的互操作性简介</span><span class="sxs-lookup"><span data-stu-id="054c7-114">Introduction to Interoperability Between COM and .NET</span></span>](introduction-to-interoperability-between-com-and-net.md)

