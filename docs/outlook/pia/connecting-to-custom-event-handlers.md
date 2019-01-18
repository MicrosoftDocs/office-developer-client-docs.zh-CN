---
title: 连接到自定义事件处理程序
TOCTitle: Connecting to custom event handlers
ms:assetid: 6e894c16-0fe9-4b86-b798-547b86f44cd8
ms:mtpsurl: https://msdn.microsoft.com/library/Bb610520(v=office.15)
ms:contentKeyID: 55119783
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 58722b8b140f89f0fe29a3e52db578a423a0160a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711796"
---
# <a name="connecting-to-custom-event-handlers"></a>连接到自定义事件处理程序

Outlook 通过引发事件来通知加载项有情况发生，如收件箱收到新邮件等。加载项可指示 Outlook 在出现特定事件后，应执行相应的操作。这种通知和回调机制受 .NET Framework 委派支持。Outlook 主互操作程序集 (PIA) 定义您可以将回调方法与其连接以处理相应事件的委派。此主题描述这一定义回调方法并将其作为事件处理程序连接到 Outlook 对象的过程。

## <a name="creating-a-callback-method"></a>创建回调方法

实现回调方法可处理发生的特定事件，该方法由通知源执行。在 Outlook 中，加载项可以实现回调方法，以响应 Outlook 引发的特定事件。该回调方法必须匹配相应事件的委派签名。例如，若要为 [ItemSend](https://msdn.microsoft.com/library/bb647198\(v=office.15\)) 事件实现事件处理程序，必须声明与相应委派的签名匹配的回调方法：

```csharp
public delegate void ApplicationEvents_11_ItemSendEventHandler(object Item, ref bool Cancel)
```


```vb
Public Delegate Sub ApplicationEvents_11_ItemSendEventHandler(_
    ByVal Item As Object, ByRef Cancel As Boolean)
```

定义回调方法时，忽略 **Delegate** 关键字（否则可能会定义其他委托）。示例回调方法 **MyItemSendEventHandler** 如下所示：

```csharp
public void MyItemSendEventHandler(object Item, ref bool Cancel)
```


```vb
Public Sub MyItemSendEventHandler (_
    ByVal Item As Object, ByRef Cancel As Boolean)
…
End Sub
```

## <a name="connecting-a-callback-method"></a>连接回调方法

为事件实现某回调方法后，可以将其连接到 Outlook 对象，以便 Outlook 知道将此方法作为该事件的事件处理程序进行调用。请注意，一个事件可以由多个事件处理程序进行处理，并且需要进行委派，以便将事件处理进程分配给事件处理程序。

接下来是最后一个示例，此示例为 **Application** 对象的 **ItemSend** 事件指定事件处理程序，以在 C\# 中将 **MyItemSendEventHandler** 连接到 **Application** 对象，创建委托对象实例，将 **MyItemSendEventHandler** 传递给委托对象的构造函数，再使用 += 运算符将此委托对象添加到 **ItemSend** 事件中：

```csharp
app.ItemSend += new ApplicationEvents_11_ItemSendEventHandler(MyItemSendEventHandler)
```

在 Visual Basic 中，使用 **AddHandler** 语句关联 **ItemSend** 事件与 **MyItemSendEventHandler** 事件处理程序：

```vb
AddHandler app.ItemSend, AddressOf MyItemSendEventHandler
```

## <a name="see-also"></a>另请参阅

- [Outlook PIA 中的事件](events-in-the-outlook-pia.md)
- [Outlook PIA 中的对象](objects-in-the-outlook-pia.md)

