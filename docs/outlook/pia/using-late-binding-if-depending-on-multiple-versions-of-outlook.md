---
title: 在需要依赖 Outlook 的多个版本时使用晚期绑定
TOCTitle: Using late binding if depending on multiple versions of Outlook
ms:assetid: 4e5412a0-d0f8-4819-ba0f-f36ba885f8f6
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb610234(v=office.15)
ms:contentKeyID: 55119791
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e4cca4d426e5e7e9fd06fa3a0c3af1158b7e6c2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357468"
---
# <a name="using-late-binding-if-depending-on-multiple-versions-of-outlook"></a>在需要依赖 Outlook 的多个版本时使用晚期绑定

使用 Outlook 主互操作程序集 (PIA) 的托管 Outlook 加载项是使用 PIA 提供的类型信息进行编译。 借助这种提前将类型信息绑定到方法和属性的**早期绑定**，编译者可以执行类型和语法检查，从而确保能够将正确数量和类型的参数传递给方法或属性，并让返回的值为所需类型。 

但是，早期绑定也有不利之处，即如果加载项所调用的方法或属性在早期版本中具有不同的声明，则会出现版本不兼容问题。 例如，增加新方法和属性或修改某个对象的现有成员会改变该对象的二进制布局，进而导致使用较新类型信息自动化 Outlook 早期版本的托管加载项出现问题。 

在这种情况下，**后期绑定**一直等到运行时，才将属性和方法调用绑定到自己的对象。 后期绑定有助于避免因不同 Outlook 版本中不同的类型所造成的混乱，尤其在编写依赖多个 Outlook 版本的加载项时非常有用。

后期绑定涉及到调用由 Outlook 实现的 [IDispatch](https://docs.microsoft.com/windows/desktop/api/oaidl/nn-oaidl-idispatch) 接口的加载项。 若要在 Visual C\# 中使用后期绑定，请使用 [System.Type.InvokeMember](https://docs.microsoft.com/dotnet/api/system.type.invokemember?view=netframework-4.7.2) 方法。 此方法调用 [IDispatch::GetIDsOfNames](https://docs.microsoft.com/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) 和 [IDispatch::Invoke](https://docs.microsoft.com/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)，以绑定到 Outlook 的方法和属性。 使用 IDispatch::GetIDsOfNames 方法，Visual C\# 可以询问对象支持哪些方法和属性。然后，使用 IDispatch::Invoke 方法，Visual C\# 可以调用这些方法和属性。 

<!-- PAGES 404 
For more information about using late binding in C\#, see [KB 302902: Binding for Office Automation Servers with Visual C\# .NET](https://go.microsoft.com/fwlink/?linkid=88971). For more information about using late binding in Visual Basic, see [KB 304661: How to Use Visual Basic .NET for Binding for Office Automation Servers](https://go.microsoft.com/fwlink/?linkid=88972).

Note that late binding requires obtaining a DispID for every method or property, so late binding generally does not perform as well as early binding. For more information about how early binding compares with late binding, see [KB 245115: Using Early Binding and Late Binding in Automation](https://go.microsoft.com/fwlink/?linkid=88973). -->

## <a name="see-also"></a>另请参阅

- [COM 和 .NET 之间的互操作性简介](introduction-to-interoperability-between-com-and-net.md)

