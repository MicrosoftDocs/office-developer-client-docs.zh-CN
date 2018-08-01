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
ms.openlocfilehash: 395e44c2ea54816fab9f29dbedfe5e165e98c7b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775322"
---
# <a name="imapicontrol--iunknown"></a><span data-ttu-id="27056-103">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="27056-103">IMAPIControl : IUnknown</span></span>

  
  
<span data-ttu-id="27056-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="27056-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="27056-105">启用和禁用按钮控件，并执行任务时客户端应用程序的用户单击已启用的控件。</span><span class="sxs-lookup"><span data-stu-id="27056-105">Enables and disables a button control, and performs tasks when a user of a client application clicks the enabled control.</span></span> <span data-ttu-id="27056-106">服务提供商实现控件对象上对话框，例如配置的属性页，通过使用显示表定义创建自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="27056-106">Service providers implement control objects to create custom buttons on dialog boxes, such as configuration property sheets, that are defined by using display tables.</span></span> 
  
<span data-ttu-id="27056-107">有关如何使用显示表格和控制对象的详细信息，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="27056-107">For more information about how to work with display tables and control objects, see [Display Tables](display-tables.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="27056-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="27056-108">Header file:</span></span>  <br/> |<span data-ttu-id="27056-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="27056-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="27056-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="27056-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="27056-111">控件对象</span><span class="sxs-lookup"><span data-stu-id="27056-111">Control objects</span></span>  <br/> |
|<span data-ttu-id="27056-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="27056-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="27056-113">服务提供商</span><span class="sxs-lookup"><span data-stu-id="27056-113">Service providers</span></span>  <br/> |
|<span data-ttu-id="27056-114">调用：</span><span class="sxs-lookup"><span data-stu-id="27056-114">Called by:</span></span>  <br/> |<span data-ttu-id="27056-115">MAPI</span><span class="sxs-lookup"><span data-stu-id="27056-115">MAPI</span></span>  <br/> |
|<span data-ttu-id="27056-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="27056-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="27056-117">IID_IMAPIControl</span><span class="sxs-lookup"><span data-stu-id="27056-117">IID_IMAPIControl</span></span>  <br/> |
|<span data-ttu-id="27056-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="27056-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="27056-119">LPMAPICONTROL</span><span class="sxs-lookup"><span data-stu-id="27056-119">LPMAPICONTROL</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="27056-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="27056-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="27056-121">时出错</span><span class="sxs-lookup"><span data-stu-id="27056-121">GetLastError</span></span>](imapicontrol-getlasterror.md) <br/> |<span data-ttu-id="27056-122">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前一个按钮控件错误的信息。</span><span class="sxs-lookup"><span data-stu-id="27056-122">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous button control error.</span></span>  <br/> |
|[<span data-ttu-id="27056-123">Activate</span><span class="sxs-lookup"><span data-stu-id="27056-123">Activate</span></span>](imapicontrol-activate.md) <br/> |<span data-ttu-id="27056-124">执行显示一个对话框，或在客户端应用程序用户单击按钮控件时启动编程操作等任务。</span><span class="sxs-lookup"><span data-stu-id="27056-124">Performs a task such as displaying a dialog box or starting a programmatic operation when a client application user clicks the button control.</span></span>  <br/> |
|[<span data-ttu-id="27056-125">GetState</span><span class="sxs-lookup"><span data-stu-id="27056-125">GetState</span></span>](imapicontrol-getstate.md) <br/> |<span data-ttu-id="27056-126">检索值，该值指示是否启用或禁用按钮控件。</span><span class="sxs-lookup"><span data-stu-id="27056-126">Retrieves a value that indicates whether the button control is enabled or disabled.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="27056-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27056-127">See also</span></span>



[<span data-ttu-id="27056-128">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="27056-128">MAPI Interfaces</span></span>](mapi-interfaces.md)

