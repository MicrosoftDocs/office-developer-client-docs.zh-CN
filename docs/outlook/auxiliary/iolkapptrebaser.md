---
title: IOlkApptRebaser
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d67bd395-d324-217d-8ddc-1d48dd724383
description: 支持重设置日历文件夹中的约会的Babas。
ms.openlocfilehash: cf4f7c790a8561f149160c83418a0d5ebd91a455
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410068"
---
# <a name="iolkapptrebaser"></a><span data-ttu-id="58ca3-103">IOlkApptRebaser</span><span class="sxs-lookup"><span data-stu-id="58ca3-103">IOlkApptRebaser</span></span>

<span data-ttu-id="58ca3-104">支持重设置日历文件夹中的约会的Babas。</span><span class="sxs-lookup"><span data-stu-id="58ca3-104">Supports rebasing appointments in a calendar folder.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="58ca3-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="58ca3-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="58ca3-106">继承自：</span><span class="sxs-lookup"><span data-stu-id="58ca3-106">Inherits from:</span></span>  <br/> |<span data-ttu-id="58ca3-107">**IUnknown**</span><span class="sxs-lookup"><span data-stu-id="58ca3-107">**IUnknown**</span></span> <br/> |
|<span data-ttu-id="58ca3-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="58ca3-108">Header file:</span></span>  <br/> |<span data-ttu-id="58ca3-109">tzmovelib.h</span><span class="sxs-lookup"><span data-stu-id="58ca3-109">tzmovelib.h</span></span>  <br/> |
|<span data-ttu-id="58ca3-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="58ca3-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="58ca3-111">tzmovelib.dll</span><span class="sxs-lookup"><span data-stu-id="58ca3-111">tzmovelib.dll</span></span>  <br/> |
|<span data-ttu-id="58ca3-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="58ca3-112">Called by:</span></span>  <br/> |<span data-ttu-id="58ca3-113">MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="58ca3-113">MAPI client applications</span></span>  <br/> |
|<span data-ttu-id="58ca3-114">在：</span><span class="sxs-lookup"><span data-stu-id="58ca3-114">Exposed on:</span></span>  <br/> |<span data-ttu-id="58ca3-115">Outlook重做对象</span><span class="sxs-lookup"><span data-stu-id="58ca3-115">Outlook rebasing object</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="58ca3-116">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="58ca3-116">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="58ca3-117">**[BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md)**</span><span class="sxs-lookup"><span data-stu-id="58ca3-117">**[BeginEnumerateAppointments](iolkapptrebaser-beginenumerateappointments.md)**</span></span> <br/> |<span data-ttu-id="58ca3-118">从开始的任务在日历文件夹以查找需要重定基址的约会的约会枚举。</span><span class="sxs-lookup"><span data-stu-id="58ca3-118">Begins a task for appointment enumeration in a calendar folder to find the appointments that need rebasing.</span></span>  <br/> |
|<span data-ttu-id="58ca3-119">**[EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)**</span><span class="sxs-lookup"><span data-stu-id="58ca3-119">**[EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)**</span></span> <br/> |<span data-ttu-id="58ca3-120">等待要完成的日历文件夹中的约会枚举和返回的约会列表，需要重定基址。</span><span class="sxs-lookup"><span data-stu-id="58ca3-120">Waits for appointment enumeration in a calendar folder to complete and returns a list of appointments that need rebasing.</span></span>  <br/> |
|<span data-ttu-id="58ca3-121">**[BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)**</span><span class="sxs-lookup"><span data-stu-id="58ca3-121">**[BeginRebaseAppointments](iolkapptrebaser-beginrebaseappointments.md)**</span></span> <br/> |<span data-ttu-id="58ca3-122">在给定约会列表（通常从 **EndEnumerateAppointments** 获取）后，开始为约会重设定底值的任务。</span><span class="sxs-lookup"><span data-stu-id="58ca3-122">Begins a task for appointment rebasing given a list of appointments, usually obtained from **EndEnumerateAppointments**.</span></span>  <br/> |
|<span data-ttu-id="58ca3-123">**[EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)**</span><span class="sxs-lookup"><span data-stu-id="58ca3-123">**[EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)**</span></span> <br/> |<span data-ttu-id="58ca3-124">等待约会重定基址来完成，并检索结果。</span><span class="sxs-lookup"><span data-stu-id="58ca3-124">Waits for appointment rebasing to complete and retrieves the results.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="58ca3-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58ca3-125">See also</span></span>

- [<span data-ttu-id="58ca3-126">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="58ca3-126">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

