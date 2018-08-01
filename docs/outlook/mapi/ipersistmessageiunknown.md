---
title: IPersistMessage IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage
api_type:
- COM
ms.assetid: 40ec6dd4-2206-4e59-aafe-53aaf693f973
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 62fb2b069a50408713eea741cf837c421a749fcd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776010"
---
# <a name="ipersistmessage--iunknown"></a><span data-ttu-id="4a484-103">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4a484-103">IPersistMessage : IUnknown</span></span>

  
  
<span data-ttu-id="4a484-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4a484-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4a484-105">启用表单查看器处理存储窗体和各种状态间转换。</span><span class="sxs-lookup"><span data-stu-id="4a484-105">Enables form viewers to handle the storage of a form and to transition between the various states.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4a484-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4a484-106">Header file:</span></span>  <br/> |<span data-ttu-id="4a484-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="4a484-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="4a484-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="4a484-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="4a484-109">保留消息对象</span><span class="sxs-lookup"><span data-stu-id="4a484-109">Persist message objects</span></span>  <br/> |
|<span data-ttu-id="4a484-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="4a484-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="4a484-111">窗体对象</span><span class="sxs-lookup"><span data-stu-id="4a484-111">Form objects</span></span>  <br/> |
|<span data-ttu-id="4a484-112">调用：</span><span class="sxs-lookup"><span data-stu-id="4a484-112">Called by:</span></span>  <br/> |<span data-ttu-id="4a484-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="4a484-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="4a484-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="4a484-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4a484-115">IID_IPersistMessage</span><span class="sxs-lookup"><span data-stu-id="4a484-115">IID_IPersistMessage</span></span>  <br/> |
|<span data-ttu-id="4a484-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="4a484-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="4a484-117">LPPERSISTMESSAGE</span><span class="sxs-lookup"><span data-stu-id="4a484-117">LPPERSISTMESSAGE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4a484-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="4a484-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4a484-119">时出错</span><span class="sxs-lookup"><span data-stu-id="4a484-119">GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="4a484-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关表单对象中前面的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4a484-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error in the form object.</span></span>  <br/> |
|[<span data-ttu-id="4a484-121">GetClassID</span><span class="sxs-lookup"><span data-stu-id="4a484-121">GetClassID</span></span>](ipersistmessage-getclassid.md) <br/> |<span data-ttu-id="4a484-122">返回表示可以管理窗体的窗体服务器的标识符。</span><span class="sxs-lookup"><span data-stu-id="4a484-122">Returns an identifier that represents the form server that can manage the form.</span></span>  <br/> |
|[<span data-ttu-id="4a484-123">IsDirty</span><span class="sxs-lookup"><span data-stu-id="4a484-123">IsDirty</span></span>](ipersistmessage-isdirty.md) <br/> |<span data-ttu-id="4a484-124">检查自上次保存以来所做的更改的表单。</span><span class="sxs-lookup"><span data-stu-id="4a484-124">Checks the form for changes that were made since the last save.</span></span>  <br/> |
|[<span data-ttu-id="4a484-125">丢失</span><span class="sxs-lookup"><span data-stu-id="4a484-125">InitNew</span></span>](ipersistmessage-initnew.md) <br/> |<span data-ttu-id="4a484-126">初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="4a484-126">Initializes a new message.</span></span>  <br/> |
|[<span data-ttu-id="4a484-127">加载</span><span class="sxs-lookup"><span data-stu-id="4a484-127">Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="4a484-128">加载指定的消息的窗体。</span><span class="sxs-lookup"><span data-stu-id="4a484-128">Loads the form for a specified message.</span></span>  <br/> |
|[<span data-ttu-id="4a484-129">Save</span><span class="sxs-lookup"><span data-stu-id="4a484-129">Save</span></span>](ipersistmessage-save.md) <br/> |<span data-ttu-id="4a484-130">将修订后的表单保存回其已加载或创建的邮件。</span><span class="sxs-lookup"><span data-stu-id="4a484-130">Saves a revised form back to the message from which it was loaded or created.</span></span>  <br/> |
|[<span data-ttu-id="4a484-131">SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="4a484-131">SaveCompleted</span></span>](ipersistmessage-savecompleted.md) <br/> |<span data-ttu-id="4a484-132">通知窗体的保存操作已完成。</span><span class="sxs-lookup"><span data-stu-id="4a484-132">Notifies the form that a save operation has been completed.</span></span>  <br/> |
|[<span data-ttu-id="4a484-133">HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="4a484-133">HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md) <br/> |<span data-ttu-id="4a484-134">使窗体释放其当前邮件。</span><span class="sxs-lookup"><span data-stu-id="4a484-134">Causes the form to release its current message.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4a484-135">说明</span><span class="sxs-lookup"><span data-stu-id="4a484-135">Remarks</span></span>

<span data-ttu-id="4a484-136">实现**IPersistMessage**接口所需的所有表单。</span><span class="sxs-lookup"><span data-stu-id="4a484-136">All forms are required to implement the **IPersistMessage** interface.</span></span> 
  
 <span data-ttu-id="4a484-137">**IPersistMessage**同样适用于 OLE [IPersistStorage](http://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="4a484-137">**IPersistMessage** works similarly to the OLE [IPersistStorage](http://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) interface.</span></span> <span data-ttu-id="4a484-138">有关详细信息，请参阅**IPersistStorage**方法。</span><span class="sxs-lookup"><span data-stu-id="4a484-138">For more information, see the **IPersistStorage** methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4a484-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a484-139">See also</span></span>



[<span data-ttu-id="4a484-140">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="4a484-140">MAPI Interfaces</span></span>](mapi-interfaces.md)

