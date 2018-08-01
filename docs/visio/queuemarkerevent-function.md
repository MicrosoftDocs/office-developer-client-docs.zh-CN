---
title: QUEUEMARKEREVENT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60107
localization_priority: Normal
ms.assetid: b4671715-4209-7774-c174-c19dc9721a02
description: 将导致触发到您的加载项，Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项的标记事件的应用程序。
ms.openlocfilehash: b9175caf0845530c93f6db15e286f3eae21ea415
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781003"
---
# <a name="queuemarkerevent-function"></a><span data-ttu-id="08c06-103">QUEUEMARKEREVENT 函数</span><span class="sxs-lookup"><span data-stu-id="08c06-103">QUEUEMARKEREVENT Function</span></span>

<span data-ttu-id="08c06-104">将导致触发到您的加载项，Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项的标记事件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="08c06-104">Causes the application to fire a marker event to your add-on, Microsoft Visual Basic for Applications (VBA) code, or COM add-in.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="08c06-105">语法</span><span class="sxs-lookup"><span data-stu-id="08c06-105">Syntax</span></span>

<span data-ttu-id="08c06-106">QUEUEMARKEREVENT (* * *event_string* * *)</span><span class="sxs-lookup"><span data-stu-id="08c06-106">QUEUEMARKEREVENT (** *event_string* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="08c06-107">参数</span><span class="sxs-lookup"><span data-stu-id="08c06-107">Parameters</span></span>

|<span data-ttu-id="08c06-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="08c06-108">**Name**</span></span>|<span data-ttu-id="08c06-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="08c06-109">**Required/Optional**</span></span>|<span data-ttu-id="08c06-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="08c06-110">**Data Type**</span></span>|<span data-ttu-id="08c06-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="08c06-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="08c06-112">_event_string_</span><span class="sxs-lookup"><span data-stu-id="08c06-112">_event_string_</span></span> <br/> |<span data-ttu-id="08c06-113">必需</span><span class="sxs-lookup"><span data-stu-id="08c06-113">Required</span></span>  <br/> |<span data-ttu-id="08c06-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="08c06-114">**String**</span></span> <br/> | <span data-ttu-id="08c06-115">要传递给事件处理程序的字符串。</span><span class="sxs-lookup"><span data-stu-id="08c06-115">The string to pass to your event handler.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="08c06-116">说明</span><span class="sxs-lookup"><span data-stu-id="08c06-116">Remarks</span></span>

<span data-ttu-id="08c06-117">QUEUEMARKEREVENT 函数为开发人员提供一种方法来通知从 ShapeSheet 单元格，其代码并将特定于解决方案的信息传递。</span><span class="sxs-lookup"><span data-stu-id="08c06-117">The QUEUEMARKEREVENT function provides developers with a way to notify their code from a ShapeSheet cell, and pass solution-specific information.</span></span> <span data-ttu-id="08c06-118">包含与 QUEUEMARKEREVENT 函数的公式的单元格计算时，应用程序实例将触发标记事件，并将_event_string_传递给**MarkerEvent**事件侦听的所有事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="08c06-118">When the cell containing the formula with the QUEUEMARKEREVENT function is evaluated, the application fires a marker event and passes  _event_string_ to all event handlers that are listening to the **MarkerEvent** event.</span></span> 
  
<span data-ttu-id="08c06-119">有关标记事件的详细信息，请参阅**QueueMarkerEvent**方法和**MarkerEvent**事件主题 Microsoft Visio 自动化参考中。</span><span class="sxs-lookup"><span data-stu-id="08c06-119">For more information about marker events, see the **QueueMarkerEvent** method and **MarkerEvent** event topics in the Microsoft Visio Automation Reference.</span></span> 
  
## <a name="example"></a><span data-ttu-id="08c06-120">示例</span><span class="sxs-lookup"><span data-stu-id="08c06-120">Example</span></span>

<span data-ttu-id="08c06-121">QUEUEMARKEREVENT ("MyCustomNotification")</span><span class="sxs-lookup"><span data-stu-id="08c06-121">QUEUEMARKEREVENT ("MyCustomNotification")</span></span> 
  
<span data-ttu-id="08c06-122">导致应用程序触发标记事件，并将字符串“MyCustomNotification”传递给正在侦听 **MarkerEvent** 事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="08c06-122">Causes the application to fire a marker event, and passes the string "MyCustomNotification" to event handlers that are listening to the **MarkerEvent** event.</span></span> 
  

