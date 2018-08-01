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
ms.openlocfilehash: f16585a96164835784bfa1af3752bd652daf76e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775729"
---
# <a name="imapiviewadvisesink--iunknown"></a><span data-ttu-id="c4f4e-103">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c4f4e-103">IMAPIViewAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="c4f4e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c4f4e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c4f4e-105">从窗体接收通知。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-105">Receives notifications from forms.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c4f4e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c4f4e-106">Header file:</span></span>  <br/> |<span data-ttu-id="c4f4e-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="c4f4e-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="c4f4e-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="c4f4e-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="c4f4e-109">查看建议接收器对象</span><span class="sxs-lookup"><span data-stu-id="c4f4e-109">View advise sink objects</span></span>  <br/> |
|<span data-ttu-id="c4f4e-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="c4f4e-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="c4f4e-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="c4f4e-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="c4f4e-112">调用：</span><span class="sxs-lookup"><span data-stu-id="c4f4e-112">Called by:</span></span>  <br/> |<span data-ttu-id="c4f4e-113">窗体对象</span><span class="sxs-lookup"><span data-stu-id="c4f4e-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="c4f4e-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="c4f4e-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c4f4e-115">IID_IMAPIViewAdviseSink</span><span class="sxs-lookup"><span data-stu-id="c4f4e-115">IID_IMAPIViewAdviseSink</span></span>  <br/> |
|<span data-ttu-id="c4f4e-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="c4f4e-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="c4f4e-117">LPMAPIVIEWADVISESINK</span><span class="sxs-lookup"><span data-stu-id="c4f4e-117">LPMAPIVIEWADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c4f4e-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="c4f4e-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="c4f4e-119">OnShutdown</span><span class="sxs-lookup"><span data-stu-id="c4f4e-119">OnShutdown</span></span>](imapiviewadvisesink-onshutdown.md) <br/> |<span data-ttu-id="c4f4e-120">通知表单查看器正在关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-120">Notifies the form viewer that a form is being closed.</span></span>  <br/> |
|[<span data-ttu-id="c4f4e-121">OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="c4f4e-121">OnNewMessage</span></span>](imapiviewadvisesink-onnewmessage.md) <br/> |<span data-ttu-id="c4f4e-122">通知表单查看器的新或现有邮件已加载的窗体。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-122">Notifies the form viewer that either a new or an existing message has been loaded in a form.</span></span>  <br/> |
|[<span data-ttu-id="c4f4e-123">OnPrint</span><span class="sxs-lookup"><span data-stu-id="c4f4e-123">OnPrint</span></span>](imapiviewadvisesink-onprint.md) <br/> |<span data-ttu-id="c4f4e-124">通知窗体的打印状态的表单查看器。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-124">Notifies the form viewer of the printing status of a form.</span></span>  <br/> |
|[<span data-ttu-id="c4f4e-125">OnSubmitted</span><span class="sxs-lookup"><span data-stu-id="c4f4e-125">OnSubmitted</span></span>](imapiviewadvisesink-onsubmitted.md) <br/> |<span data-ttu-id="c4f4e-126">通知表单查看器的当前消息，已提交到 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-126">Notifies the form viewer that the current message has been submitted to MAPI spooler.</span></span>  <br/> |
|[<span data-ttu-id="c4f4e-127">OnSaved</span><span class="sxs-lookup"><span data-stu-id="c4f4e-127">OnSaved</span></span>](imapiviewadvisesink-onsaved.md) <br/> |<span data-ttu-id="c4f4e-128">通知已保存窗体中的当前消息表单查看器。</span><span class="sxs-lookup"><span data-stu-id="c4f4e-128">Notifies the form viewer that the current message in a form has been saved.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c4f4e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f4e-129">See also</span></span>



[<span data-ttu-id="c4f4e-130">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="c4f4e-130">MAPI Interfaces</span></span>](mapi-interfaces.md)

