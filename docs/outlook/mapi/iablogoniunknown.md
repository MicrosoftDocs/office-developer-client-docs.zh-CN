---
title: IABLogon IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon
api_type:
- COM
ms.assetid: fe340182-f41e-42e7-b8e8-cc005b1e9a5f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 784430f1286c9a017337a0fae4b269757a56a3e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775237"
---
# <a name="iablogon--iunknown"></a><span data-ttu-id="2ad22-103">IABLogon: IUnknown</span><span class="sxs-lookup"><span data-stu-id="2ad22-103">IABLogon : IUnknown</span></span>

  
  
<span data-ttu-id="2ad22-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2ad22-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2ad22-105">访问通讯簿提供程序中的资源。</span><span class="sxs-lookup"><span data-stu-id="2ad22-105">Accesses resources in an address book provider.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ad22-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2ad22-106">Header file:</span></span>  <br/> |<span data-ttu-id="2ad22-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="2ad22-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="2ad22-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="2ad22-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="2ad22-109">通讯簿登录对象</span><span class="sxs-lookup"><span data-stu-id="2ad22-109">Address book logon objects</span></span>  <br/> |
|<span data-ttu-id="2ad22-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2ad22-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="2ad22-111">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="2ad22-111">Address book providers</span></span>  <br/> |
|<span data-ttu-id="2ad22-112">调用：</span><span class="sxs-lookup"><span data-stu-id="2ad22-112">Called by:</span></span>  <br/> |<span data-ttu-id="2ad22-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="2ad22-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="2ad22-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="2ad22-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="2ad22-115">IID_IABLogon</span><span class="sxs-lookup"><span data-stu-id="2ad22-115">IID_IABLogon</span></span>  <br/> |
|<span data-ttu-id="2ad22-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="2ad22-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="2ad22-117">LPABLOGON</span><span class="sxs-lookup"><span data-stu-id="2ad22-117">LPABLOGON</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="2ad22-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="2ad22-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="2ad22-119">时出错</span><span class="sxs-lookup"><span data-stu-id="2ad22-119">GetLastError</span></span>](iablogon-getlasterror.md) <br/> |<span data-ttu-id="2ad22-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关以前的通讯簿提供程序错误的信息。</span><span class="sxs-lookup"><span data-stu-id="2ad22-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous address book provider error.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-121">注销</span><span class="sxs-lookup"><span data-stu-id="2ad22-121">Logoff</span></span>](iablogon-logoff.md) <br/> |<span data-ttu-id="2ad22-122">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="2ad22-122">Initiates the logoff process.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-123">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="2ad22-123">OpenEntry</span></span>](iablogon-openentry.md) <br/> |<span data-ttu-id="2ad22-124">打开的容器，消息用户或通讯组列表，并返回指向接口实现，以提供更多访问的指针。</span><span class="sxs-lookup"><span data-stu-id="2ad22-124">Opens a container, messaging user, or distribution list, and returns a pointer to an interface implementation to provide further access.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-125">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="2ad22-125">CompareEntryIDs</span></span>](iablogon-compareentryids.md) <br/> |<span data-ttu-id="2ad22-126">比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="2ad22-126">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-127">建议</span><span class="sxs-lookup"><span data-stu-id="2ad22-127">Advise</span></span>](iablogon-advise.md) <br/> |<span data-ttu-id="2ad22-128">注册呼叫者接收影响的容器，消息用户或通讯组列表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="2ad22-128">Registers the caller to receive notification of specified events that affect a container, messaging user, or distribution list.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-129">取消通知</span><span class="sxs-lookup"><span data-stu-id="2ad22-129">Unadvise</span></span>](iablogon-unadvise.md) <br/> |<span data-ttu-id="2ad22-130">取消以前已设置为**Advise**方法的调用的通知。</span><span class="sxs-lookup"><span data-stu-id="2ad22-130">Cancels notifications that were previously set up with a call to the **Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-131">OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="2ad22-131">OpenStatusEntry</span></span>](iablogon-openstatusentry.md) <br/> |<span data-ttu-id="2ad22-132">打开提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="2ad22-132">Opens the provider's status object.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-133">OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="2ad22-133">OpenTemplateID</span></span>](iablogon-opentemplateid.md) <br/> |<span data-ttu-id="2ad22-134">打开具有数据驻留在承载通讯簿提供程序中的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="2ad22-134">Opens a recipient entry that has data residing in a host address book provider.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-135">GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="2ad22-135">GetOneOffTable</span></span>](iablogon-getoneofftable.md) <br/> |<span data-ttu-id="2ad22-136">返回一个一次性模板，用于创建要添加到的传出邮件的收件人列表的收件人的表。</span><span class="sxs-lookup"><span data-stu-id="2ad22-136">Returns a table of one-off templates for creating recipients to be added to the recipient list of an outgoing message.</span></span>  <br/> |
|[<span data-ttu-id="2ad22-137">PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="2ad22-137">PrepareRecips</span></span>](iablogon-preparerecips.md) <br/> |<span data-ttu-id="2ad22-138">通过在邮件系统，以供以后使用准备收件人列表。</span><span class="sxs-lookup"><span data-stu-id="2ad22-138">Prepares a recipient list for later use by the messaging system.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ad22-139">备注</span><span class="sxs-lookup"><span data-stu-id="2ad22-139">Remarks</span></span>

<span data-ttu-id="2ad22-140">**IABLogon**接口的方法的常规信息，请参阅[实现服务提供程序登录名](implementing-service-provider-logon.md)。</span><span class="sxs-lookup"><span data-stu-id="2ad22-140">For general information about the methods of the **IABLogon** interface, see [Implementing Service Provider Logon](implementing-service-provider-logon.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ad22-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ad22-141">See also</span></span>



[<span data-ttu-id="2ad22-142">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="2ad22-142">MAPI Interfaces</span></span>](mapi-interfaces.md)

