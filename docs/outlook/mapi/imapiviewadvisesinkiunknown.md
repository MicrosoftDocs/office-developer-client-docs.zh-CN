---
title: IMAPIViewAdviseSink IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink
api_type:
- COM
ms.assetid: 1231391d-803a-4b41-b252-4d986f99361a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70f61fe33baa7870a58c4cbc7d75e0df119b5b1a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429416"
---
# <a name="imapiviewadvisesink--iunknown"></a><span data-ttu-id="03657-103">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="03657-103">IMAPIViewAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="03657-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="03657-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="03657-105">接收来自表单的通知。</span><span class="sxs-lookup"><span data-stu-id="03657-105">Receives notifications from forms.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="03657-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="03657-106">Header file:</span></span>  <br/> |<span data-ttu-id="03657-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="03657-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="03657-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="03657-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="03657-109">查看通知接收对象</span><span class="sxs-lookup"><span data-stu-id="03657-109">View advise sink objects</span></span>  <br/> |
|<span data-ttu-id="03657-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="03657-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="03657-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="03657-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="03657-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="03657-112">Called by:</span></span>  <br/> |<span data-ttu-id="03657-113">表单对象</span><span class="sxs-lookup"><span data-stu-id="03657-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="03657-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="03657-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="03657-115">IID_IMAPIViewAdviseSink</span><span class="sxs-lookup"><span data-stu-id="03657-115">IID_IMAPIViewAdviseSink</span></span>  <br/> |
|<span data-ttu-id="03657-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="03657-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="03657-117">LPMAPIVIEWADVISESINK</span><span class="sxs-lookup"><span data-stu-id="03657-117">LPMAPIVIEWADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="03657-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="03657-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="03657-119">OnShutdown</span><span class="sxs-lookup"><span data-stu-id="03657-119">OnShutdown</span></span>](imapiviewadvisesink-onshutdown.md) <br/> |<span data-ttu-id="03657-120">通知表单查看器正在关闭表单。</span><span class="sxs-lookup"><span data-stu-id="03657-120">Notifies the form viewer that a form is being closed.</span></span>  <br/> |
|[<span data-ttu-id="03657-121">OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="03657-121">OnNewMessage</span></span>](imapiviewadvisesink-onnewmessage.md) <br/> |<span data-ttu-id="03657-122">通知表单查看器已在表单中加载了新邮件或现有邮件。</span><span class="sxs-lookup"><span data-stu-id="03657-122">Notifies the form viewer that either a new or an existing message has been loaded in a form.</span></span>  <br/> |
|[<span data-ttu-id="03657-123">OnPrint</span><span class="sxs-lookup"><span data-stu-id="03657-123">OnPrint</span></span>](imapiviewadvisesink-onprint.md) <br/> |<span data-ttu-id="03657-124">通知窗体查看者窗体的打印状态。</span><span class="sxs-lookup"><span data-stu-id="03657-124">Notifies the form viewer of the printing status of a form.</span></span>  <br/> |
|[<span data-ttu-id="03657-125">OnSubmitted</span><span class="sxs-lookup"><span data-stu-id="03657-125">OnSubmitted</span></span>](imapiviewadvisesink-onsubmitted.md) <br/> |<span data-ttu-id="03657-126">通知表单查看器当前邮件已提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="03657-126">Notifies the form viewer that the current message has been submitted to MAPI spooler.</span></span>  <br/> |
|[<span data-ttu-id="03657-127">OnSaved</span><span class="sxs-lookup"><span data-stu-id="03657-127">OnSaved</span></span>](imapiviewadvisesink-onsaved.md) <br/> |<span data-ttu-id="03657-128">通知窗体查看器窗体中的当前邮件已保存。</span><span class="sxs-lookup"><span data-stu-id="03657-128">Notifies the form viewer that the current message in a form has been saved.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="03657-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03657-129">See also</span></span>



[<span data-ttu-id="03657-130">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="03657-130">MAPI Interfaces</span></span>](mapi-interfaces.md)

