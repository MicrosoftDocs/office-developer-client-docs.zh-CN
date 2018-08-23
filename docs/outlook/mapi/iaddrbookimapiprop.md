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
ms.openlocfilehash: 44bc6de420953bd665bd3caa336b76b15c1effd6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579457"
---
# <a name="iaddrbook--imapiprop"></a><span data-ttu-id="bc28e-103">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="bc28e-103">IAddrBook : IMAPIProp</span></span>

  
  
<span data-ttu-id="bc28e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc28e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc28e-105">支持对 MAPI 通讯簿的访问，包括操作，例如显示常见对话框;打开容器，邮件用户和通讯组列表;而在执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="bc28e-105">Supports access to the MAPI address book and includes operations such as displaying common dialog boxes; opening containers, messaging users, and distribution lists; and performing name resolution.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bc28e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bc28e-106">Header file:</span></span>  <br/> |<span data-ttu-id="bc28e-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="bc28e-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="bc28e-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="bc28e-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="bc28e-109">地址簿对象</span><span class="sxs-lookup"><span data-stu-id="bc28e-109">Address book objects</span></span>  <br/> |
|<span data-ttu-id="bc28e-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="bc28e-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="bc28e-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="bc28e-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="bc28e-112">调用：</span><span class="sxs-lookup"><span data-stu-id="bc28e-112">Called by:</span></span>  <br/> |<span data-ttu-id="bc28e-113">客户端应用程序，服务提供商</span><span class="sxs-lookup"><span data-stu-id="bc28e-113">Client applications, service providers</span></span>  <br/> |
|<span data-ttu-id="bc28e-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="bc28e-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="bc28e-115">IID_IAddrBook</span><span class="sxs-lookup"><span data-stu-id="bc28e-115">IID_IAddrBook</span></span>  <br/> |
|<span data-ttu-id="bc28e-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="bc28e-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="bc28e-117">LPADRBOOK</span><span class="sxs-lookup"><span data-stu-id="bc28e-117">LPADRBOOK</span></span>  <br/> |
|<span data-ttu-id="bc28e-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="bc28e-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="bc28e-119">不可写</span><span class="sxs-lookup"><span data-stu-id="bc28e-119">Not writable</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="bc28e-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="bc28e-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="bc28e-121">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="bc28e-121">OpenEntry</span></span>](iaddrbook-openentry.md) <br/> |<span data-ttu-id="bc28e-122">打开的通讯簿条目，并返回可用于访问该条目的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="bc28e-122">Opens an address book entry and returns a pointer to an interface that can be used to access the entry.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-123">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="bc28e-123">CompareEntryIDs</span></span>](iaddrbook-compareentryids.md) <br/> |<span data-ttu-id="bc28e-124">比较两个条目标识符属于特定地址簿提供程序，以确定它们是否引用同一个通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="bc28e-124">Compares two entry identifiers that belong to a particular address book provider to determine whether they refer to the same address book object.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-125">建议</span><span class="sxs-lookup"><span data-stu-id="bc28e-125">Advise</span></span>](iaddrbook-advise.md) <br/> |<span data-ttu-id="bc28e-126">注册接收有关对一个或多个条目的更改的通知通讯簿中的客户端或服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="bc28e-126">Registers a client or service provider to receive notifications about changes to one or more entries in the address book.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-127">取消通知</span><span class="sxs-lookup"><span data-stu-id="bc28e-127">Unadvise</span></span>](iaddrbook-unadvise.md) <br/> |<span data-ttu-id="bc28e-128">取消以前建立的通讯簿条目的通知注册。</span><span class="sxs-lookup"><span data-stu-id="bc28e-128">Cancels a notification registration previously established for an address book entry.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-129">CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="bc28e-129">CreateOneOff</span></span>](iaddrbook-createoneoff.md) <br/> |<span data-ttu-id="bc28e-130">创建一个一次性地址的项标识符。</span><span class="sxs-lookup"><span data-stu-id="bc28e-130">Creates an entry identifier for a one-off address.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-131">NewEntry</span><span class="sxs-lookup"><span data-stu-id="bc28e-131">NewEntry</span></span>](iaddrbook-newentry.md) <br/> |<span data-ttu-id="bc28e-132">将一个新收件人添加到通讯簿容器或传出邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="bc28e-132">Adds a new recipient to an address book container or to the recipient list of an outgoing message.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-133">ResolveName</span><span class="sxs-lookup"><span data-stu-id="bc28e-133">ResolveName</span></span>](iaddrbook-resolvename.md) <br/> |<span data-ttu-id="bc28e-134">执行名称解析，分配给收件人列表中的收件人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="bc28e-134">Performs name resolution, assigning entry identifiers to recipients in a recipient list.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-135">地址</span><span class="sxs-lookup"><span data-stu-id="bc28e-135">Address</span></span>](iaddrbook-address.md) <br/> |<span data-ttu-id="bc28e-136">显示 Outlook 通讯簿对话框。</span><span class="sxs-lookup"><span data-stu-id="bc28e-136">Displays the Outlook address book dialog box.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-137">详细信息</span><span class="sxs-lookup"><span data-stu-id="bc28e-137">Details</span></span>](iaddrbook-details.md) <br/> |<span data-ttu-id="bc28e-138">显示一个对话框，显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bc28e-138">Displays a dialog box that shows details about a particular address book entry.</span></span>  <br/> |
|<span data-ttu-id="bc28e-139">**RecipOptions**</span><span class="sxs-lookup"><span data-stu-id="bc28e-139">**RecipOptions**</span></span> <br/> | <span data-ttu-id="bc28e-140">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="bc28e-140">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="bc28e-141">**QueryDefaultRecipOpt**</span><span class="sxs-lookup"><span data-stu-id="bc28e-141">**QueryDefaultRecipOpt**</span></span> <br/> | <span data-ttu-id="bc28e-142">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="bc28e-142">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="bc28e-143">GetPAB</span><span class="sxs-lookup"><span data-stu-id="bc28e-143">GetPAB</span></span>](iaddrbook-getpab.md) <br/> |<span data-ttu-id="bc28e-144">返回的项标识符指定为个人通讯簿 (PAB) 的容器。</span><span class="sxs-lookup"><span data-stu-id="bc28e-144">Returns the entry identifier of the container that is designated as the personal address book (PAB).</span></span>  <br/> |
|[<span data-ttu-id="bc28e-145">SetPAB</span><span class="sxs-lookup"><span data-stu-id="bc28e-145">SetPAB</span></span>](iaddrbook-setpab.md) <br/> |<span data-ttu-id="bc28e-146">指定为个人通讯簿 (PAB) 特定的容器。</span><span class="sxs-lookup"><span data-stu-id="bc28e-146">Designates a particular container as the personal address book (PAB).</span></span>  <br/> |
|[<span data-ttu-id="bc28e-147">GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="bc28e-147">GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md) <br/> |<span data-ttu-id="bc28e-148">返回初始的通讯簿容器的项标识符。</span><span class="sxs-lookup"><span data-stu-id="bc28e-148">Returns the entry identifier for the initial address book container.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-149">SetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="bc28e-149">SetDefaultDir</span></span>](iaddrbook-setdefaultdir.md) <br/> |<span data-ttu-id="bc28e-150">建立的最初可默认通讯簿容器为指定的容器。</span><span class="sxs-lookup"><span data-stu-id="bc28e-150">Establishes the specified container as the default address book container that is initially made available.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-151">GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="bc28e-151">GetSearchPath</span></span>](iaddrbook-getsearchpath.md) <br/> |<span data-ttu-id="bc28e-152">返回一个已排序的列表项标识符启动[ResolveName](iaddrbook-resolvename.md)方法的名称解析进程中包含的容器。</span><span class="sxs-lookup"><span data-stu-id="bc28e-152">Returns an ordered list of entry identifiers of the containers to be included in the name resolution process initiated by the [ResolveName](iaddrbook-resolvename.md) method.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-153">SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="bc28e-153">SetSearchPath</span></span>](iaddrbook-setsearchpath.md) <br/> |<span data-ttu-id="bc28e-154">设置中的配置文件的名称解析过程使用新的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="bc28e-154">Sets a new search path in the profile that is used for the name resolution process.</span></span>  <br/> |
|[<span data-ttu-id="bc28e-155">PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="bc28e-155">PrepareRecips</span></span>](iaddrbook-preparerecips.md) <br/> |<span data-ttu-id="bc28e-156">通过在邮件系统，以供以后使用准备收件人列表。</span><span class="sxs-lookup"><span data-stu-id="bc28e-156">Prepares a recipient list for later use by the messaging system.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bc28e-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc28e-157">See also</span></span>



[<span data-ttu-id="bc28e-158">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="bc28e-158">MAPI Interfaces</span></span>](mapi-interfaces.md)

