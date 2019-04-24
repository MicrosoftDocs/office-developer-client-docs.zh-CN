---
title: ConnectComplete 和 Disconnect 事件 (ADO)
TOCTitle: ConnectComplete and Disconnect events (ADO)
ms:assetid: 8ecb080b-7fc9-7565-25bd-bd57b983750d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249629(v=office.15)
ms:contentKeyID: 48546293
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e1e1d4487eb113c25e25ce6b9de051e33a4536b3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295987"
---
# <a name="connectcomplete-and-disconnect-events-ado"></a><span data-ttu-id="f2737-102">ConnectComplete 和 Disconnect 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="f2737-102">ConnectComplete and Disconnect events (ADO)</span></span>

<span data-ttu-id="f2737-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f2737-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f2737-104">**ConnectComplete** 事件在连接*启动*之后调用。</span><span class="sxs-lookup"><span data-stu-id="f2737-104">The **ConnectComplete** event is called after a connection *starts*.</span></span> <span data-ttu-id="f2737-105">**Disconnect** 事件在连接*终止*之后调用。</span><span class="sxs-lookup"><span data-stu-id="f2737-105">The **Disconnect** event is called after a connection *ends*.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2737-106">语法</span><span class="sxs-lookup"><span data-stu-id="f2737-106">Syntax</span></span>

<span data-ttu-id="f2737-107">ConnectComplete*pError*、 *adStatus*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="f2737-107">ConnectComplete*pError*, *adStatus*, *pConnection*</span></span>

<span data-ttu-id="f2737-108">断开连接*adStatus*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="f2737-108">Disconnect*adStatus*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="f2737-109">参数</span><span class="sxs-lookup"><span data-stu-id="f2737-109">Parameters</span></span>

|<span data-ttu-id="f2737-110">参数</span><span class="sxs-lookup"><span data-stu-id="f2737-110">Parameter</span></span>|<span data-ttu-id="f2737-111">描述</span><span class="sxs-lookup"><span data-stu-id="f2737-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="f2737-112">*pError*</span><span class="sxs-lookup"><span data-stu-id="f2737-112">*pError*</span></span> |<span data-ttu-id="f2737-p102">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="f2737-p102">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>|
|<span data-ttu-id="f2737-115">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="f2737-115">*adStatus*</span></span> |<span data-ttu-id="f2737-116">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="f2737-116">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="f2737-117">调用 **ConnectComplete** 时，如果 **WillConnect** 事件已请求取消挂起的连接，则该参数设置为 **adStatusCancel** 。</span><span class="sxs-lookup"><span data-stu-id="f2737-117">When **ConnectComplete** is called, this parameter is set to **adStatusCancel** if a **WillConnect** event has requested cancellation of the pending connection.</span></span><br/><br/><span data-ttu-id="f2737-p104">在任何一个事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。但是，关闭然后重新打开 [Connection](connection-object-ado.md) 会导致这些事件再次发生。</span><span class="sxs-lookup"><span data-stu-id="f2737-p104">Before either event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications. However, closing and reopening the [Connection](connection-object-ado.md) causes these events to occur again.</span></span>|
|<span data-ttu-id="f2737-120">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="f2737-120">*pConnection*</span></span> |<span data-ttu-id="f2737-121">为其应用该事件的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="f2737-121">The **Connection** object for which this event applies.</span></span>|

