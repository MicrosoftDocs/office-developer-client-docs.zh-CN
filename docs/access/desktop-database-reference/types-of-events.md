---
title: 类型的事件 （Access 桌面数据库参考 （英文）
TOCTitle: Types of Events
ms:assetid: 94660fc1-65c3-1d21-c451-f3898014e0b6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249660(v=office.15)
ms:contentKeyID: 48546414
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ffb3bd48db4d8071e56553f4ea5bf79b83952466
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467193"
---
# <a name="types-of-events"></a><span data-ttu-id="cb6f6-102">事件类型</span><span class="sxs-lookup"><span data-stu-id="cb6f6-102">Types of Events</span></span>


<span data-ttu-id="cb6f6-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cb6f6-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="cb6f6-p101">事件有两种基本类型。一种是"Will 事件"，在操作开始之前调用，通常名称中包括"Will"，如 **WillChangeRecordset** 或 **WillConnect** 。而在事件完成之后调用的事件，其名称中往往包括"Complete"，如 **RecordChangeComplete** 或 **ConnectComplete** 。也有例外情况，如 **InfoMessage** ，不过它发生在关联的操作完成之后。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-p101">There are two basic types of events. "Will Events," which are called before an operation starts, usually include "Will" in their names — for example, **WillChangeRecordset** or **WillConnect**. Events that are called after an event has been completed usually include "Complete" in their names — for example, **RecordChangeComplete** or **ConnectComplete**. Exceptions exist — such as **InfoMessage** — but these occur after the associated operation has completed.</span></span>

## <a name="will-events"></a><span data-ttu-id="cb6f6-108">Will 事件</span><span class="sxs-lookup"><span data-stu-id="cb6f6-108">Will Events</span></span>

<span data-ttu-id="cb6f6-109">在操作开始之前调用的事件处理程序，为您提供了检查或修改操作参数、随后或取消操作或允许操作完成的机会。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-109">Event handlers called before the operation starts offer you the opportunity to examine or modify the operation parameters, and then either cancel the operation or allow it to complete.</span></span> <span data-ttu-id="cb6f6-110">这些事件处理程序例程通常具有窗体的名称 \**将*事件 \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-110">These event-handler routines usually have names of the form \**Will*Event\*\*\*.</span></span>

## <a name="complete-events"></a><span data-ttu-id="cb6f6-111">Complete 事件</span><span class="sxs-lookup"><span data-stu-id="cb6f6-111">Complete Events</span></span>

<span data-ttu-id="cb6f6-112">在操作完成之后调用的事件处理程序可以通知应用程序操作已结束。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-112">Event handlers called after an operation completes can notify your application that an operation has concluded.</span></span> <span data-ttu-id="cb6f6-113">如果 Will 事件处理程序取消了挂起的操作，则也会通知此事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-113">Such an event handler is also notified when a Will event handler cancels a pending operation.</span></span> <span data-ttu-id="cb6f6-114">这些事件处理程序例程通常具有窗体的名称 \***事件 \* 完成**。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-114">These event-handler routines usually have names of the form \***Event\*Complete**.</span></span>

<span data-ttu-id="cb6f6-115">Will 和 Complete 事件通常成对使用。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-115">Will and Complete events are typically used in pairs.</span></span>

## <a name="other-events"></a><span data-ttu-id="cb6f6-116">其他事件</span><span class="sxs-lookup"><span data-stu-id="cb6f6-116">Other Events</span></span>

<span data-ttu-id="cb6f6-117">其他事件处理程序 — 即，其名称不窗体的事件**将 \* 事件**\* 或 \***事件 \* 完成 —** 仅在操作完成之后调用。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-117">The other event handlers — that is, events whose names are not of the form **Will\*Event**\* or \***Event\*Complete —** are called only after an operation completes.</span></span> <span data-ttu-id="cb6f6-118">这些事件包括 **Disconnect** 、 **EndOfRecordset** 和 **InfoMessage** 。</span><span class="sxs-lookup"><span data-stu-id="cb6f6-118">These events are **Disconnect**, **EndOfRecordset**, and **InfoMessage**.</span></span>

