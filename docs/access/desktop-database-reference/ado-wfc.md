---
title: ADO for Windows Foundation Classes (ADO/WFC)
TOCTitle: ADO/WFC
ms:assetid: 73206be8-6515-79e4-e904-cc2d0d59411d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249468(v=office.15)
ms:contentKeyID: 48545628
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd5b54160bfa6c692bfcd6489646021dcce34631
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467331"
---
# <a name="adowfc"></a>ADO/WFC


**适用于**： Access 2013 |Office 2013

ADO for Windows Foundation Classes (ADO/WFC) 建立在 ADO 事件模型基础上，它可以提供经过简化的应用程序编程接口。通常，ADO/WFC 可以截获 ADO 事件，并将事件参数合并成单个事件类，然后调用事件处理程序。

**使用 ADO/WFC 的 ADO 事件的方法**

1.  定义您自己的事件处理程序来处理事件。例如，如果想处理 **ConnectionEvent** 系列中的 **ConnectComplete** 事件，可以使用此代码：
    
    ```java 
     
    public void onConnectComplete(Object sender,ConnectionEvent e) 
    { 
        System.out.println("onConnectComplete:" + e); 
    } 
    ```

2.  定义一个处理程序对象来代表事件处理程序。对于类型为 **ConnectionEvent** 的事件，处理程序对象的数据类型应当是 **ConnectEventHandler** ，而对于类型为 **RecordsetEvent** 的事件，其数据类型应当是 **RecordsetEventHandler** 。例如，对于 **ConnectComplete** 事件处理程序，代码应当类似如下：
    
    ```java
        ConnectionEventHandler handler =  
                new ConnectionEventHandler(this, "onConnectComplete"); 
    ```

    **ConnectionEventHandler** 构造函数的第一个参数是一个引用，它引用了第二个参数所命名的事件处理程序所属的类。 Microsoft Visual J++ 编译器还支持等价的语法：
    
    ```java 
     
        ConnectionEventHandler handler =  
            new ConnectionEventHandler(this, "onConnectComplete"); 
    ```
    
    ```java 
     
        ConnectionEventHandler handler =  
            new ConnectionEventHandler(this.onConnectComplete); 
    ```
    
    **ConnectionEventHandler** 构造函数的第一个参数是一个引用，它引用了第二个参数所命名的事件处理程序所属的类。 Microsoft Visual J++ 编译器还支持等价的语法：
    
    ```java 
     
        ConnectionEventHandler handler =  
            new ConnectionEventHandler(this.onConnectComplete); 
    ```
    
    

单个参数是对所需的类 (**this**) 以及该类中的方法 (**onConnectComplete**) 的引用。


3.  将事件处理程序添加到指定用于处理特定类型事件的处理程序所组成的列表中。 使用具有名称的方法，如 **addOn *** EventName*（*处理*）。

4.  ADO/WFC 在内部实现了所有 ADO 事件处理程序。因此，由 **Connection** 或 **Recordset** 操作导致的事件将被 ADO/WFC 事件处理程序截获。 ADO/WFC 事件处理程序在 ADO/WFC **ConnectionEvent** 类实例中传递 ADO **ConnectionEvent** 参数，或在 ADO/WFC **RecordsetEvent** 类实例中传递 ADO **RecordsetEvent** 参数。这些 ADO/WFC 类将 ADO 事件参数合并在一起；就是说，对于所有 ADO **ConnectionEvent** 或 **RecordsetEvent** 方法中的每个唯一的参数，每个 ADO/WFC 类都包含一个相应的数据成员。

5.  然后，ADO/WFC 通过 ADO/WFC 事件对象调用事件处理程序。例如， **onConnectComplete** 处理程序有一个类似如下的签名：
    
    ```java 
     
        public void onConnectComplete(Object sender,ConnectionEvent e) 
    ```
    
    第一个参数为发送事件 （[连接](connection-object-ado.md)或[Recordset](recordset-object-ado.md)） 的对象的类型和第二个参数是 ADO/WFC 事件对象 （**ConnectionEvent**或**RecordsetEvent**）。 事件处理程序的签名比 ADO 事件更简单。 但是，仍然必须理解 ADO 事件模型，才能知道什么参数将应用于事件以及如何响应。

6.  从事件处理程序返回到 ADO 事件的 ADO/WFC 处理程序。ADO/WFC 会将相关的 ADO/WFC 事件数据成员复制回 ADO 事件参数，然后 ADO 事件处理程序返回。

7.  完成处理后，请从 ADO/WFC 事件处理程序列表中删除处理程序。 使用具有名称的方法，如 **removeOn *** EventName*（*处理*）。

