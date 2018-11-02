---
title: Recordset2.StillExecuting 属性 (DAO)
TOCTitle: StillExecuting Property
ms:assetid: f051c350-0451-44fe-0e47-b152bae4b481
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836546(v=office.15)
ms:contentKeyID: 48548601
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 55a5adf32c64735cb773e3f1da5de79703a2a3cc
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930145"
---
# <a name="recordset2stillexecuting-property-dao"></a><span data-ttu-id="29957-102">Recordset2.StillExecuting 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="29957-102">Recordset2.StillExecuting property (DAO)</span></span>


<span data-ttu-id="29957-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="29957-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="29957-104">语法</span><span class="sxs-lookup"><span data-stu-id="29957-104">Syntax</span></span>

<span data-ttu-id="29957-105">*表达式*。StillExecuting</span><span class="sxs-lookup"><span data-stu-id="29957-105">*expression* .StillExecuting</span></span>

<span data-ttu-id="29957-106">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="29957-106">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="29957-107">注解</span><span class="sxs-lookup"><span data-stu-id="29957-107">Remarks</span></span>

<span data-ttu-id="29957-p101">使用 **StillExecuting** 属性可以确定最近调用的异步 **Execute** 或 **OpenConnection** 方法（即用 **dbRunAsync** 选项执行的方法）是否已完成。在 **StillExecuting** 属性为 **True** 的情况下，不能访问任何返回的对象。</span><span class="sxs-lookup"><span data-stu-id="29957-p101">Use the **StillExecuting** property to determine if the most recently called asynchronous **Execute** or **OpenConnection** method (that is, a method executed with the **dbRunAsync** option) is complete. While the **StillExecuting** property is **True**, any returned object cannot be accessed.</span></span>

<span data-ttu-id="29957-p102">一旦 **StillExecuting** 属性返回 **False**，在返回相关 **Connection** 对象的 **OpenConnection** 调用之后，即可引用该对象。只要 **StillExecuting** 仍为 **True**，就不能引用该对象，而只能读取 **StillExecuting** 属性。</span><span class="sxs-lookup"><span data-stu-id="29957-p102">Once the **StillExecuting** property returns **False**, following the **OpenConnection** call that returns the associated **Connection** object, the object can be referenced. So long as **StillExecuting** remains **True**, the object may not be referenced, other than to read the **StillExecuting** property.</span></span>

<span data-ttu-id="29957-112">使用 **[Cancel](connection-cancel-method-dao.md)** 方法可以终止执行正在进行的任务。</span><span class="sxs-lookup"><span data-stu-id="29957-112">Use the **[Cancel](connection-cancel-method-dao.md)** method to terminate execution of a task in progress.</span></span>

