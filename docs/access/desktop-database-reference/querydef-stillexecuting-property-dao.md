---
title: QueryDef.StillExecuting Property (DAO)
TOCTitle: StillExecuting Property
ms:assetid: 98e85d37-de50-afe1-dcca-01623546e0ad
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197953(v=office.15)
ms:contentKeyID: 48546505
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053584
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b8f3c62795b8e3be65b1f768a3c12092b516593c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467194"
---
# <a name="querydefstillexecuting-property-dao"></a><span data-ttu-id="252ef-102">QueryDef.StillExecuting Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="252ef-102">QueryDef.StillExecuting Property (DAO)</span></span>


<span data-ttu-id="252ef-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="252ef-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="252ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="252ef-104">Syntax</span></span>

<span data-ttu-id="252ef-105">*表达式*。StillExecuting</span><span class="sxs-lookup"><span data-stu-id="252ef-105">*expression* .StillExecuting</span></span>

<span data-ttu-id="252ef-106">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="252ef-106">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="252ef-107">注解</span><span class="sxs-lookup"><span data-stu-id="252ef-107">Remarks</span></span>

<span data-ttu-id="252ef-p101">使用 **StillExecuting** 属性可以确定最近调用的异步 **[Execute](querydef-execute-method-dao.md)** 或 **[OpenConnection](dbengine-openconnection-method-dao.md)** 方法（即用 **dbRunAsync** 选项执行的方法）是否已完成。在 **StillExecuting** 属性为 **True** 的情况下，不能访问任何返回的对象。</span><span class="sxs-lookup"><span data-stu-id="252ef-p101">Use the **StillExecuting** property to determine if the most recently called asynchronous **[Execute](querydef-execute-method-dao.md)** or **[OpenConnection](dbengine-openconnection-method-dao.md)** method (that is, a method executed with the **dbRunAsync** option) is complete. While the **StillExecuting** property is **True**, any returned object cannot be accessed.</span></span>

<span data-ttu-id="252ef-p102">一旦 **StillExecuting** 属性返回 **False**，在返回相关 [**Connection**](connection-object-dao.md) 对象的 **OpenConnection** 调用之后，即可引用该对象。只要 **StillExecuting** 仍为 **True**，就不能引用该对象，而只能读取 **StillExecuting** 属性。</span><span class="sxs-lookup"><span data-stu-id="252ef-p102">Once the **StillExecuting** property returns **False**, following the **OpenConnection** call that returns the associated **[Connection](connection-object-dao.md)** object, the object can be referenced. So long as **StillExecuting** remains **True**, the object may not be referenced, other than to read the **StillExecuting** property.</span></span>

<span data-ttu-id="252ef-112">使用 **[Cancel](connection-cancel-method-dao.md)** 方法可以终止执行正在进行的任务。</span><span class="sxs-lookup"><span data-stu-id="252ef-112">Use the **[Cancel](connection-cancel-method-dao.md)** method to terminate execution of a task in progress.</span></span>

