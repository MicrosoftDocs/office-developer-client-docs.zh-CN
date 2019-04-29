---
title: IAddrBook IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook
api_type:
- COM
ms.assetid: 9ccacbc0-10d5-40f9-a12b-d090a21d0d49
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da71e9dd5f2fc20bb1daf528f4466ea29507bf06
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429822"
---
# <a name="iaddrbook--imapiprop"></a><span data-ttu-id="61dfc-103">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="61dfc-103">IAddrBook : IMAPIProp</span></span>

  
  
<span data-ttu-id="61dfc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61dfc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61dfc-105">支持对 MAPI 通讯簿的访问, 包括显示常见对话框等操作。打开容器、邮件用户和通讯组列表;并执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="61dfc-105">Supports access to the MAPI address book and includes operations such as displaying common dialog boxes; opening containers, messaging users, and distribution lists; and performing name resolution.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="61dfc-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="61dfc-106">Header file:</span></span>  <br/> |<span data-ttu-id="61dfc-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="61dfc-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="61dfc-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="61dfc-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="61dfc-109">通讯簿对象</span><span class="sxs-lookup"><span data-stu-id="61dfc-109">Address book objects</span></span>  <br/> |
|<span data-ttu-id="61dfc-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="61dfc-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="61dfc-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="61dfc-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="61dfc-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="61dfc-112">Called by:</span></span>  <br/> |<span data-ttu-id="61dfc-113">客户端应用程序、服务提供商</span><span class="sxs-lookup"><span data-stu-id="61dfc-113">Client applications, service providers</span></span>  <br/> |
|<span data-ttu-id="61dfc-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="61dfc-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="61dfc-115">IID_IAddrBook</span><span class="sxs-lookup"><span data-stu-id="61dfc-115">IID_IAddrBook</span></span>  <br/> |
|<span data-ttu-id="61dfc-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="61dfc-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="61dfc-117">LPADRBOOK</span><span class="sxs-lookup"><span data-stu-id="61dfc-117">LPADRBOOK</span></span>  <br/> |
|<span data-ttu-id="61dfc-118">事务模型:</span><span class="sxs-lookup"><span data-stu-id="61dfc-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="61dfc-119">不可写</span><span class="sxs-lookup"><span data-stu-id="61dfc-119">Not writable</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="61dfc-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="61dfc-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="61dfc-121">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="61dfc-121">OpenEntry</span></span>](iaddrbook-openentry.md) <br/> |<span data-ttu-id="61dfc-122">打开通讯簿条目并返回指向可用于访问该条目的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="61dfc-122">Opens an address book entry and returns a pointer to an interface that can be used to access the entry.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-123">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="61dfc-123">CompareEntryIDs</span></span>](iaddrbook-compareentryids.md) <br/> |<span data-ttu-id="61dfc-124">对属于特定通讯簿提供程序的两个条目标识符进行比较, 以确定它们是否引用相同的通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="61dfc-124">Compares two entry identifiers that belong to a particular address book provider to determine whether they refer to the same address book object.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-125">她们</span><span class="sxs-lookup"><span data-stu-id="61dfc-125">Advise</span></span>](iaddrbook-advise.md) <br/> |<span data-ttu-id="61dfc-126">注册客户端或服务提供商, 以接收有关通讯簿中的一个或多个条目的更改通知。</span><span class="sxs-lookup"><span data-stu-id="61dfc-126">Registers a client or service provider to receive notifications about changes to one or more entries in the address book.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-127">Unadvise</span><span class="sxs-lookup"><span data-stu-id="61dfc-127">Unadvise</span></span>](iaddrbook-unadvise.md) <br/> |<span data-ttu-id="61dfc-128">取消之前为通讯簿条目建立的通知注册。</span><span class="sxs-lookup"><span data-stu-id="61dfc-128">Cancels a notification registration previously established for an address book entry.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-129">CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="61dfc-129">CreateOneOff</span></span>](iaddrbook-createoneoff.md) <br/> |<span data-ttu-id="61dfc-130">为一次性地址创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="61dfc-130">Creates an entry identifier for a one-off address.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-131">NewEntry</span><span class="sxs-lookup"><span data-stu-id="61dfc-131">NewEntry</span></span>](iaddrbook-newentry.md) <br/> |<span data-ttu-id="61dfc-132">将新的收件人添加到通讯簿容器或传出邮件的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="61dfc-132">Adds a new recipient to an address book container or to the recipient list of an outgoing message.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-133">ResolveName</span><span class="sxs-lookup"><span data-stu-id="61dfc-133">ResolveName</span></span>](iaddrbook-resolvename.md) <br/> |<span data-ttu-id="61dfc-134">执行名称解析, 将条目标识符分配给收件人列表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="61dfc-134">Performs name resolution, assigning entry identifiers to recipients in a recipient list.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-135">地址</span><span class="sxs-lookup"><span data-stu-id="61dfc-135">Address</span></span>](iaddrbook-address.md) <br/> |<span data-ttu-id="61dfc-136">显示 "Outlook 通讯簿" 对话框。</span><span class="sxs-lookup"><span data-stu-id="61dfc-136">Displays the Outlook address book dialog box.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-137">详细信息</span><span class="sxs-lookup"><span data-stu-id="61dfc-137">Details</span></span>](iaddrbook-details.md) <br/> |<span data-ttu-id="61dfc-138">显示一个对话框, 显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="61dfc-138">Displays a dialog box that shows details about a particular address book entry.</span></span>  <br/> |
|<span data-ttu-id="61dfc-139">**RecipOptions**</span><span class="sxs-lookup"><span data-stu-id="61dfc-139">**RecipOptions**</span></span> <br/> | <span data-ttu-id="61dfc-140">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="61dfc-140">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="61dfc-141">**QueryDefaultRecipOpt**</span><span class="sxs-lookup"><span data-stu-id="61dfc-141">**QueryDefaultRecipOpt**</span></span> <br/> | <span data-ttu-id="61dfc-142">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="61dfc-142">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="61dfc-143">GetPAB</span><span class="sxs-lookup"><span data-stu-id="61dfc-143">GetPAB</span></span>](iaddrbook-getpab.md) <br/> |<span data-ttu-id="61dfc-144">返回指定为 "个人通讯簿" (PAB) 的容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="61dfc-144">Returns the entry identifier of the container that is designated as the personal address book (PAB).</span></span>  <br/> |
|[<span data-ttu-id="61dfc-145">SetPAB</span><span class="sxs-lookup"><span data-stu-id="61dfc-145">SetPAB</span></span>](iaddrbook-setpab.md) <br/> |<span data-ttu-id="61dfc-146">指定特定的容器作为个人通讯簿 (PAB)。</span><span class="sxs-lookup"><span data-stu-id="61dfc-146">Designates a particular container as the personal address book (PAB).</span></span>  <br/> |
|[<span data-ttu-id="61dfc-147">GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="61dfc-147">GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md) <br/> |<span data-ttu-id="61dfc-148">返回初始通讯簿容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="61dfc-148">Returns the entry identifier for the initial address book container.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-149">SetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="61dfc-149">SetDefaultDir</span></span>](iaddrbook-setdefaultdir.md) <br/> |<span data-ttu-id="61dfc-150">将指定的容器建立为最初可用的默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="61dfc-150">Establishes the specified container as the default address book container that is initially made available.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-151">GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="61dfc-151">GetSearchPath</span></span>](iaddrbook-getsearchpath.md) <br/> |<span data-ttu-id="61dfc-152">返回要包含在由[ResolveName](iaddrbook-resolvename.md)方法启动的名称解析进程中的容器的条目标识符的已排序列表。</span><span class="sxs-lookup"><span data-stu-id="61dfc-152">Returns an ordered list of entry identifiers of the containers to be included in the name resolution process initiated by the [ResolveName](iaddrbook-resolvename.md) method.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-153">SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="61dfc-153">SetSearchPath</span></span>](iaddrbook-setsearchpath.md) <br/> |<span data-ttu-id="61dfc-154">在用于名称解析过程的配置文件中设置新的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="61dfc-154">Sets a new search path in the profile that is used for the name resolution process.</span></span>  <br/> |
|[<span data-ttu-id="61dfc-155">PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="61dfc-155">PrepareRecips</span></span>](iaddrbook-preparerecips.md) <br/> |<span data-ttu-id="61dfc-156">准备收件人列表, 以供邮件系统以后使用。</span><span class="sxs-lookup"><span data-stu-id="61dfc-156">Prepares a recipient list for later use by the messaging system.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="61dfc-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61dfc-157">See also</span></span>



[<span data-ttu-id="61dfc-158">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="61dfc-158">MAPI Interfaces</span></span>](mapi-interfaces.md)

