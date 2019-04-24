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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc8615fcd984623ae9c17c45fb7b51a4498a723b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348830"
---
# <a name="iablogon--iunknown"></a><span data-ttu-id="2f067-103">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2f067-103">IABLogon : IUnknown</span></span>

  
  
<span data-ttu-id="2f067-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f067-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f067-105">访问通讯簿提供程序中的资源。</span><span class="sxs-lookup"><span data-stu-id="2f067-105">Accesses resources in an address book provider.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2f067-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2f067-106">Header file:</span></span>  <br/> |<span data-ttu-id="2f067-107">Mapispi</span><span class="sxs-lookup"><span data-stu-id="2f067-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="2f067-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="2f067-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="2f067-109">通讯簿登录对象</span><span class="sxs-lookup"><span data-stu-id="2f067-109">Address book logon objects</span></span>  <br/> |
|<span data-ttu-id="2f067-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="2f067-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="2f067-111">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="2f067-111">Address book providers</span></span>  <br/> |
|<span data-ttu-id="2f067-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="2f067-112">Called by:</span></span>  <br/> |<span data-ttu-id="2f067-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="2f067-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="2f067-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="2f067-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="2f067-115">IID_IABLogon</span><span class="sxs-lookup"><span data-stu-id="2f067-115">IID_IABLogon</span></span>  <br/> |
|<span data-ttu-id="2f067-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="2f067-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="2f067-117">LPABLOGON</span><span class="sxs-lookup"><span data-stu-id="2f067-117">LPABLOGON</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="2f067-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="2f067-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="2f067-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="2f067-119">GetLastError</span></span>](iablogon-getlasterror.md) <br/> |<span data-ttu-id="2f067-120">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含以前的通讯簿提供程序错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="2f067-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous address book provider error.</span></span>  <br/> |
|[<span data-ttu-id="2f067-121">注销</span><span class="sxs-lookup"><span data-stu-id="2f067-121">Logoff</span></span>](iablogon-logoff.md) <br/> |<span data-ttu-id="2f067-122">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="2f067-122">Initiates the logoff process.</span></span>  <br/> |
|[<span data-ttu-id="2f067-123">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="2f067-123">OpenEntry</span></span>](iablogon-openentry.md) <br/> |<span data-ttu-id="2f067-124">打开容器、邮件用户或通讯组列表, 并返回指向接口实现的指针, 以提供进一步的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f067-124">Opens a container, messaging user, or distribution list, and returns a pointer to an interface implementation to provide further access.</span></span>  <br/> |
|[<span data-ttu-id="2f067-125">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="2f067-125">CompareEntryIDs</span></span>](iablogon-compareentryids.md) <br/> |<span data-ttu-id="2f067-126">对两个条目标识符进行比较, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="2f067-126">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="2f067-127">她们</span><span class="sxs-lookup"><span data-stu-id="2f067-127">Advise</span></span>](iablogon-advise.md) <br/> |<span data-ttu-id="2f067-128">注册调用方, 以接收影响容器、邮件用户或通讯组列表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="2f067-128">Registers the caller to receive notification of specified events that affect a container, messaging user, or distribution list.</span></span>  <br/> |
|[<span data-ttu-id="2f067-129">Unadvise</span><span class="sxs-lookup"><span data-stu-id="2f067-129">Unadvise</span></span>](iablogon-unadvise.md) <br/> |<span data-ttu-id="2f067-130">取消以前通过调用**Advise**方法而设置的通知。</span><span class="sxs-lookup"><span data-stu-id="2f067-130">Cancels notifications that were previously set up with a call to the **Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="2f067-131">OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="2f067-131">OpenStatusEntry</span></span>](iablogon-openstatusentry.md) <br/> |<span data-ttu-id="2f067-132">打开提供程序的 status 对象。</span><span class="sxs-lookup"><span data-stu-id="2f067-132">Opens the provider's status object.</span></span>  <br/> |
|[<span data-ttu-id="2f067-133">OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="2f067-133">OpenTemplateID</span></span>](iablogon-opentemplateid.md) <br/> |<span data-ttu-id="2f067-134">打开包含驻留在主机通讯簿提供程序中的数据的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="2f067-134">Opens a recipient entry that has data residing in a host address book provider.</span></span>  <br/> |
|[<span data-ttu-id="2f067-135">GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="2f067-135">GetOneOffTable</span></span>](iablogon-getoneofftable.md) <br/> |<span data-ttu-id="2f067-136">返回一个一次性模板表, 用于创建要添加到传出邮件的收件人列表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="2f067-136">Returns a table of one-off templates for creating recipients to be added to the recipient list of an outgoing message.</span></span>  <br/> |
|[<span data-ttu-id="2f067-137">PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="2f067-137">PrepareRecips</span></span>](iablogon-preparerecips.md) <br/> |<span data-ttu-id="2f067-138">准备收件人列表, 以供邮件系统以后使用。</span><span class="sxs-lookup"><span data-stu-id="2f067-138">Prepares a recipient list for later use by the messaging system.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2f067-139">注解</span><span class="sxs-lookup"><span data-stu-id="2f067-139">Remarks</span></span>

<span data-ttu-id="2f067-140">有关**IABLogon**接口的方法的一般信息, 请参阅[实现服务提供程序登录](implementing-service-provider-logon.md)。</span><span class="sxs-lookup"><span data-stu-id="2f067-140">For general information about the methods of the **IABLogon** interface, see [Implementing Service Provider Logon](implementing-service-provider-logon.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f067-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f067-141">See also</span></span>



[<span data-ttu-id="2f067-142">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="2f067-142">MAPI Interfaces</span></span>](mapi-interfaces.md)

