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
# <a name="imapiviewcontext--iunknown"></a><span data-ttu-id="0d5ce-103">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0d5ce-103">IMAPIViewContext : IUnknown</span></span>

  
  
<span data-ttu-id="0d5ce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d5ce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d5ce-105">管理客户端应用程序的表单查看器中的表单。</span><span class="sxs-lookup"><span data-stu-id="0d5ce-105">Manages a form in a client application's form viewer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0d5ce-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0d5ce-106">Header file:</span></span>  <br/> |<span data-ttu-id="0d5ce-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="0d5ce-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="0d5ce-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="0d5ce-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="0d5ce-109">View context 对象</span><span class="sxs-lookup"><span data-stu-id="0d5ce-109">View context objects</span></span>  <br/> |
|<span data-ttu-id="0d5ce-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="0d5ce-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="0d5ce-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="0d5ce-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="0d5ce-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="0d5ce-112">Called by:</span></span>  <br/> |<span data-ttu-id="0d5ce-113">表单对象</span><span class="sxs-lookup"><span data-stu-id="0d5ce-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="0d5ce-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="0d5ce-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="0d5ce-115">IID_IMAPIViewContext</span><span class="sxs-lookup"><span data-stu-id="0d5ce-115">IID_IMAPIViewContext</span></span>  <br/> |
|<span data-ttu-id="0d5ce-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="0d5ce-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="0d5ce-117">LPMAPIVIEWCONTEXT</span><span class="sxs-lookup"><span data-stu-id="0d5ce-117">LPMAPIVIEWCONTEXT</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="0d5ce-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="0d5ce-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="0d5ce-119">SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="0d5ce-119">SetAdviseSink</span></span>](imapiviewcontext-setadvisesink.md) <br/> |<span data-ttu-id="0d5ce-120">管理表单注册, 以便在查看器中接收有关更改的通知。</span><span class="sxs-lookup"><span data-stu-id="0d5ce-120">Manages a form's registration to receive notifications about changes in the viewer.</span></span>  <br/> |
|[<span data-ttu-id="0d5ce-121">ActivateNext</span><span class="sxs-lookup"><span data-stu-id="0d5ce-121">ActivateNext</span></span>](imapiviewcontext-activatenext.md) <br/> |<span data-ttu-id="0d5ce-122">激活窗体查看器中的下一条或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0d5ce-122">Activates the next or previous message in the form viewer.</span></span>  <br/> |
|[<span data-ttu-id="0d5ce-123">GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="0d5ce-123">GetPrintSetup</span></span>](imapiviewcontext-getprintsetup.md) <br/> |<span data-ttu-id="0d5ce-124">检索当前打印信息。</span><span class="sxs-lookup"><span data-stu-id="0d5ce-124">Retrieves current printing information.</span></span>  <br/> |
|[<span data-ttu-id="0d5ce-125">GetSaveStream</span><span class="sxs-lookup"><span data-stu-id="0d5ce-125">GetSaveStream</span></span>](imapiviewcontext-getsavestream.md) <br/> |<span data-ttu-id="0d5ce-126">检索用于保存当前邮件的流。</span><span class="sxs-lookup"><span data-stu-id="0d5ce-126">Retrieves a stream to be used for saving the current message.</span></span>  <br/> |
|[<span data-ttu-id="0d5ce-127">GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="0d5ce-127">GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md) <br/> |<span data-ttu-id="0d5ce-128">检索当前查看器状态。</span><span class="sxs-lookup"><span data-stu-id="0d5ce-128">Retrieves the current viewer status.</span></span>  <br/> |
|[<span data-ttu-id="0d5ce-129">GetLastError</span><span class="sxs-lookup"><span data-stu-id="0d5ce-129">GetLastError</span></span>](imapiviewcontext-getlasterror.md) <br/> |<span data-ttu-id="0d5ce-130">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关 view context 对象中发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="0d5ce-130">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring in the view context object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0d5ce-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d5ce-131">See also</span></span>



[<span data-ttu-id="0d5ce-132">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="0d5ce-132">MAPI Interfaces</span></span>](mapi-interfaces.md)

