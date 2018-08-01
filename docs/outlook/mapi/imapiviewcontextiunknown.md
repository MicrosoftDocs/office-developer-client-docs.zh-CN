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
ms.openlocfilehash: a7d62253baaaae7955e722874a15d05ed16e566e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775750"
---
# <a name="imapiviewcontext--iunknown"></a><span data-ttu-id="61c4e-103">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="61c4e-103">IMAPIViewContext : IUnknown</span></span>

  
  
<span data-ttu-id="61c4e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="61c4e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="61c4e-105">管理客户端应用程序的表单查看器中的窗体。</span><span class="sxs-lookup"><span data-stu-id="61c4e-105">Manages a form in a client application's form viewer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="61c4e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="61c4e-106">Header file:</span></span>  <br/> |<span data-ttu-id="61c4e-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="61c4e-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="61c4e-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="61c4e-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="61c4e-109">视图上下文对象</span><span class="sxs-lookup"><span data-stu-id="61c4e-109">View context objects</span></span>  <br/> |
|<span data-ttu-id="61c4e-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="61c4e-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="61c4e-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="61c4e-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="61c4e-112">调用：</span><span class="sxs-lookup"><span data-stu-id="61c4e-112">Called by:</span></span>  <br/> |<span data-ttu-id="61c4e-113">窗体对象</span><span class="sxs-lookup"><span data-stu-id="61c4e-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="61c4e-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="61c4e-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="61c4e-115">IID_IMAPIViewContext</span><span class="sxs-lookup"><span data-stu-id="61c4e-115">IID_IMAPIViewContext</span></span>  <br/> |
|<span data-ttu-id="61c4e-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="61c4e-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="61c4e-117">LPMAPIVIEWCONTEXT</span><span class="sxs-lookup"><span data-stu-id="61c4e-117">LPMAPIVIEWCONTEXT</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="61c4e-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="61c4e-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="61c4e-119">SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="61c4e-119">SetAdviseSink</span></span>](imapiviewcontext-setadvisesink.md) <br/> |<span data-ttu-id="61c4e-120">管理窗体的注册中查看者接收有关更改的通知。</span><span class="sxs-lookup"><span data-stu-id="61c4e-120">Manages a form's registration to receive notifications about changes in the viewer.</span></span>  <br/> |
|[<span data-ttu-id="61c4e-121">ActivateNext</span><span class="sxs-lookup"><span data-stu-id="61c4e-121">ActivateNext</span></span>](imapiviewcontext-activatenext.md) <br/> |<span data-ttu-id="61c4e-122">激活表单查看器中的下一页或上一页消息。</span><span class="sxs-lookup"><span data-stu-id="61c4e-122">Activates the next or previous message in the form viewer.</span></span>  <br/> |
|[<span data-ttu-id="61c4e-123">GetPrintSetup</span><span class="sxs-lookup"><span data-stu-id="61c4e-123">GetPrintSetup</span></span>](imapiviewcontext-getprintsetup.md) <br/> |<span data-ttu-id="61c4e-124">检索当前打印的信息。</span><span class="sxs-lookup"><span data-stu-id="61c4e-124">Retrieves current printing information.</span></span>  <br/> |
|[<span data-ttu-id="61c4e-125">GetSaveStream</span><span class="sxs-lookup"><span data-stu-id="61c4e-125">GetSaveStream</span></span>](imapiviewcontext-getsavestream.md) <br/> |<span data-ttu-id="61c4e-126">检索用于保存当前消息流。</span><span class="sxs-lookup"><span data-stu-id="61c4e-126">Retrieves a stream to be used for saving the current message.</span></span>  <br/> |
|[<span data-ttu-id="61c4e-127">GetViewStatus</span><span class="sxs-lookup"><span data-stu-id="61c4e-127">GetViewStatus</span></span>](imapiviewcontext-getviewstatus.md) <br/> |<span data-ttu-id="61c4e-128">检索当前的查看器状态。</span><span class="sxs-lookup"><span data-stu-id="61c4e-128">Retrieves the current viewer status.</span></span>  <br/> |
|[<span data-ttu-id="61c4e-129">时出错</span><span class="sxs-lookup"><span data-stu-id="61c4e-129">GetLastError</span></span>](imapiviewcontext-getlasterror.md) <br/> |<span data-ttu-id="61c4e-130">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面视图上下文对象中出现的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="61c4e-130">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring in the view context object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="61c4e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61c4e-131">See also</span></span>



[<span data-ttu-id="61c4e-132">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="61c4e-132">MAPI Interfaces</span></span>](mapi-interfaces.md)

