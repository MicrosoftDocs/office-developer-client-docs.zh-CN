---
title: ADO for Windows Foundation Classes (ADO/WFC)
TOCTitle: ADO/WFC
ms:assetid: 73206be8-6515-79e4-e904-cc2d0d59411d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249468(v=office.15)
ms:contentKeyID: 48545628
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: da01d44e1e681a2de41741b11a9c412181c2fd9e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885078"
---
# <a name="adowfc"></a><span data-ttu-id="150c7-102">ADO/WFC</span><span class="sxs-lookup"><span data-stu-id="150c7-102">ADO/WFC</span></span>


<span data-ttu-id="150c7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="150c7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="150c7-p101">ADO for Windows Foundation Classes (ADO/WFC) 建立在 ADO 事件模型基础上，它可以提供经过简化的应用程序编程接口。通常，ADO/WFC 可以截获 ADO 事件，并将事件参数合并成单个事件类，然后调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="150c7-p101">ADO for Windows Foundation Classes (ADO/WFC) builds on the ADO event model and presents a simplified application programming interface. In general, ADO/WFC intercepts ADO events, consolidates the event parameters into a single event class, and then calls your event handler.</span></span>

<span data-ttu-id="150c7-106">**使用 ADO/WFC 的 ADO 事件的方法**</span><span class="sxs-lookup"><span data-stu-id="150c7-106">**To use ADO events in ADO/WFC**</span></span>

1.  <span data-ttu-id="150c7-p102">定义您自己的事件处理程序来处理事件。例如，如果想处理 **ConnectionEvent** 系列中的 **ConnectComplete** 事件，可以使用此代码：</span><span class="sxs-lookup"><span data-stu-id="150c7-p102">Define your own event handler to process an event. For example, if you wanted to process the **ConnectComplete** event in the **ConnectionEvent** family, you might use this code:</span></span>
    
    ```java 
     
    public void onConnectComplete(Object sender,ConnectionEvent e) 
    { 
        System.out.println("onConnectComplete:" + e); 
    } 
    ```

2.  <span data-ttu-id="150c7-p103">定义一个处理程序对象来代表事件处理程序。对于类型为 **ConnectionEvent** 的事件，处理程序对象的数据类型应当是 **ConnectEventHandler** ，而对于类型为 **RecordsetEvent** 的事件，其数据类型应当是 **RecordsetEventHandler** 。例如，对于 **ConnectComplete** 事件处理程序，代码应当类似如下：</span><span class="sxs-lookup"><span data-stu-id="150c7-p103">Define a handler object to represent your event handler. The handler object should be of data type **ConnectEventHandler** for an event of type **ConnectionEvent**, or data type **RecordsetEventHandler** for an event of type **RecordsetEvent**. For example, code the following for your **ConnectComplete** event handler:</span></span>
    
    ```java
        ConnectionEventHandler handler =  
                new ConnectionEventHandler(this, "onConnectComplete"); 
    ```

    <span data-ttu-id="150c7-p104">**ConnectionEventHandler** 构造函数的第一个参数是一个引用，它引用了第二个参数所命名的事件处理程序所属的类。 Microsoft Visual J++ 编译器还支持等价的语法：</span><span class="sxs-lookup"><span data-stu-id="150c7-p104">The first argument of the **ConnectionEventHandler** constructor is a reference to the class that contains the event handler named in the second argument. The Microsoft Visual J++ compiler also supports an equivalent syntax:</span></span>
    
    ```java 
     
        ConnectionEventHandler handler =  
            new ConnectionEventHandler(this, "onConnectComplete"); 
    ```
    
    ```java 
     
        ConnectionEventHandler handler =  
            new ConnectionEventHandler(this.onConnectComplete); 
    ```
    
    <span data-ttu-id="150c7-p105">**ConnectionEventHandler** 构造函数的第一个参数是一个引用，它引用了第二个参数所命名的事件处理程序所属的类。 Microsoft Visual J++ 编译器还支持等价的语法：</span><span class="sxs-lookup"><span data-stu-id="150c7-p105">The first argument of the **ConnectionEventHandler** constructor is a reference to the class that contains the event handler named in the second argument. The Microsoft Visual J++ compiler also supports an equivalent syntax:</span></span>
    
    ```java 
     
        ConnectionEventHandler handler =  
            new ConnectionEventHandler(this.onConnectComplete); 
    ```
    
    <span data-ttu-id="150c7-116">

单个参数是对所需的类 (\*\*this\*\*) 以及该类中的方法 (\*\*onConnectComplete\*\*) 的引用。
</span><span class="sxs-lookup"><span data-stu-id="150c7-116">The single argument is a reference to the desired class (**this**) and method within the class (**onConnectComplete**).</span></span>

