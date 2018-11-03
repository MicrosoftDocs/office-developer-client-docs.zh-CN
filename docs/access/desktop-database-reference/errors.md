---
title: 错误 （访问桌面数据库参考 （英文）
TOCTitle: Errors
ms:assetid: 42f5cab9-f32a-d789-10e8-8d73892427f6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249199(v=office.15)
ms:contentKeyID: 48544490
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4f8514fddb5523b670e2dff2b9b55981cab52f72
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946984"
---
# <a name="errors"></a><span data-ttu-id="df6df-102">错误</span><span class="sxs-lookup"><span data-stu-id="df6df-102">Errors</span></span>

<span data-ttu-id="df6df-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="df6df-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="df6df-104">任何涉及 ADO 对象的操作都可以生成提供程序错误。</span><span class="sxs-lookup"><span data-stu-id="df6df-104">Any operation involving ADO objects can generate one or more provider errors.</span></span> <span data-ttu-id="df6df-105">每个错误发生时，系统会将 **Error** 对象放在 **Connection** 对象的 **Errors** 集合中。</span><span class="sxs-lookup"><span data-stu-id="df6df-105">As each error occurs, one or more **Error** objects are placed in the **Errors** collection of the **Connection** object.</span></span> <span data-ttu-id="df6df-106">有关处理警告和错误 ADO 应用程序中的详细信息，请参阅[第 6 章： 错误处理](chapter-6-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="df6df-106">For details about handling warnings and errors in your ADO application, see [Chapter 6: Error handling](chapter-6-error-handling.md).</span></span>

<span data-ttu-id="df6df-p102">应用程序错误可以由单独的机制引发。例如，在 Visual Basic 中， **Err** 对象将包含应用程序级别的错误。</span><span class="sxs-lookup"><span data-stu-id="df6df-p102">Application errors can be raised by a separate mechanism. For example, in Visual Basic, the **Err** object will contain application-level errors.</span></span>

