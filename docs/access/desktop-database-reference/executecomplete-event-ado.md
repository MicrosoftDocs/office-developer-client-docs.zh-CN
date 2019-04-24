---
title: ExecuteComplete 事件 (ADO)
TOCTitle: ExecuteComplete event (ADO)
ms:assetid: 47317d97-e373-32f4-9438-2dff46b8d367
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249219(v=office.15)
ms:contentKeyID: 48544589
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8a094968e70ace5e6cba1df184bf0ba57c2d7789
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293222"
---
# <a name="executecomplete-event-ado"></a><span data-ttu-id="f6dcf-102">ExecuteComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="f6dcf-102">ExecuteComplete event (ADO)</span></span>

<span data-ttu-id="f6dcf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f6dcf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f6dcf-104">**ExecuteComplete** 事件在命令执行完毕之后调用。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-104">The **ExecuteComplete** event is called after a command has finished executing.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6dcf-105">语法</span><span class="sxs-lookup"><span data-stu-id="f6dcf-105">Syntax</span></span>

<span data-ttu-id="f6dcf-106">ExecuteComplete*RecordsAffected*、 *pError*、 *adStatus*、 *pCommand*、 *pRecordset*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="f6dcf-106">ExecuteComplete*RecordsAffected*, *pError*, *adStatus*, *pCommand*, *pRecordset*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="f6dcf-107">参数</span><span class="sxs-lookup"><span data-stu-id="f6dcf-107">Parameters</span></span>

|<span data-ttu-id="f6dcf-108">参数</span><span class="sxs-lookup"><span data-stu-id="f6dcf-108">Parameter</span></span>|<span data-ttu-id="f6dcf-109">描述</span><span class="sxs-lookup"><span data-stu-id="f6dcf-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="f6dcf-110">*RecordsAffected*</span><span class="sxs-lookup"><span data-stu-id="f6dcf-110">*RecordsAffected*</span></span> |<span data-ttu-id="f6dcf-111">**长整型** 值，指示受命令影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-111">A **Long** value indicating the number of records affected by the command.</span></span>|
|<span data-ttu-id="f6dcf-112">*pError*</span><span class="sxs-lookup"><span data-stu-id="f6dcf-112">*pError*</span></span> |<span data-ttu-id="f6dcf-p101">[Error](error-object-ado.md) 对象。如果 **adStatus** 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-p101">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of **adStatus** is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>|
|<span data-ttu-id="f6dcf-115">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="f6dcf-115">*adStatus*</span></span> |<span data-ttu-id="f6dcf-116">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-116">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="f6dcf-117">在此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-117">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>|
|<span data-ttu-id="f6dcf-118">*pCommand*</span><span class="sxs-lookup"><span data-stu-id="f6dcf-118">*pCommand*</span></span> |<span data-ttu-id="f6dcf-p103">已执行的 [Command](command-object-ado.md) 对象。即使在不显式创建 **Command** 的情况下调用 **Connection.Execute** 或 **Recordset.Open** 时（在这种情况下， **Command** 对象由 ADO 在内部创建），也包含一个 **Command** 对象。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-p103">The [Command](command-object-ado.md) object that was executed. Contains a **Command** object even when calling **Connection.Execute** or **Recordset.Open** without explicitly creating a **Command**, in which cases the **Command** object is created internally by ADO.</span></span>|
|<span data-ttu-id="f6dcf-121">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="f6dcf-121">*pRecordset*</span></span> |<span data-ttu-id="f6dcf-p104">作为已执行命令的结果的 [Recordset](recordset-object-ado.md) 对象。该 **Recordset** 可以为空。您绝不能从该事件处理程序内销毁此 Recordset 对象，否则，当 ADO 尝试访问不再存在的对象时，会导致违规存取错误。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-p104">A [Recordset](recordset-object-ado.md) object that is the result of the executed command. This **Recordset** may be empty. You should never destroy this Recordset object from within this event handler. Doing so will result in an Access Violation when ADO tries to access an object that no longer exists.</span></span>|
|<span data-ttu-id="f6dcf-126">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="f6dcf-126">*pConnection*</span></span> |<span data-ttu-id="f6dcf-p105">[Connection](connection-object-ado.md) 对象。操作通过该连接执行。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-p105">A [Connection](connection-object-ado.md) object. The connection over which the operation was executed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f6dcf-129">注解</span><span class="sxs-lookup"><span data-stu-id="f6dcf-129">Remarks</span></span>

<span data-ttu-id="f6dcf-130">**ExecuteComplete** 事件发生的原因可能是 **Connection.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection)、**Command.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)、**Recordset.**[Open](open-method-ado-recordset.md)、**Recordset.**[Requery](requery-method-ado.md) 或 **Recordset.**[NextRecordset](nextrecordset-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f6dcf-130">An **ExecuteComplete** event may occur due to the **Connection.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection), **Command.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command), **Recordset.**[Open](open-method-ado-recordset.md), **Recordset.**[Requery](requery-method-ado.md), or **Recordset.**[NextRecordset](nextrecordset-method-ado.md) methods.</span></span>

