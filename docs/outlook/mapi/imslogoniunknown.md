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
ms.openlocfilehash: 013903f36bf648c4aed194c88104e7dd981b199f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563938"
---
# <a name="imslogon--iunknown"></a><span data-ttu-id="2cb0d-103">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2cb0d-103">IMSLogon : IUnknown</span></span>

  
  
<span data-ttu-id="2cb0d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2cb0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2cb0d-105">在邮件中的访问资源存储登录对象。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-105">Accesses resources in a message store logon object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2cb0d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2cb0d-106">Header file:</span></span>  <br/> |<span data-ttu-id="2cb0d-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="2cb0d-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="2cb0d-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="2cb0d-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="2cb0d-109">消息存储登录对象</span><span class="sxs-lookup"><span data-stu-id="2cb0d-109">Message store logon objects</span></span>  <br/> |
|<span data-ttu-id="2cb0d-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2cb0d-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="2cb0d-111">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="2cb0d-111">Message store providers</span></span>  <br/> |
|<span data-ttu-id="2cb0d-112">调用：</span><span class="sxs-lookup"><span data-stu-id="2cb0d-112">Called by:</span></span>  <br/> |<span data-ttu-id="2cb0d-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="2cb0d-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="2cb0d-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="2cb0d-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="2cb0d-115">IID_IMSLogon</span><span class="sxs-lookup"><span data-stu-id="2cb0d-115">IID_IMSLogon</span></span>  <br/> |
|<span data-ttu-id="2cb0d-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="2cb0d-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="2cb0d-117">LPMSLOGON</span><span class="sxs-lookup"><span data-stu-id="2cb0d-117">LPMSLOGON</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="2cb0d-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="2cb0d-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="2cb0d-119">时出错</span><span class="sxs-lookup"><span data-stu-id="2cb0d-119">GetLastError</span></span>](imslogon-getlasterror.md) <br/> |<span data-ttu-id="2cb0d-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含上次消息存储对象发生的错误有关的信息。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the last error that occurred for the message store object.</span></span>  <br/> |
|[<span data-ttu-id="2cb0d-121">注销</span><span class="sxs-lookup"><span data-stu-id="2cb0d-121">Logoff</span></span>](imslogon-logoff.md) <br/> |<span data-ttu-id="2cb0d-122">注销一条消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-122">Logs off a message store provider.</span></span>  <br/> |
|[<span data-ttu-id="2cb0d-123">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="2cb0d-123">OpenEntry</span></span>](imslogon-openentry.md) <br/> |<span data-ttu-id="2cb0d-124">打开文件夹或 message 对象并返回指向要进一步提供访问权限的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-124">Opens a folder or message object and returns a pointer to the object to provide further access.</span></span>  <br/> |
|[<span data-ttu-id="2cb0d-125">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="2cb0d-125">CompareEntryIDs</span></span>](imslogon-compareentryids.md) <br/> |<span data-ttu-id="2cb0d-126">比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-126">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="2cb0d-127">建议</span><span class="sxs-lookup"><span data-stu-id="2cb0d-127">Advise</span></span>](imslogon-advise.md) <br/> |<span data-ttu-id="2cb0d-128">使用有关邮件存储区中的更改的通知的消息存储提供程序注册的对象。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-128">Registers an object with a message store provider for notifications about changes in the message store.</span></span>  <br/> |
|[<span data-ttu-id="2cb0d-129">取消通知</span><span class="sxs-lookup"><span data-stu-id="2cb0d-129">Unadvise</span></span>](imslogon-unadvise.md) <br/> |<span data-ttu-id="2cb0d-130">删除以前使用调用**IMSLogon::Advise**方法建立的邮件存储更改的通知的对象的注册。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-130">Removes an object's registration for notification of message store changes previously established by using a call to the **IMSLogon::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="2cb0d-131">OpenStatusEntry</span><span class="sxs-lookup"><span data-stu-id="2cb0d-131">OpenStatusEntry</span></span>](imslogon-openstatusentry.md) <br/> |<span data-ttu-id="2cb0d-132">打开状态对象。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-132">Opens a status object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2cb0d-133">注解</span><span class="sxs-lookup"><span data-stu-id="2cb0d-133">Remarks</span></span>

<span data-ttu-id="2cb0d-134">消息存储登录对象是 MAPI 直接调用打开的邮件存储提供程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-134">The message store logon object is the part of an open message store provider that MAPI calls directly.</span></span> <span data-ttu-id="2cb0d-135">MAPI 呼叫和消息存储对象，该客户端应用程序调用; 对象的消息存储登录对象之间没有一对一的对应关系可以当作登录并存储对象作为公开两个接口的一个对象。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-135">There is a one-to-one correspondence between the message store logon object that MAPI calls and the message store object that client applications call; you can think of the logon and store objects as one object that exposes two interfaces.</span></span> <span data-ttu-id="2cb0d-136">两个对象一起创建组合在一起和释放。</span><span class="sxs-lookup"><span data-stu-id="2cb0d-136">The two objects are created together and freed together.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2cb0d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cb0d-137">See also</span></span>



[<span data-ttu-id="2cb0d-138">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="2cb0d-138">MAPI Interfaces</span></span>](mapi-interfaces.md)

