---
title: IMAPIControl IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl
api_type:
- COM
ms.assetid: 5a647e15-ba22-4a7c-b235-75cd76b77c1a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8dce1415ef8d18f4b786e92324c888f9a0845162
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414037"
---
# <a name="imapicontrol--iunknown"></a><span data-ttu-id="69306-103">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="69306-103">IMAPIControl : IUnknown</span></span>

  
  
<span data-ttu-id="69306-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="69306-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="69306-105">启用和禁用按钮控件，当客户端应用程序的用户单击启用的控件时执行任务。</span><span class="sxs-lookup"><span data-stu-id="69306-105">Enables and disables a button control, and performs tasks when a user of a client application clicks the enabled control.</span></span> <span data-ttu-id="69306-106">服务提供程序实现控件对象，以在使用显示表定义的对话框（如配置属性表）上创建自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="69306-106">Service providers implement control objects to create custom buttons on dialog boxes, such as configuration property sheets, that are defined by using display tables.</span></span> 
  
<span data-ttu-id="69306-107">有关如何使用显示表和控件对象的信息，请参阅 [显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="69306-107">For more information about how to work with display tables and control objects, see [Display Tables](display-tables.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="69306-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="69306-108">Header file:</span></span>  <br/> |<span data-ttu-id="69306-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="69306-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="69306-110">公开者：</span><span class="sxs-lookup"><span data-stu-id="69306-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="69306-111">Control 对象</span><span class="sxs-lookup"><span data-stu-id="69306-111">Control objects</span></span>  <br/> |
|<span data-ttu-id="69306-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="69306-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="69306-113">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="69306-113">Service providers</span></span>  <br/> |
|<span data-ttu-id="69306-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="69306-114">Called by:</span></span>  <br/> |<span data-ttu-id="69306-115">MAPI</span><span class="sxs-lookup"><span data-stu-id="69306-115">MAPI</span></span>  <br/> |
|<span data-ttu-id="69306-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="69306-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="69306-117">IID_IMAPIControl</span><span class="sxs-lookup"><span data-stu-id="69306-117">IID_IMAPIControl</span></span>  <br/> |
|<span data-ttu-id="69306-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="69306-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="69306-119">LPMAPICONTROL</span><span class="sxs-lookup"><span data-stu-id="69306-119">LPMAPICONTROL</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="69306-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="69306-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="69306-121">GetLastError</span><span class="sxs-lookup"><span data-stu-id="69306-121">GetLastError</span></span>](imapicontrol-getlasterror.md) <br/> |<span data-ttu-id="69306-122">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个按钮控件错误的信息。</span><span class="sxs-lookup"><span data-stu-id="69306-122">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous button control error.</span></span>  <br/> |
|[<span data-ttu-id="69306-123">Activate</span><span class="sxs-lookup"><span data-stu-id="69306-123">Activate</span></span>](imapicontrol-activate.md) <br/> |<span data-ttu-id="69306-124">执行一个任务，如在客户端应用程序用户单击按钮控件时显示对话框或启动编程操作。</span><span class="sxs-lookup"><span data-stu-id="69306-124">Performs a task such as displaying a dialog box or starting a programmatic operation when a client application user clicks the button control.</span></span>  <br/> |
|[<span data-ttu-id="69306-125">GetState</span><span class="sxs-lookup"><span data-stu-id="69306-125">GetState</span></span>](imapicontrol-getstate.md) <br/> |<span data-ttu-id="69306-126">检索一个值，该值指示按钮控件是启用还是禁用。</span><span class="sxs-lookup"><span data-stu-id="69306-126">Retrieves a value that indicates whether the button control is enabled or disabled.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="69306-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69306-127">See also</span></span>



[<span data-ttu-id="69306-128">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="69306-128">MAPI Interfaces</span></span>](mapi-interfaces.md)

