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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351137"
---
# <a name="imapiviewadvisesink--iunknown"></a><span data-ttu-id="0110a-103">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0110a-103">IMAPIViewAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="0110a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0110a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0110a-105">接收来自表单的通知。</span><span class="sxs-lookup"><span data-stu-id="0110a-105">Receives notifications from forms.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0110a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0110a-106">Header file:</span></span>  <br/> |<span data-ttu-id="0110a-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="0110a-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="0110a-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="0110a-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="0110a-109">查看建议接收器对象</span><span class="sxs-lookup"><span data-stu-id="0110a-109">View advise sink objects</span></span>  <br/> |
|<span data-ttu-id="0110a-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="0110a-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="0110a-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="0110a-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="0110a-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="0110a-112">Called by:</span></span>  <br/> |<span data-ttu-id="0110a-113">表单对象</span><span class="sxs-lookup"><span data-stu-id="0110a-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="0110a-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="0110a-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="0110a-115">IID_IMAPIViewAdviseSink</span><span class="sxs-lookup"><span data-stu-id="0110a-115">IID_IMAPIViewAdviseSink</span></span>  <br/> |
|<span data-ttu-id="0110a-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="0110a-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="0110a-117">LPMAPIVIEWADVISESINK</span><span class="sxs-lookup"><span data-stu-id="0110a-117">LPMAPIVIEWADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="0110a-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="0110a-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="0110a-119">OnShutdown</span><span class="sxs-lookup"><span data-stu-id="0110a-119">OnShutdown</span></span>](imapiviewadvisesink-onshutdown.md) <br/> |<span data-ttu-id="0110a-120">通知表单查看器表单正在关闭。</span><span class="sxs-lookup"><span data-stu-id="0110a-120">Notifies the form viewer that a form is being closed.</span></span>  <br/> |
|[<span data-ttu-id="0110a-121">OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="0110a-121">OnNewMessage</span></span>](imapiviewadvisesink-onnewmessage.md) <br/> |<span data-ttu-id="0110a-122">通知表单查看器新的或现有的邮件已加载到表单中。</span><span class="sxs-lookup"><span data-stu-id="0110a-122">Notifies the form viewer that either a new or an existing message has been loaded in a form.</span></span>  <br/> |
|[<span data-ttu-id="0110a-123">OnPrint</span><span class="sxs-lookup"><span data-stu-id="0110a-123">OnPrint</span></span>](imapiviewadvisesink-onprint.md) <br/> |<span data-ttu-id="0110a-124">将表单的打印状态通知给表单查看器。</span><span class="sxs-lookup"><span data-stu-id="0110a-124">Notifies the form viewer of the printing status of a form.</span></span>  <br/> |
|[<span data-ttu-id="0110a-125">OnSubmitted</span><span class="sxs-lookup"><span data-stu-id="0110a-125">OnSubmitted</span></span>](imapiviewadvisesink-onsubmitted.md) <br/> |<span data-ttu-id="0110a-126">通知表单查看器当前邮件已提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="0110a-126">Notifies the form viewer that the current message has been submitted to MAPI spooler.</span></span>  <br/> |
|[<span data-ttu-id="0110a-127">OnSaved</span><span class="sxs-lookup"><span data-stu-id="0110a-127">OnSaved</span></span>](imapiviewadvisesink-onsaved.md) <br/> |<span data-ttu-id="0110a-128">通知表单查看器表单中的当前邮件已保存。</span><span class="sxs-lookup"><span data-stu-id="0110a-128">Notifies the form viewer that the current message in a form has been saved.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0110a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0110a-129">See also</span></span>



[<span data-ttu-id="0110a-130">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="0110a-130">MAPI Interfaces</span></span>](mapi-interfaces.md)

