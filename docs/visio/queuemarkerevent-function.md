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
description: 使应用程序触发对加载项的标记事件、Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项。
ms.openlocfilehash: 841f6acc63497a6f0b8930c89534b5f8b04c0393
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358723"
---
# <a name="queuemarkerevent-function"></a><span data-ttu-id="ed5ad-103">QUEUEMARKEREVENT 函数</span><span class="sxs-lookup"><span data-stu-id="ed5ad-103">QUEUEMARKEREVENT Function</span></span>

<span data-ttu-id="ed5ad-104">使应用程序触发对加载项的标记事件、Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项。</span><span class="sxs-lookup"><span data-stu-id="ed5ad-104">Causes the application to fire a marker event to your add-on, Microsoft Visual Basic for Applications (VBA) code, or COM add-in.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ed5ad-105">语法</span><span class="sxs-lookup"><span data-stu-id="ed5ad-105">Syntax</span></span>

<span data-ttu-id="ed5ad-106">QUEUEMARKEREVENT (\* \* *event_string* \* \*)</span><span class="sxs-lookup"><span data-stu-id="ed5ad-106">QUEUEMARKEREVENT (\*\* *event_string* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ed5ad-107">参数</span><span class="sxs-lookup"><span data-stu-id="ed5ad-107">Parameters</span></span>

|<span data-ttu-id="ed5ad-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ed5ad-108">**Name**</span></span>|<span data-ttu-id="ed5ad-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ed5ad-109">**Required/Optional**</span></span>|<span data-ttu-id="ed5ad-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ed5ad-110">**Data Type**</span></span>|<span data-ttu-id="ed5ad-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed5ad-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ed5ad-112">_event_string_</span><span class="sxs-lookup"><span data-stu-id="ed5ad-112">_event_string_</span></span> <br/> |<span data-ttu-id="ed5ad-113">必需</span><span class="sxs-lookup"><span data-stu-id="ed5ad-113">Required</span></span>  <br/> |<span data-ttu-id="ed5ad-114">**String**</span><span class="sxs-lookup"><span data-stu-id="ed5ad-114">**String**</span></span> <br/> | <span data-ttu-id="ed5ad-115">要传递给事件处理程序的字符串。</span><span class="sxs-lookup"><span data-stu-id="ed5ad-115">The string to pass to your event handler.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ed5ad-116">注解</span><span class="sxs-lookup"><span data-stu-id="ed5ad-116">Remarks</span></span>

<span data-ttu-id="ed5ad-117">借助 QUEUEMARKEREVENT 函数，开发人员可以通知 ShapeSheet 单元格中的代码，然后传递特定于解决方案的信息。</span><span class="sxs-lookup"><span data-stu-id="ed5ad-117">The QUEUEMARKEREVENT function provides developers with a way to notify their code from a ShapeSheet cell, and pass solution-specific information.</span></span> <span data-ttu-id="ed5ad-118">计算包含包含 QUEUEMARKEREVENT 函数的公式的单元格时, 应用程序触发标记事件并将_event_string_传递给正在侦听**MarkerEvent**事件的所有事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ed5ad-118">When the cell containing the formula with the QUEUEMARKEREVENT function is evaluated, the application fires a marker event and passes  _event_string_ to all event handlers that are listening to the **MarkerEvent** event.</span></span> 
  
<span data-ttu-id="ed5ad-119">有关标记事件的详细信息, 请参阅 Microsoft Visio Automation Reference 中的**QueueMarkerEvent**方法和**MarkerEvent**事件主题。</span><span class="sxs-lookup"><span data-stu-id="ed5ad-119">For more information about marker events, see the **QueueMarkerEvent** method and **MarkerEvent** event topics in the Microsoft Visio Automation Reference.</span></span> 
  
## <a name="example"></a><span data-ttu-id="ed5ad-120">示例</span><span class="sxs-lookup"><span data-stu-id="ed5ad-120">Example</span></span>

<span data-ttu-id="ed5ad-121">QUEUEMARKEREVENT ("MyCustomNotification")</span><span class="sxs-lookup"><span data-stu-id="ed5ad-121">QUEUEMARKEREVENT ("MyCustomNotification")</span></span> 
  
<span data-ttu-id="ed5ad-122">导致应用程序触发标记事件，并将字符串“MyCustomNotification”传递给正在侦听 **MarkerEvent** 事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ed5ad-122">Causes the application to fire a marker event, and passes the string "MyCustomNotification" to event handlers that are listening to the **MarkerEvent** event.</span></span> 
  

