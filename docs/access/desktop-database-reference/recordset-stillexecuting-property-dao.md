---
title: Recordset.StillExecuting 属性 (DAO)
TOCTitle: StillExecuting Property
ms:assetid: 0e53c98f-17ac-3569-d780-540a6932013e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845245(v=office.15)
ms:contentKeyID: 48543245
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1195a45c3846cf79a45c16cda8e23bc95ef8156d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707533"
---
# <a name="recordsetstillexecuting-property-dao"></a><span data-ttu-id="1d480-102">Recordset.StillExecuting 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1d480-102">Recordset.StillExecuting property (DAO)</span></span>

<span data-ttu-id="1d480-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1d480-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="1d480-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d480-104">Syntax</span></span>

<span data-ttu-id="1d480-105">*表达式*。StillExecuting</span><span class="sxs-lookup"><span data-stu-id="1d480-105">*expression* .StillExecuting</span></span>

<span data-ttu-id="1d480-106">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="1d480-106">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d480-107">注解</span><span class="sxs-lookup"><span data-stu-id="1d480-107">Remarks</span></span>

<span data-ttu-id="1d480-p101">使用 **StillExecuting** 属性可以确定最近调用的异步 **Execute** 或 **OpenConnection** 方法（即用 **dbRunAsync** 选项执行的方法）是否已完成。在 **StillExecuting** 属性为 **True** 的情况下，不能访问任何返回的对象。</span><span class="sxs-lookup"><span data-stu-id="1d480-p101">Use the **StillExecuting** property to determine if the most recently called asynchronous **Execute** or **OpenConnection** method (that is, a method executed with the **dbRunAsync** option) is complete. While the **StillExecuting** property is **True**, any returned object cannot be accessed.</span></span>

<span data-ttu-id="1d480-p102">一旦 **StillExecuting** 属性返回 **False**，在返回相关 **Connection** 对象的 **OpenConnection** 调用之后，即可引用该对象。只要 **StillExecuting** 仍为 **True**，就不能引用该对象，而只能读取 **StillExecuting** 属性。</span><span class="sxs-lookup"><span data-stu-id="1d480-p102">Once the **StillExecuting** property returns **False**, following the **OpenConnection** call that returns the associated **Connection** object, the object can be referenced. So long as **StillExecuting** remains **True**, the object may not be referenced, other than to read the **StillExecuting** property.</span></span>

<span data-ttu-id="1d480-112">使用 **[Cancel](connection-cancel-method-dao.md)** 方法可以终止执行正在进行的任务。</span><span class="sxs-lookup"><span data-stu-id="1d480-112">Use the **[Cancel](connection-cancel-method-dao.md)** method to terminate execution of a task in progress.</span></span>

