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
ms.openlocfilehash: ae2729ec5620b6b408a5c999d4b6ede7143bed2f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584561"
---
# <a name="imapiviewcontext--iunknown"></a><span data-ttu-id="643a1-103">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="643a1-103">IMAPIViewContext : IUnknown</span></span>

  
  
<span data-ttu-id="643a1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="643a1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="643a1-105">管理客户端应用程序的表单查看器中的窗体。</span><span class="sxs-lookup"><span data-stu-id="643a1-105">Manages a form in a client application's form viewer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="643a1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="643a1-106">Header file:</span></span>  <br/> |<span data-ttu-id="643a1-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="643a1-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="643a1-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="643a1-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="643a1-109">视图上下文对象</span><span class="sxs-lookup"><span data-stu-id="643a1-109">View context objects</span></span>  <br/> |
|<span data-ttu-id="643a1-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="643a1-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="643a1-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="643a1-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="643a1-112">调用：</span><span class="sxs-lookup"><span data-stu-id="643a1-112">Called by:</span></span>  <br/> |<span data-ttu-id="643a1-113">窗体对象</span><span class="sxs-lookup"><span data-stu-id="643a1-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="643a1-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="643a1-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="643a1-115">IID_IMAPIViewContext</span><span class="sxs-lookup"><span data-stu-id="643a1-115">IID_IMAPIViewContext</span></span>  <br/> |
|<span data-ttu-id="643a1-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="643a1-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="643a1-117">LPMAPIVIEWCONTEXT</span><span class="sxs-lookup"><span data-stu-id="643a1-117">LPMAPIVIEWCONTEXT</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="643a1-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="643a1-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="643a1-119">SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="643a1-119">SetAdviseSink</span></span>](imapiviewcontext-setadvisesink.md) <br/> |<span data-ttu-id="643a1-120">管理窗体的注册中查看者接收有关更改的通知。</span><span class="sxs-lookup"><span data-stu-id="643a1-120">Manages a form's registration to receive notifications about changes in the viewer.</span></span>  <br/> |
|[<span data-ttu-id="643a1-121">ActivateNext</span><span class="sxs-lookup"><span data-stu-id="643a1-121">ActivateNext</span></span>](imapiviewcontext-activatenext.md) <br/> |<span data-ttu-id="643a1-122">激活表单查看器中的下一页或上一页消息。</span><span class="sxs-lookup"><span data-stu-id="643a1-122">Activates the next or previous message in the form viewer.</span></span>  <br/> |
|[<span data-ttu-id="643a1-123">GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="643a1-123">GetPrintSetup</span></span>](imapiviewcontext-getprintsetup.md) <br/> |<span data-ttu-id="643a1-124">检索当前打印的信息。</span><span class="sxs-lookup"><span data-stu-id="643a1-124">Retrieves current printing information.</span></span>  <br/> |
|[<span data-ttu-id="643a1-125">GetSaveStream</span><span class="sxs-lookup"><span data-stu-id="643a1-125">GetSaveStream</span></span>](imapiviewcontext-getsavestream.md) <br/> |<span data-ttu-id="643a1-126">检索用于保存当前消息流。</span><span class="sxs-lookup"><span data-stu-id="643a1-126">Retrieves a stream to be used for saving the current message.</span></span>  <br/> |
|[<span data-ttu-id="643a1-127">GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="643a1-127">GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md) <br/> |<span data-ttu-id="643a1-128">检索当前的查看器状态。</span><span class="sxs-lookup"><span data-stu-id="643a1-128">Retrieves the current viewer status.</span></span>  <br/> |
|[<span data-ttu-id="643a1-129">时出错</span><span class="sxs-lookup"><span data-stu-id="643a1-129">GetLastError</span></span>](imapiviewcontext-getlasterror.md) <br/> |<span data-ttu-id="643a1-130">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面视图上下文对象中出现的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="643a1-130">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring in the view context object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="643a1-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="643a1-131">See also</span></span>



[<span data-ttu-id="643a1-132">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="643a1-132">MAPI Interfaces</span></span>](mapi-interfaces.md)

