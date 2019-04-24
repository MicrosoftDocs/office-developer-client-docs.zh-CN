---
title: Visual j + + (Access 桌面数据库参考)
TOCTitle: Visual J++
ms:assetid: 5c05db85-cdf2-9a73-fbc5-3dbfa6752376
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249320(v=office.15)
ms:contentKeyID: 48545079
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: da13ae0f10e2338b961f2f12686bd378580a69d7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311331"
---
# <a name="visual-j"></a><span data-ttu-id="623ca-102">Visual J++</span><span class="sxs-lookup"><span data-stu-id="623ca-102">Visual J++</span></span>


<span data-ttu-id="623ca-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="623ca-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="623ca-104">此简短 Microsoft Visual J++ 示例显示如何将您自己的函数与特定事件关联。</span><span class="sxs-lookup"><span data-stu-id="623ca-104">This short Microsoft Visual J++ example shows how you can associate your own function with a particular event.</span></span>

```java 
 
// BeginEventExampleVJ 
import com.ms.wfc.data.*; 
 
public class EventExampleVJ 
{ 
 ConnectionEventHandler handler = new ConnectionEventHandler(this,"onConnectComplete"); 
 
 public void onConnectComplete(Object sender,ConnectionEvent e) 
 { 
 if (e.adStatus == AdoEnums.EventStatus.ERRORSOCCURRED) 
 System.out.println("Connection failed"); 
 else 
 System.out.println("Connection completed"); 
 return; 
 } 
 
 public static void main (String[] args) 
 { 
 EventExampleVJ Class1 = new EventExampleVJ(); 
 Connection conn = new Connection(); 
 
 conn.addOnConnectComplete(Class1.handler); // Enable event support. 
 conn.open("DSN=Pubs"); 
 conn.close(); 
 conn.removeOnConnectComplete(Class1.handler); // Disable event support. 
 } 
} 
// EndEventExampleVJ 
```

<span data-ttu-id="623ca-105">首先，通过创建新的 **ConnectionEventHandler** 对象并将 *onConnectComplete* 函数分配给该对象，使类方法 *onConnectionComplete* 与 **ConnectionComplete** 事件关联。</span><span class="sxs-lookup"><span data-stu-id="623ca-105">First, the class method *onConnectionComplete* is associated with the **ConnectionComplete** event by creating a new **ConnectionEventHandler** object and assigning the *onConnectComplete* function to the object.</span></span>

<span data-ttu-id="623ca-106">然后，*main* 函数创建 **Connection** 对象，并通过调用 **addOnConnectComplete** 方法然后将 *handler* 函数的地址传递给它来启用事件处理。</span><span class="sxs-lookup"><span data-stu-id="623ca-106">The *main* function then creates a **Connection** object and enables event handling by calling the **addOnConnectComplete** method and passing it the address of the *handler* function.</span></span>

