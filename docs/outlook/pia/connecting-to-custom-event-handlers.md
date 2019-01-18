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
# <a name="connecting-to-custom-event-handlers"></a><span data-ttu-id="fdee3-102">连接到自定义事件处理程序</span><span class="sxs-lookup"><span data-stu-id="fdee3-102">Connecting to custom event handlers</span></span>

<span data-ttu-id="fdee3-p101">Outlook 通过引发事件来通知加载项有情况发生，如收件箱收到新邮件等。加载项可指示 Outlook 在出现特定事件后，应执行相应的操作。这种通知和回调机制受 .NET Framework 委派支持。Outlook 主互操作程序集 (PIA) 定义您可以将回调方法与其连接以处理相应事件的委派。此主题描述这一定义回调方法并将其作为事件处理程序连接到 Outlook 对象的过程。</span><span class="sxs-lookup"><span data-stu-id="fdee3-p101">Outlook raises events to notify add-ins about something happening, such as the Inbox receiving a new mail item. Add-ins can specify to Outlook that upon the occurrence of a specific event, certain actions should take place. This alert and callback mechanism is supported by delegates of the .NET Framework. The Outlook Primary Interop Assembly (PIA) defines delegates to which you can connect callback methods to handle corresponding events. This topic describes this process of defining a callback method and connecting it as an event handler to the Outlook object.</span></span>

## <a name="creating-a-callback-method"></a><span data-ttu-id="fdee3-108">创建回调方法</span><span class="sxs-lookup"><span data-stu-id="fdee3-108">Creating a Callback method</span></span>

<span data-ttu-id="fdee3-p102">实现回调方法可处理发生的特定事件，该方法由通知源执行。在 Outlook 中，加载项可以实现回调方法，以响应 Outlook 引发的特定事件。该回调方法必须匹配相应事件的委派签名。例如，若要为 [ItemSend](https://msdn.microsoft.com/library/bb647198\(v=office.15\)) 事件实现事件处理程序，必须声明与相应委派的签名匹配的回调方法：</span><span class="sxs-lookup"><span data-stu-id="fdee3-p102">A callback is a method that is implemented to handle the occurrence of a specific event and is executed by a notification source. In Outlook, add-ins can implement callback methods to respond to certain events raised by Outlook. This callback method must match the signature of the delegate of that event. For example, to implement an event handler for the [ItemSend](https://msdn.microsoft.com/library/bb647198\(v=office.15\)) event, you must declare the callback method that matches the signature of the corresponding delegate:</span></span>

```csharp
public delegate void ApplicationEvents_11_ItemSendEventHandler(object Item, ref bool Cancel)
```


```vb
Public Delegate Sub ApplicationEvents_11_ItemSendEventHandler(_
    ByVal Item As Object, ByRef Cancel As Boolean)
```

<span data-ttu-id="fdee3-p103">定义回调方法时，忽略 **Delegate** 关键字（否则可能会定义其他委托）。示例回调方法 **MyItemSendEventHandler** 如下所示：</span><span class="sxs-lookup"><span data-stu-id="fdee3-p103">When defining the callback method, ignore the **Delegate** keyword which otherwise would define another delegate. A sample callback method, **MyItemSendEventHandler**, is shown below:</span></span>

```csharp
public void MyItemSendEventHandler(object Item, ref bool Cancel)
```


```vb
Public Sub MyItemSendEventHandler (_
    ByVal Item As Object, ByRef Cancel As Boolean)
…
End Sub
```

## <a name="connecting-a-callback-method"></a><span data-ttu-id="fdee3-115">连接回调方法</span><span class="sxs-lookup"><span data-stu-id="fdee3-115">Connecting a Callback method</span></span>

<span data-ttu-id="fdee3-p104">为事件实现某回调方法后，可以将其连接到 Outlook 对象，以便 Outlook 知道将此方法作为该事件的事件处理程序进行调用。请注意，一个事件可以由多个事件处理程序进行处理，并且需要进行委派，以便将事件处理进程分配给事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fdee3-p104">After implementing a callback method for an event, you can connect it to the Outlook object so that Outlook knows to call the method as an event handler of that event. Note that an event can be handled by more than one event handler, and this is where delegates that assign event handling to event handlers come into play.</span></span>

<span data-ttu-id="fdee3-118">接下来是最后一个示例，此示例为 **Application** 对象的 **ItemSend** 事件指定事件处理程序，以在 C\# 中将 **MyItemSendEventHandler** 连接到 **Application** 对象，创建委托对象实例，将 **MyItemSendEventHandler** 传递给委托对象的构造函数，再使用 += 运算符将此委托对象添加到 **ItemSend** 事件中：</span><span class="sxs-lookup"><span data-stu-id="fdee3-118">Continuing with the last example of specifying a event handler for the **ItemSend** event of the **Application** object, to connect **MyItemSendEventHandler** to the **Application** object in C\#, create an instance of the delegate object, pass **MyItemSendEventHandler** to the constructor of the delegate object, and then add this delegate object to the **ItemSend** event using the += operator:</span></span>

```csharp
app.ItemSend += new ApplicationEvents_11_ItemSendEventHandler(MyItemSendEventHandler)
```

<span data-ttu-id="fdee3-119">在 Visual Basic 中，使用 **AddHandler** 语句关联 **ItemSend** 事件与 **MyItemSendEventHandler** 事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="fdee3-119">In Visual Basic, you use the **AddHandler** statement to associate the **ItemSend** event with the **MyItemSendEventHandler** event handler:</span></span>

```vb
AddHandler app.ItemSend, AddressOf MyItemSendEventHandler
```

## <a name="see-also"></a><span data-ttu-id="fdee3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdee3-120">See also</span></span>

- [<span data-ttu-id="fdee3-121">Outlook PIA 中的事件</span><span class="sxs-lookup"><span data-stu-id="fdee3-121">Events in the Outlook PIA</span></span>](events-in-the-outlook-pia.md)
- [<span data-ttu-id="fdee3-122">Outlook PIA 中的对象</span><span class="sxs-lookup"><span data-stu-id="fdee3-122">Objects in the Outlook PIA</span></span>](objects-in-the-outlook-pia.md)

