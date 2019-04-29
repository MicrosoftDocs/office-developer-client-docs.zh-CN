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
# <a name="imslogon--iunknown"></a><span data-ttu-id="b119f-103">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b119f-103">IMSLogon : IUnknown</span></span>

  
  
<span data-ttu-id="b119f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b119f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b119f-105">访问邮件存储区登录对象中的资源。</span><span class="sxs-lookup"><span data-stu-id="b119f-105">Accesses resources in a message store logon object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b119f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b119f-106">Header file:</span></span>  <br/> |<span data-ttu-id="b119f-107">Mapispi</span><span class="sxs-lookup"><span data-stu-id="b119f-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="b119f-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="b119f-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="b119f-109">邮件存储区登录对象</span><span class="sxs-lookup"><span data-stu-id="b119f-109">Message store logon objects</span></span>  <br/> |
|<span data-ttu-id="b119f-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="b119f-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="b119f-111">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="b119f-111">Message store providers</span></span>  <br/> |
|<span data-ttu-id="b119f-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="b119f-112">Called by:</span></span>  <br/> |<span data-ttu-id="b119f-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="b119f-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="b119f-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="b119f-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b119f-115">IID_IMSLogon</span><span class="sxs-lookup"><span data-stu-id="b119f-115">IID_IMSLogon</span></span>  <br/> |
|<span data-ttu-id="b119f-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="b119f-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="b119f-117">LPMSLOGON</span><span class="sxs-lookup"><span data-stu-id="b119f-117">LPMSLOGON</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b119f-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="b119f-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="b119f-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="b119f-119">GetLastError</span></span>](imslogon-getlasterror.md) <br/> |<span data-ttu-id="b119f-120">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关邮件存储对象的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="b119f-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the last error that occurred for the message store object.</span></span>  <br/> |
|[<span data-ttu-id="b119f-121">注销</span><span class="sxs-lookup"><span data-stu-id="b119f-121">Logoff</span></span>](imslogon-logoff.md) <br/> |<span data-ttu-id="b119f-122">注销邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="b119f-122">Logs off a message store provider.</span></span>  <br/> |
|[<span data-ttu-id="b119f-123">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="b119f-123">OpenEntry</span></span>](imslogon-openentry.md) <br/> |<span data-ttu-id="b119f-124">打开一个文件夹或邮件对象, 并返回指向该对象的指针, 以提供进一步的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b119f-124">Opens a folder or message object and returns a pointer to the object to provide further access.</span></span>  <br/> |
|[<span data-ttu-id="b119f-125">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="b119f-125">CompareEntryIDs</span></span>](imslogon-compareentryids.md) <br/> |<span data-ttu-id="b119f-126">对两个条目标识符进行比较, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="b119f-126">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="b119f-127">她们</span><span class="sxs-lookup"><span data-stu-id="b119f-127">Advise</span></span>](imslogon-advise.md) <br/> |<span data-ttu-id="b119f-128">向邮件存储提供程序注册对象, 以获取有关邮件存储区中的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="b119f-128">Registers an object with a message store provider for notifications about changes in the message store.</span></span>  <br/> |
|[<span data-ttu-id="b119f-129">Unadvise</span><span class="sxs-lookup"><span data-stu-id="b119f-129">Unadvise</span></span>](imslogon-unadvise.md) <br/> |<span data-ttu-id="b119f-130">使用对**IMSLogon:: Advise**方法的调用, 删除以前建立的邮件存储区更改通知的对象注册。</span><span class="sxs-lookup"><span data-stu-id="b119f-130">Removes an object's registration for notification of message store changes previously established by using a call to the **IMSLogon::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="b119f-131">OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="b119f-131">OpenStatusEntry</span></span>](imslogon-openstatusentry.md) <br/> |<span data-ttu-id="b119f-132">打开一个 status 对象。</span><span class="sxs-lookup"><span data-stu-id="b119f-132">Opens a status object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b119f-133">说明</span><span class="sxs-lookup"><span data-stu-id="b119f-133">Remarks</span></span>

<span data-ttu-id="b119f-134">邮件存储区登录对象是 MAPI 直接调用的打开邮件存储提供程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="b119f-134">The message store logon object is the part of an open message store provider that MAPI calls directly.</span></span> <span data-ttu-id="b119f-135">MAPI 调用的邮件存储登录对象和客户端应用程序调用的邮件存储对象之间存在一对一的对应关系;您可以将登录和存储对象视为一个公开两个接口的对象。</span><span class="sxs-lookup"><span data-stu-id="b119f-135">There is a one-to-one correspondence between the message store logon object that MAPI calls and the message store object that client applications call; you can think of the logon and store objects as one object that exposes two interfaces.</span></span> <span data-ttu-id="b119f-136">这两个对象一起创建并一起释放。</span><span class="sxs-lookup"><span data-stu-id="b119f-136">The two objects are created together and freed together.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b119f-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b119f-137">See also</span></span>



[<span data-ttu-id="b119f-138">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="b119f-138">MAPI Interfaces</span></span>](mapi-interfaces.md)

