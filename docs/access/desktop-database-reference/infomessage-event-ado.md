---
title: InfoMessage 事件 (ADO)
TOCTitle: InfoMessage Event (ADO)
ms:assetid: 5d4f487f-96c8-4cf6-60ab-583510d3096f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249328(v=office.15)
ms:contentKeyID: 48545109
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6cc3b69eb3310d8e717605edd3d6fae32d635806
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468919"
---
# <a name="infomessage-event-ado"></a><span data-ttu-id="2d776-102">InfoMessage 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2d776-102">InfoMessage Event (ADO)</span></span>


<span data-ttu-id="2d776-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2d776-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2d776-104">只要在 **ConnectionEvent** 操作期间发生警告，便会调用 **InfoMessage** 事件。</span><span class="sxs-lookup"><span data-stu-id="2d776-104">The **InfoMessage** event is called whenever a warning occurs during a **ConnectionEvent** operation.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d776-105">语法</span><span class="sxs-lookup"><span data-stu-id="2d776-105">Syntax</span></span>

<span data-ttu-id="2d776-106">InfoMessage*pError*， *adStatus* *pConnection*</span><span class="sxs-lookup"><span data-stu-id="2d776-106">InfoMessage*pError*, *adStatus*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="2d776-107">参数</span><span class="sxs-lookup"><span data-stu-id="2d776-107">Parameters</span></span>

  - <span data-ttu-id="2d776-108">*pError*</span><span class="sxs-lookup"><span data-stu-id="2d776-108">*pError*</span></span>

  - <span data-ttu-id="2d776-p101">[Error](error-object-ado.md) 对象。此参数包含返回的任何错误。如果返回了多个错误，则枚举 **Errors** 集合以找到这些错误。</span><span class="sxs-lookup"><span data-stu-id="2d776-p101">An [Error](error-object-ado.md) object. This parameter contains any errors that are returned. If multiple errors are returned, enumerate the **Errors** collection to find them.</span></span>

  - <span data-ttu-id="2d776-112">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="2d776-112">*adStatus*</span></span>

  - [<span data-ttu-id="2d776-113">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="2d776-113">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="2d776-114">在此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="2d776-114">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="2d776-115">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="2d776-115">*pConnection*</span></span>

  - <span data-ttu-id="2d776-p102">[Connection](connection-object-ado.md) 对象。发生警告的连接。例如，当打开 **Connection** 对象或对 [Connection](command-object-ado.md) 执行 **Command** 时，会发生警告。</span><span class="sxs-lookup"><span data-stu-id="2d776-p102">A [Connection](connection-object-ado.md) object. The connection for which the warning occurred. For example, warnings can occur when opening a **Connection** object or executing a [Command](command-object-ado.md) on a **Connection**.</span></span>

