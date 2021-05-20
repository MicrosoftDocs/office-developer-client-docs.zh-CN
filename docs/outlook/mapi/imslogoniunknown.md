---
title: IMSLogon IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon
api_type:
- COM
ms.assetid: d87093dc-f705-465f-ab3c-944ca0cd3e54
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 991e48aa458a58ad2d7d688e81dbb357ef9bda5b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428877"
---
# <a name="imslogon--iunknown"></a><span data-ttu-id="e928c-103">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e928c-103">IMSLogon : IUnknown</span></span>

  
  
<span data-ttu-id="e928c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e928c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e928c-105">访问邮件存储登录对象中的资源。</span><span class="sxs-lookup"><span data-stu-id="e928c-105">Accesses resources in a message store logon object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e928c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e928c-106">Header file:</span></span>  <br/> |<span data-ttu-id="e928c-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="e928c-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="e928c-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="e928c-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="e928c-109">邮件存储登录对象</span><span class="sxs-lookup"><span data-stu-id="e928c-109">Message store logon objects</span></span>  <br/> |
|<span data-ttu-id="e928c-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="e928c-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="e928c-111">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e928c-111">Message store providers</span></span>  <br/> |
|<span data-ttu-id="e928c-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="e928c-112">Called by:</span></span>  <br/> |<span data-ttu-id="e928c-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="e928c-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="e928c-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="e928c-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="e928c-115">IID_IMSLogon</span><span class="sxs-lookup"><span data-stu-id="e928c-115">IID_IMSLogon</span></span>  <br/> |
|<span data-ttu-id="e928c-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="e928c-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="e928c-117">LPMSLOGON</span><span class="sxs-lookup"><span data-stu-id="e928c-117">LPMSLOGON</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="e928c-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="e928c-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="e928c-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="e928c-119">GetLastError</span></span>](imslogon-getlasterror.md) <br/> |<span data-ttu-id="e928c-120">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关邮件存储对象发生的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="e928c-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the last error that occurred for the message store object.</span></span>  <br/> |
|[<span data-ttu-id="e928c-121">注销</span><span class="sxs-lookup"><span data-stu-id="e928c-121">Logoff</span></span>](imslogon-logoff.md) <br/> |<span data-ttu-id="e928c-122">注销邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="e928c-122">Logs off a message store provider.</span></span>  <br/> |
|[<span data-ttu-id="e928c-123">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="e928c-123">OpenEntry</span></span>](imslogon-openentry.md) <br/> |<span data-ttu-id="e928c-124">打开文件夹或邮件对象，并返回指向该对象的指针以提供进一步的访问。</span><span class="sxs-lookup"><span data-stu-id="e928c-124">Opens a folder or message object and returns a pointer to the object to provide further access.</span></span>  <br/> |
|[<span data-ttu-id="e928c-125">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="e928c-125">CompareEntryIDs</span></span>](imslogon-compareentryids.md) <br/> |<span data-ttu-id="e928c-126">比较两个条目标识符以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="e928c-126">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="e928c-127">建议</span><span class="sxs-lookup"><span data-stu-id="e928c-127">Advise</span></span>](imslogon-advise.md) <br/> |<span data-ttu-id="e928c-128">向邮件存储提供程序注册对象，以接收有关邮件存储中更改的通知。</span><span class="sxs-lookup"><span data-stu-id="e928c-128">Registers an object with a message store provider for notifications about changes in the message store.</span></span>  <br/> |
|[<span data-ttu-id="e928c-129">非企业</span><span class="sxs-lookup"><span data-stu-id="e928c-129">Unadvise</span></span>](imslogon-unadvise.md) <br/> |<span data-ttu-id="e928c-130">通过调用 **IMSLogon：：Advise** 方法，删除对象对之前建立的邮件存储更改通知的注册。</span><span class="sxs-lookup"><span data-stu-id="e928c-130">Removes an object's registration for notification of message store changes previously established by using a call to the **IMSLogon::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="e928c-131">OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="e928c-131">OpenStatusEntry</span></span>](imslogon-openstatusentry.md) <br/> |<span data-ttu-id="e928c-132">打开 status 对象。</span><span class="sxs-lookup"><span data-stu-id="e928c-132">Opens a status object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e928c-133">备注</span><span class="sxs-lookup"><span data-stu-id="e928c-133">Remarks</span></span>

<span data-ttu-id="e928c-134">邮件存储登录对象是 MAPI 直接调用的打开邮件存储提供程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="e928c-134">The message store logon object is the part of an open message store provider that MAPI calls directly.</span></span> <span data-ttu-id="e928c-135">MAPI 调用的邮件存储登录对象与客户端应用程序调用的邮件存储对象之间具有一对一对应关系;你可以将登录名视为一个公开两个接口的对象，</span><span class="sxs-lookup"><span data-stu-id="e928c-135">There is a one-to-one correspondence between the message store logon object that MAPI calls and the message store object that client applications call; you can think of the logon and store objects as one object that exposes two interfaces.</span></span> <span data-ttu-id="e928c-136">这两个对象一起创建并释放在一起。</span><span class="sxs-lookup"><span data-stu-id="e928c-136">The two objects are created together and freed together.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e928c-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e928c-137">See also</span></span>



[<span data-ttu-id="e928c-138">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="e928c-138">MAPI Interfaces</span></span>](mapi-interfaces.md)

