---
title: Outlook PIA 中的对象
TOCTitle: Objects in the Outlook PIA
ms:assetid: 1be732a6-d6da-4fa0-beaa-accf35db12d6
ms:mtpsurl: https://msdn.microsoft.com/library/Bb609459(v=office.15)
ms:contentKeyID: 55119778
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 434be5dc9193beaf9723530c6d963ed0a96d8884
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407028"
---
# <a name="objects-in-the-outlook-pia"></a>Outlook PIA 中的对象

在对象浏览器中浏览 Outlook 主互操作程序集 (PIA) 时，您可能会注意到许多接口和类的名称都引用了 Outlook 对象模型中的熟悉对象。 对象模型中的一些对象与 PIA 中的接口具有一对一的映射。 

例如， **AddressEntry** 映射到 PIA 中的 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 接口， **AddressList** 对象映射到 [AddressList](https://msdn.microsoft.com/library/bb623538\(v=office.15\)) 接口。 

但是，其他多数对象都在 PIA 中具有一对多的映射。 此一对多映射适用于在 Microsoft Office Outlook 2007 之前存在的一些对象以及自 Outlook 2007 以来添加的所有对象。 本主题列出了映射到 COM 对象的典型 .NET 接口、类和委托，还介绍了如何访问 Outlook PIA 中的对象。 它还介绍了 Outlook PIA 中的一些例外，即在基于 COM 的对象模型中对象遭隐藏或弃用的情况。

## <a name="helper-objects"></a>帮助程序对象

本节使用 **FormRegion** 对象作为示例演示了在 Outlook PIA 中用于对象的典型帮助程序类。在 Outlook 2007 中将 **FormRegion** 对象添加到对象模型中。与 PIA 中的 **FormRegion** 对象相关的是接口、类和委托，如图 1 所示。

**图 1：Outlook 对象模型和 Outlook PIA 中表示的 FormRegion 对象**

![Outlook 对象模型和 Outlook PIA 中表示的 FormRegion 对象](media/pia-outlook-object-model.gif)

您在访问 **FormRegion** 对象及其方法、属性和事件成员时最常用的一个接口是 [FormRegion](https://msdn.microsoft.com/library/bb652633\(v=office.15\)) 接口。 不过，不得将 **FormRegion** .NET 接口视为 **FormRegion** COM 对象的确切镜像；如果查看 Visual Studio 中的对象浏览器，便会发现 **FormRegion** 接口继承自另一接口，即 [\_FormRegion](https://msdn.microsoft.com/library/bb645761\(v=office.15\)) 接口。 实际上， **FormRegion** 接口只是基于 COM 类型库创建 Outlook PIA 所产生的少数几个接口和类中的一个。

为了创建 Outlook PIA，Outlook 将使用 .NET Framework 中的类型库导入程序 (TLBIMP) 将 COM 类型库中的类型定义转换为公共语言运行库程序集中的等效定义。在 COM 中， **FormRegion** 对象实际上是一个由以下两个接口组成的 coclass，这两个接口定义 **FormRegion** 对象实现的接口：

- 主接口 **\_FormRegion**

- 事件接口 [FormRegionEvents](https://msdn.microsoft.com/library/bb611940\(v=office.15\))

TLBIMP 直接从类型库中导入 **\_FormRegion** 和 **FormRegionEvents**。

除了导入主接口和事件接口外，TLBIMP 还会创建一个与 COM 对象同名的 .NET 接口，以及一个使用该对象的名称并在其后面追加"Class"的 .NET 类。对于 **FormRegion** 对象，TLBIMP 会创建以下内容：

- .NET 接口 **FormRegion**

- .NET 类 [FormRegionClass](https://msdn.microsoft.com/library/bb624204\(v=office.15\))

对于本主题所提及的 .NET 接口和 .NET 类，您应始终使用 TLBIMP 创建的 .NET 接口来访问对象。例如，为了在 VB 中访问 **FormRegion** 对象，需始终使用 **FormRegion** 接口，如以下代码示例所示：

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
Sub DemoFormRegion(ByVal Region As Outlook.FormRegion)
    Dim MyFormRegion As Outlook.FormRegion = Region
    ' Additional method code here
End Sub
```

<br/>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook; 
void DemoFormRegion(Outlook.FormRegion region) 
{
    Outlook.FormRegion myFormRegion = region; 
    // Additional method code here
}
```

若要了解 TLBIMP 分别导入和创建的主接口和 .NET 类的用途，请参阅 [Outlook PIA 中的方法和属性](methods-and-properties-in-the-outlook-pia.md)。 若要了解与事件相关的接口、委托和接收器帮助程序类的用途，请参阅 [Outlook PIA 中的事件](events-in-the-outlook-pia.md)。

## <a name="deprecated-objects"></a>弃用的对象

Outlook PIA 中公开了类型库中弃用的对象。 例如，**\_DDocSiteControl** 和 **\_DRecipientControl** 对象在类型库中被隐藏，但在 PIA 中却是公开的。

又例如，**MAPIFolder** 对象已遭弃用。 从 Outlook 2007 开始， **Folder** 对象替换了对象模型中的 **MAPIFolder** 对象。 现有解决方案应通过 **Folder** 替换对 **MAPIFolder** 的引用，Outlook 2007 和更高版本新增的所有解决方案都应只使用 **Folder** 对象。 对于非托管解决方案，Visual Basic 编辑器的对象浏览器不再列出 **MAPIFolder** 对象，甚至不列为隐藏对象。 

对于托管解决方案，即使 Outlook PIA 公开可用于访问 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象及其成员的 **Folder** 接口，Outlook PIA 也会将 [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) 公开为用于定义 **Folder** 对象成员的接口。

## <a name="see-also"></a>另请参阅

- [将 Outlook PIA 与对象模型相关联](relating-the-outlook-pia-with-the-object-model.md)