3.  <span data-ttu-id="150c7-117">将事件处理程序添加到指定用于处理特定类型事件的处理程序所组成的列表中。</span><span class="sxs-lookup"><span data-stu-id="150c7-117">Add your event handler to a list of handlers designated to process a particular type of event.</span></span> <span data-ttu-id="150c7-118">使用具有名称的方法，如 \**addOn \*\*\* EventName*（*处理*）。</span><span class="sxs-lookup"><span data-stu-id="150c7-118">Use the method with a name such as \**addOn\*\*\*EventName*(*handler*).</span></span>

4.  <span data-ttu-id="150c7-p107">ADO/WFC 在内部实现了所有 ADO 事件处理程序。因此，由 **Connection** 或 **Recordset** 操作导致的事件将被 ADO/WFC 事件处理程序截获。 ADO/WFC 事件处理程序在 ADO/WFC **ConnectionEvent** 类实例中传递 ADO **ConnectionEvent** 参数，或在 ADO/WFC **RecordsetEvent** 类实例中传递 ADO **RecordsetEvent** 参数。这些 ADO/WFC 类将 ADO 事件参数合并在一起；就是说，对于所有 ADO **ConnectionEvent** 或 **RecordsetEvent** 方法中的每个唯一的参数，每个 ADO/WFC 类都包含一个相应的数据成员。</span><span class="sxs-lookup"><span data-stu-id="150c7-p107">ADO/WFC internally implements all the ADO event handlers. Therefore, an event caused by a **Connection** or **Recordset** operation is intercepted by an ADO/WFC event handler. The ADO/WFC event handler passes ADO **ConnectionEvent** parameters in an instance of the ADO/WFC **ConnectionEvent** class, or ADO **RecordsetEvent** parameters in an instance of the ADO/WFC **RecordsetEvent** class. These ADO/WFC classes consolidate the ADO event parameters; that is, each ADO/WFC class contains one data member for each unique parameter in all the ADO **ConnectionEvent** or **RecordsetEvent** methods.</span></span>

5.  <span data-ttu-id="150c7-p108">然后，ADO/WFC 通过 ADO/WFC 事件对象调用事件处理程序。例如， **onConnectComplete** 处理程序有一个类似如下的签名：</span><span class="sxs-lookup"><span data-stu-id="150c7-p108">ADO/WFC then calls your event handler with the ADO/WFC event object. For example, your **onConnectComplete** handler has a signature like this:</span></span>
    
    ```java 
     
        public void onConnectComplete(Object sender,ConnectionEvent e) 
    ```
    
    <span data-ttu-id="150c7-125">第一个参数为发送事件 （[连接](connection-object-ado.md)或[Recordset](recordset-object-ado.md)） 的对象的类型和第二个参数是 ADO/WFC 事件对象 （**ConnectionEvent**或**RecordsetEvent**）。</span><span class="sxs-lookup"><span data-stu-id="150c7-125">The first argument is the type of object that sent the event ([Connection](connection-object-ado.md) or [Recordset](recordset-object-ado.md)), and the second argument is the ADO/WFC event object (**ConnectionEvent** or **RecordsetEvent**).</span></span> <span data-ttu-id="150c7-126">事件处理程序的签名比 ADO 事件更简单。</span><span class="sxs-lookup"><span data-stu-id="150c7-126">The signature of your event handler is simpler than an ADO event.</span></span> <span data-ttu-id="150c7-127">但是，仍然必须理解 ADO 事件模型，才能知道什么参数将应用于事件以及如何响应。</span><span class="sxs-lookup"><span data-stu-id="150c7-127">However, you must still understand the ADO event model to know what parameters apply to an event and how to respond.</span></span>

6.  <span data-ttu-id="150c7-p110">从事件处理程序返回到 ADO 事件的 ADO/WFC 处理程序。ADO/WFC 会将相关的 ADO/WFC 事件数据成员复制回 ADO 事件参数，然后 ADO 事件处理程序返回。</span><span class="sxs-lookup"><span data-stu-id="150c7-p110">Return from your event handler to the ADO/WFC handler for the ADO event. ADO/WFC copies pertinent ADO/WFC event data members back to the ADO event parameters, and then the ADO event handler returns.</span></span>

7.  <span data-ttu-id="150c7-130">完成处理后，请从 ADO/WFC 事件处理程序列表中删除处理程序。</span><span class="sxs-lookup"><span data-stu-id="150c7-130">When you are finished processing, remove your handler from the list of ADO/WFC event handlers.</span></span> <span data-ttu-id="150c7-131">使用具有名称的方法，如 \**removeOn \*\*\* EventName*（*处理*）。</span><span class="sxs-lookup"><span data-stu-id="150c7-131">Use the method with a name such as \**removeOn\*\*\*EventName*(*handler*).</span></span>

