---
title: ConnectComplete 和 Disconnect 事件 (ADO)
TOCTitle: ConnectComplete and Disconnect Events (ADO)
ms:assetid: 8ecb080b-7fc9-7565-25bd-bd57b983750d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249629(v=office.15)
ms:contentKeyID: 48546293
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 731879abf181f64c24b1012e45ea23435f965574
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468175"
---
# <a name="connectcomplete-and-disconnect-events-ado"></a><span data-ttu-id="c259b-102">ConnectComplete 和 Disconnect 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c259b-102">ConnectComplete and Disconnect Events (ADO)</span></span>


<span data-ttu-id="c259b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c259b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c259b-p101">**ConnectComplete** 事件在连接*启动*之后调用。**Disconnect** 事件在连接*终止*之后调用。</span><span class="sxs-lookup"><span data-stu-id="c259b-p101">The **ConnectComplete** event is called after a connection *starts*. The **Disconnect** event is called after a connection *ends*.</span></span>

## <a name="syntax"></a><span data-ttu-id="c259b-106">语法</span><span class="sxs-lookup"><span data-stu-id="c259b-106">Syntax</span></span>

<span data-ttu-id="c259b-107">ConnectComplete*pError*， *adStatus* *pConnection*</span><span class="sxs-lookup"><span data-stu-id="c259b-107">ConnectComplete*pError*, *adStatus*, *pConnection*</span></span>

<span data-ttu-id="c259b-108">断开*adStatus*， *pConnection*</span><span class="sxs-lookup"><span data-stu-id="c259b-108">Disconnect*adStatus*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="c259b-109">参数</span><span class="sxs-lookup"><span data-stu-id="c259b-109">Parameters</span></span>

  - <span data-ttu-id="c259b-110">*pError*</span><span class="sxs-lookup"><span data-stu-id="c259b-110">*pError*</span></span>

  - <span data-ttu-id="c259b-p102">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="c259b-p102">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>

  - <span data-ttu-id="c259b-113">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="c259b-113">*adStatus*</span></span>

  - [<span data-ttu-id="c259b-114">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="c259b-114">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="c259b-115">调用 **ConnectComplete** 时，如果 **WillConnect** 事件已请求取消挂起的连接，则该参数设置为 **adStatusCancel** 。</span><span class="sxs-lookup"><span data-stu-id="c259b-115">When **ConnectComplete** is called, this parameter is set to **adStatusCancel** if a **WillConnect** event has requested cancellation of the pending connection.</span></span>
    
    <span data-ttu-id="c259b-p103">在任何一个事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。但是，关闭然后重新打开 [Connection](connection-object-ado.md) 会导致这些事件再次发生。</span><span class="sxs-lookup"><span data-stu-id="c259b-p103">Before either event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications. However, closing and reopening the [Connection](connection-object-ado.md) causes these events to occur again.</span></span>

  - <span data-ttu-id="c259b-118">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="c259b-118">*pConnection*</span></span>

  - <span data-ttu-id="c259b-119">为其应用该事件的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="c259b-119">The **Connection** object for which this event applies.</span></span>
