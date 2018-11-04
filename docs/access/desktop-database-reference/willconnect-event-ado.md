---
title: WillConnect 事件 (ADO)
TOCTitle: WillConnect event (ADO)
ms:assetid: 8b0e9955-4e7a-7af8-ce6c-7a4ba569a5bb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249611(v=office.15)
ms:contentKeyID: 48546208
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c8ac4ab83062d9297483b7ee4883ab0b289af227
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949829"
---
# <a name="willconnect-event-ado"></a><span data-ttu-id="72954-102">WillConnect 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="72954-102">WillConnect event (ADO)</span></span>

<span data-ttu-id="72954-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="72954-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="72954-104">**WillConnect** 事件在连接启动之前调用。</span><span class="sxs-lookup"><span data-stu-id="72954-104">The **WillConnect** event is called before a connection starts.</span></span>

## <a name="syntax"></a><span data-ttu-id="72954-105">语法</span><span class="sxs-lookup"><span data-stu-id="72954-105">Syntax</span></span>

<span data-ttu-id="72954-106">WillConnect*ConnectionString*，*用户 Id*，*密码*、*选项*、 *adStatus*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="72954-106">WillConnect*ConnectionString*, *UserID*, *Password*, *Options*, *adStatus*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="72954-107">参数</span><span class="sxs-lookup"><span data-stu-id="72954-107">Parameters</span></span>

|<span data-ttu-id="72954-108">参数</span><span class="sxs-lookup"><span data-stu-id="72954-108">Parameter</span></span>|<span data-ttu-id="72954-109">说明</span><span class="sxs-lookup"><span data-stu-id="72954-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="72954-110">*ConnectionString*</span><span class="sxs-lookup"><span data-stu-id="72954-110">*ConnectionString*</span></span> |<span data-ttu-id="72954-111">**字符串型** ，包含挂起的连接的连接信息。</span><span class="sxs-lookup"><span data-stu-id="72954-111">A **String** that contains connection information for the pending connection.</span></span>|
|<span data-ttu-id="72954-112">*用户 Id*</span><span class="sxs-lookup"><span data-stu-id="72954-112">*UserID*</span></span> |<span data-ttu-id="72954-113">**字符串型** ，包含挂起的连接的用户名。</span><span class="sxs-lookup"><span data-stu-id="72954-113">A **String** that contains a user name for the pending connection.</span></span>|
|<span data-ttu-id="72954-114">*Password*</span><span class="sxs-lookup"><span data-stu-id="72954-114">*Password*</span></span> |<span data-ttu-id="72954-115">**字符串型** ，包含挂起的连接的密码。</span><span class="sxs-lookup"><span data-stu-id="72954-115">A **String** that contains a password for the pending connection.</span></span>|
|<span data-ttu-id="72954-116">*Options*</span><span class="sxs-lookup"><span data-stu-id="72954-116">*Options*</span></span> |<span data-ttu-id="72954-p101">**长整型**值，指示提供程序应如何对 *ConnectionString* 求值。您仅有的选项为 **adAsyncOpen**。</span><span class="sxs-lookup"><span data-stu-id="72954-p101">A **Long** value that indicates how the provider should evaluate the *ConnectionString*. Your only option is **adAsyncOpen**.</span></span>|
|<span data-ttu-id="72954-119">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="72954-119">*adStatus*</span></span> |<span data-ttu-id="72954-120">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="72954-120">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="72954-121">调用此事件时，默认情况下该参数设置为 **adStatusOK** 。</span><span class="sxs-lookup"><span data-stu-id="72954-121">When this event is called, this parameter is set to **adStatusOK** by default.</span></span> <span data-ttu-id="72954-122">如果此事件无法请求取消挂起的操作，则该参数设置为 **adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="72954-122">It is set to **adStatusCantDeny** if the event cannot request cancellation of the pending operation.</span></span><br/><br/><span data-ttu-id="72954-p103">在此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。将该参数设置为 **adStatusCancel** 将请求导致取消此通知的连接操作。</span><span class="sxs-lookup"><span data-stu-id="72954-p103">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications. Set this parameter to **adStatusCancel** to request the connection operation that caused cancellation of this notification.</span></span>|
|<span data-ttu-id="72954-125">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="72954-125">*pConnection*</span></span> |<span data-ttu-id="72954-p104">为其应用该事件通知的 [Connection](connection-object-ado.md) 对象。 **WillConnect** 事件处理程序对 **Connection** 的参数所做的更改对 **Connection** 将没有效果。</span><span class="sxs-lookup"><span data-stu-id="72954-p104">The [Connection](connection-object-ado.md) object for which this event notification applies. Changes to the parameters of the **Connection** by the **WillConnect** event handler will have no effect on the **Connection**.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72954-128">备注</span><span class="sxs-lookup"><span data-stu-id="72954-128">Remarks</span></span>

<span data-ttu-id="72954-p105">调用 **WillConnect** 时，*ConnectionString*、*UserID*、*Password* 和 *Options* 参数设置为由导致该事件的操作（挂起的连接）建立的值，且这些值可以在事件返回之前更改。**WillConnect** 可以返回取消挂起的连接的请求。</span><span class="sxs-lookup"><span data-stu-id="72954-p105">When **WillConnect** is called, the *ConnectionString*, *UserID*, *Password*, and *Options* parameters are set to the values established by the operation that caused this event (the pending connection), and can be changed before the event returns. **WillConnect** may return a request that the pending connection be canceled.</span></span>

<span data-ttu-id="72954-131">取消此事件时，将调用*adStatus*参数设置为**adStatusErrorsOccurred** **ConnectComplete** 。</span><span class="sxs-lookup"><span data-stu-id="72954-131">When this event is canceled, **ConnectComplete** will be called with its *adStatus* parameter set to **adStatusErrorsOccurred**.</span></span>

