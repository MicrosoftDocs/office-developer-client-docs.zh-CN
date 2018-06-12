---
title: 状态表和状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 203765c1-4b08-4032-a5bf-18f3e752a899
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 774aaea0365066981b9d6426a2579160f6578844
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778877"
---
# <a name="status-table-and-status-objects"></a><span data-ttu-id="a1a93-103">状态表和状态对象</span><span class="sxs-lookup"><span data-stu-id="a1a93-103">Status Table and Status Objects</span></span>

  
  
<span data-ttu-id="a1a93-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a1a93-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a1a93-105">MAPI 提供了一个表格的 MAPI 子系统、 MAPI 后台处理程序、 通讯簿或的特定服务提供商的状态信息。</span><span class="sxs-lookup"><span data-stu-id="a1a93-105">MAPI provides a table with information about the status of the MAPI subsystem, MAPI spooler, address book, or a particular service provider.</span></span> <span data-ttu-id="a1a93-106">您可以通过调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问此表。</span><span class="sxs-lookup"><span data-stu-id="a1a93-106">You can access this table by calling [IMAPISession::GetStatusTable](imapisession-getstatustable.md).</span></span>
  
<span data-ttu-id="a1a93-107">状态表中的各行代表由 MAPI 或服务提供商实现状态对象。</span><span class="sxs-lookup"><span data-stu-id="a1a93-107">Each row in the status table represents a status object implemented by MAPI or a service provider.</span></span> <span data-ttu-id="a1a93-108">您可以使用状态对象显示的提供程序的配置属性表中，更改提供程序的密码，来上载或下载的邮件，以及与特定的传输提供程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="a1a93-108">You can use a status object to display a provider's configuration property sheet, to change a provider password, to upload or download messages, and to communicate with a particular transport provider.</span></span> 
  
<span data-ttu-id="a1a93-109">有两种方法访问状态对象：</span><span class="sxs-lookup"><span data-stu-id="a1a93-109">There are two ways to access a status object:</span></span>
  
- <span data-ttu-id="a1a93-110">通过状态表</span><span class="sxs-lookup"><span data-stu-id="a1a93-110">Through the status table</span></span>
    
- <span data-ttu-id="a1a93-111">通过登录对象的**OpenStatusEntry**方法</span><span class="sxs-lookup"><span data-stu-id="a1a93-111">Through a logon object's **OpenStatusEntry** method</span></span> 
    
<span data-ttu-id="a1a93-112">由于登录对象是对客户端不可用，您必须使用状态表访问状态对象。</span><span class="sxs-lookup"><span data-stu-id="a1a93-112">Because logon objects are unavailable to clients, you must use the status table to access status objects.</span></span> <span data-ttu-id="a1a93-113">间接，打开状态对象和指向其**IMAPIStatus**实现的指针返回之前，需要几个呼叫状态表方法。</span><span class="sxs-lookup"><span data-stu-id="a1a93-113">The status table approach is indirect, requiring a few calls before the status object is opened and a pointer to its **IMAPIStatus** implementation returned.</span></span> 
  
 <span data-ttu-id="a1a93-114">**使用状态表打开状态对象**</span><span class="sxs-lookup"><span data-stu-id="a1a93-114">**To use the status table to open a status object**</span></span>
  
1. <span data-ttu-id="a1a93-115">调用**IMAPIStatus::GetStatusTable**检索[IMAPITable](imapitableiunknown.md)指针。</span><span class="sxs-lookup"><span data-stu-id="a1a93-115">Call **IMAPIStatus::GetStatusTable** to retrieve an [IMAPITable](imapitableiunknown.md) pointer.</span></span> 
    
2. <span data-ttu-id="a1a93-116">呼叫状态表的[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 和**PR_DISPLAY_NAME** ([列PidTagDisplayName](pidtagdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="a1a93-116">Call the status table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)), and **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="a1a93-117">限制对特定状态对象表视图。</span><span class="sxs-lookup"><span data-stu-id="a1a93-117">Limit the table view to a particular status object.</span></span> <span data-ttu-id="a1a93-118">对于 MAPI 实现，客户端可以定义使用**PR_RESOURCE_TYPE**属性限制。</span><span class="sxs-lookup"><span data-stu-id="a1a93-118">For MAPI implementations, a client can define a property restriction using **PR_RESOURCE_TYPE**.</span></span> <span data-ttu-id="a1a93-119">服务提供程序实现的客户端可以限制在**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))，提供程序的名称或**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))，提供程序 DLL 的名称文件。</span><span class="sxs-lookup"><span data-stu-id="a1a93-119">For service provider implementations, a client can restrict on **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)), the name of the provider, or on **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)), the name of the provider DLL file.</span></span>
    
4. <span data-ttu-id="a1a93-120">调用[IMAPITable::Restrict](imapitable-restrict.md)设置限制。</span><span class="sxs-lookup"><span data-stu-id="a1a93-120">Call [IMAPITable::Restrict](imapitable-restrict.md) to set the restriction.</span></span> 
    
5. <span data-ttu-id="a1a93-121">呼叫[HrQueryAllRows](hrqueryallrows.md)，传递[SPropertyRestriction](spropertyrestriction.md)结构中，若要检索的行代表提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="a1a93-121">Call [HrQueryAllRows](hrqueryallrows.md), passing in the [SPropertyRestriction](spropertyrestriction.md) structure, to retrieve the row that represents the status of the provider.</span></span> 
    
