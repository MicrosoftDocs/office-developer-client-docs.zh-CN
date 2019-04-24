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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280139"
---
# <a name="imapicontrol--iunknown"></a><span data-ttu-id="1ee56-103">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1ee56-103">IMAPIControl : IUnknown</span></span>

  
  
<span data-ttu-id="1ee56-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ee56-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ee56-105">启用和禁用按钮控件, 并在客户端应用程序的用户单击启用的控件时执行任务。</span><span class="sxs-lookup"><span data-stu-id="1ee56-105">Enables and disables a button control, and performs tasks when a user of a client application clicks the enabled control.</span></span> <span data-ttu-id="1ee56-106">服务提供程序实现控制对象, 以在对话框 (如配置属性表) 上创建使用显示表定义的自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="1ee56-106">Service providers implement control objects to create custom buttons on dialog boxes, such as configuration property sheets, that are defined by using display tables.</span></span> 
  
<span data-ttu-id="1ee56-107">有关如何处理显示表和控件对象的详细信息, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="1ee56-107">For more information about how to work with display tables and control objects, see [Display Tables](display-tables.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1ee56-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1ee56-108">Header file:</span></span>  <br/> |<span data-ttu-id="1ee56-109">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1ee56-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="1ee56-110">公开者:</span><span class="sxs-lookup"><span data-stu-id="1ee56-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="1ee56-111">控件对象</span><span class="sxs-lookup"><span data-stu-id="1ee56-111">Control objects</span></span>  <br/> |
|<span data-ttu-id="1ee56-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="1ee56-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="1ee56-113">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="1ee56-113">Service providers</span></span>  <br/> |
|<span data-ttu-id="1ee56-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="1ee56-114">Called by:</span></span>  <br/> |<span data-ttu-id="1ee56-115">MAPI</span><span class="sxs-lookup"><span data-stu-id="1ee56-115">MAPI</span></span>  <br/> |
|<span data-ttu-id="1ee56-116">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="1ee56-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="1ee56-117">IID_IMAPIControl</span><span class="sxs-lookup"><span data-stu-id="1ee56-117">IID_IMAPIControl</span></span>  <br/> |
|<span data-ttu-id="1ee56-118">指针类型:</span><span class="sxs-lookup"><span data-stu-id="1ee56-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="1ee56-119">LPMAPICONTROL</span><span class="sxs-lookup"><span data-stu-id="1ee56-119">LPMAPICONTROL</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="1ee56-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="1ee56-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="1ee56-121">GetLastError</span><span class="sxs-lookup"><span data-stu-id="1ee56-121">GetLastError</span></span>](imapicontrol-getlasterror.md) <br/> |<span data-ttu-id="1ee56-122">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个按钮控件错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="1ee56-122">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous button control error.</span></span>  <br/> |
|[<span data-ttu-id="1ee56-123">Activate</span><span class="sxs-lookup"><span data-stu-id="1ee56-123">Activate</span></span>](imapicontrol-activate.md) <br/> |<span data-ttu-id="1ee56-124">在客户端应用程序用户单击 "按钮" 控件时执行一种任务, 如显示对话框或启动编程操作。</span><span class="sxs-lookup"><span data-stu-id="1ee56-124">Performs a task such as displaying a dialog box or starting a programmatic operation when a client application user clicks the button control.</span></span>  <br/> |
|[<span data-ttu-id="1ee56-125">GetState</span><span class="sxs-lookup"><span data-stu-id="1ee56-125">GetState</span></span>](imapicontrol-getstate.md) <br/> |<span data-ttu-id="1ee56-126">检索一个值, 该值指示按钮控件是否已启用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="1ee56-126">Retrieves a value that indicates whether the button control is enabled or disabled.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1ee56-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee56-127">See also</span></span>



[<span data-ttu-id="1ee56-128">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="1ee56-128">MAPI Interfaces</span></span>](mapi-interfaces.md)

