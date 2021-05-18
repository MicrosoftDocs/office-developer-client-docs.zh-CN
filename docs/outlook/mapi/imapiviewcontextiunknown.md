---
title: IMAPIViewContext IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext
api_type:
- COM
ms.assetid: d566ff39-92c1-4a14-85e5-1c406825f805
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: db0c375218755c3a28475e2ebce2d097fb789f75
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406029"
---
# <a name="imapiviewcontext--iunknown"></a><span data-ttu-id="67f6e-103">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="67f6e-103">IMAPIViewContext : IUnknown</span></span>

  
  
<span data-ttu-id="67f6e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67f6e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67f6e-105">在客户端应用程序的表单查看器中管理表单。</span><span class="sxs-lookup"><span data-stu-id="67f6e-105">Manages a form in a client application's form viewer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="67f6e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="67f6e-106">Header file:</span></span>  <br/> |<span data-ttu-id="67f6e-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="67f6e-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="67f6e-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="67f6e-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="67f6e-109">查看上下文对象</span><span class="sxs-lookup"><span data-stu-id="67f6e-109">View context objects</span></span>  <br/> |
|<span data-ttu-id="67f6e-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="67f6e-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="67f6e-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="67f6e-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="67f6e-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="67f6e-112">Called by:</span></span>  <br/> |<span data-ttu-id="67f6e-113">表单对象</span><span class="sxs-lookup"><span data-stu-id="67f6e-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="67f6e-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="67f6e-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="67f6e-115">IID_IMAPIViewContext</span><span class="sxs-lookup"><span data-stu-id="67f6e-115">IID_IMAPIViewContext</span></span>  <br/> |
|<span data-ttu-id="67f6e-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="67f6e-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="67f6e-117">LPMAPIVIEWCONTEXT</span><span class="sxs-lookup"><span data-stu-id="67f6e-117">LPMAPIVIEWCONTEXT</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="67f6e-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="67f6e-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="67f6e-119">SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="67f6e-119">SetAdviseSink</span></span>](imapiviewcontext-setadvisesink.md) <br/> |<span data-ttu-id="67f6e-120">管理表单的注册以接收有关查看器中更改的通知。</span><span class="sxs-lookup"><span data-stu-id="67f6e-120">Manages a form's registration to receive notifications about changes in the viewer.</span></span>  <br/> |
|[<span data-ttu-id="67f6e-121">ActivateNext</span><span class="sxs-lookup"><span data-stu-id="67f6e-121">ActivateNext</span></span>](imapiviewcontext-activatenext.md) <br/> |<span data-ttu-id="67f6e-122">激活窗体查看器中的下一封邮件或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="67f6e-122">Activates the next or previous message in the form viewer.</span></span>  <br/> |
|[<span data-ttu-id="67f6e-123">GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="67f6e-123">GetPrintSetup</span></span>](imapiviewcontext-getprintsetup.md) <br/> |<span data-ttu-id="67f6e-124">检索当前打印信息。</span><span class="sxs-lookup"><span data-stu-id="67f6e-124">Retrieves current printing information.</span></span>  <br/> |
|[<span data-ttu-id="67f6e-125">GetSaveStream</span><span class="sxs-lookup"><span data-stu-id="67f6e-125">GetSaveStream</span></span>](imapiviewcontext-getsavestream.md) <br/> |<span data-ttu-id="67f6e-126">检索用于保存当前消息的流。</span><span class="sxs-lookup"><span data-stu-id="67f6e-126">Retrieves a stream to be used for saving the current message.</span></span>  <br/> |
|[<span data-ttu-id="67f6e-127">GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="67f6e-127">GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md) <br/> |<span data-ttu-id="67f6e-128">检索当前查看器状态。</span><span class="sxs-lookup"><span data-stu-id="67f6e-128">Retrieves the current viewer status.</span></span>  <br/> |
|[<span data-ttu-id="67f6e-129">GetLastError</span><span class="sxs-lookup"><span data-stu-id="67f6e-129">GetLastError</span></span>](imapiviewcontext-getlasterror.md) <br/> |<span data-ttu-id="67f6e-130">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关视图上下文对象中发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="67f6e-130">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring in the view context object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="67f6e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67f6e-131">See also</span></span>



[<span data-ttu-id="67f6e-132">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="67f6e-132">MAPI Interfaces</span></span>](mapi-interfaces.md)