6. <span data-ttu-id="a1a93-122">调用[IMAPISession::OpenEntry](imapisession-openentry.md)，指定状态表行中的项标识符来打开状态对象和检索**IMAPIStatus**指针。</span><span class="sxs-lookup"><span data-stu-id="a1a93-122">Call [IMAPISession::OpenEntry](imapisession-openentry.md), specifying the entry identifier from the status table row, to open the status object and retrieve an **IMAPIStatus** pointer.</span></span> 
    
<span data-ttu-id="a1a93-123">若要显示属性表，请为目标提供程序调用状态对象的[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a1a93-123">To display a property sheet, call the status object's [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method for the target provider.</span></span> <span data-ttu-id="a1a93-124">**留待**显示属性表查看并在某些情况下，更改提供程序的配置属性。</span><span class="sxs-lookup"><span data-stu-id="a1a93-124">**SettingsDialog** displays a property sheet for viewing and in some cases, changing the configuration properties of a provider.</span></span> 
  
<span data-ttu-id="a1a93-125">要与传输提供程序通信，调用其状态对象[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a1a93-125">To communicate with a transport provider, call its status object's [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="a1a93-126">**ValidateState**可以重新配置的传输提供程序、 禁止显示用户界面，提供程序和控制会话涉及下载邮件头从远程服务器，具体取决于您传入的标志。</span><span class="sxs-lookup"><span data-stu-id="a1a93-126">**ValidateState** can reconfigure a transport provider, prevent the provider from displaying a user interface, and control a session that involves downloading message headers from a remote server, depending on the flags that you pass in.</span></span> <span data-ttu-id="a1a93-127">例如，如果要取消的远程标头下载，传递给**ValidateState**的 ABORT_XP_HEADER_OPERATION 标志。</span><span class="sxs-lookup"><span data-stu-id="a1a93-127">For example, to cancel the downloading of remote headers, pass the ABORT_XP_HEADER_OPERATION flag to **ValidateState**.</span></span> <span data-ttu-id="a1a93-128">若要连接或断开与远程服务器的连接，请传递 FORCE_XP_CONNECT 或 FORCE_XP_DISCONNECT。</span><span class="sxs-lookup"><span data-stu-id="a1a93-128">To connect or disconnect from the remote server, pass FORCE_XP_CONNECT or FORCE_XP_DISCONNECT.</span></span> <span data-ttu-id="a1a93-129">若要重新配置提供程序，请传递 CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="a1a93-129">To reconfigure the provider, pass CONFIG_CHANGED.</span></span> 
  
<span data-ttu-id="a1a93-130">实现发送或接收的消息的需求的客户端调用传输提供程序或 MAPI 后台处理程序的[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a1a93-130">Clients that implement sending or receiving of messages on demand call either a transport provider's or the MAPI spooler's [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method.</span></span> <span data-ttu-id="a1a93-131">您可以传递到方法的三个标志： FLUSH_UPLOAD、 FLUSH_DOWNLOAD 和 FLUSH_FORCE。</span><span class="sxs-lookup"><span data-stu-id="a1a93-131">You can pass three flags into the method: FLUSH_UPLOAD, FLUSH_DOWNLOAD, and FLUSH_FORCE.</span></span> <span data-ttu-id="a1a93-132">FLUSH_UPLOAD 指示提供程序或 MAPI 后台处理程序发送时 FLUSH_DOWNLOAD 指示提供程序输出队列中等待的任何邮件或 MAPI 后台处理程序以接收任何传入消息。</span><span class="sxs-lookup"><span data-stu-id="a1a93-132">FLUSH_UPLOAD instructs the provider or the MAPI spooler to send any messages waiting in the output queue while FLUSH_DOWNLOAD instructs the provider or the MAPI spooler to receive any incoming messages.</span></span> <span data-ttu-id="a1a93-133">若要使该状态对象以执行 timing 无论刷新，可以与其他标志任一设置 FLUSH_FORCE。</span><span class="sxs-lookup"><span data-stu-id="a1a93-133">FLUSH_FORCE can be set with either of the other flags to cause the status object to perform the flush regardless of the timing.</span></span> 
  
<span data-ttu-id="a1a93-134">不希望能够调用**留待**或[ChangePassword](imapistatus-changepassword.md)上的任何 MAPI 子系统、 MAPI 后台处理程序或地址簿状态对象。</span><span class="sxs-lookup"><span data-stu-id="a1a93-134">Do not expect to be able to call **SettingsDialog** or [ChangePassword](imapistatus-changepassword.md) on any of the MAPI subsystem, MAPI spooler, or address book status objects.</span></span> <span data-ttu-id="a1a93-135">子系统和地址簿状态对象仅支持**ValidateState**;MAPI 后台处理程序状态对象支持**FlushQueues**除了**ValidateState**。</span><span class="sxs-lookup"><span data-stu-id="a1a93-135">Both the subsystem and address book status objects only support **ValidateState**; the MAPI spooler status object supports **FlushQueues** in addition to **ValidateState**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1a93-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1a93-136">See also</span></span>



[<span data-ttu-id="a1a93-137">状态表</span><span class="sxs-lookup"><span data-stu-id="a1a93-137">Status Tables</span></span>](status-tables.md)
  
[<span data-ttu-id="a1a93-138">MAPI 状态对象</span><span class="sxs-lookup"><span data-stu-id="a1a93-138">MAPI Status Objects</span></span>](mapi-status-objects.md)

