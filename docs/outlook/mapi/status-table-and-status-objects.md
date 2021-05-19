---
title: 状态表和状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 203765c1-4b08-4032-a5bf-18f3e752a899
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3eb190069b43ea1960c3b6edf30a9e0b782d2c41
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425174"
---
# <a name="status-table-and-status-objects"></a><span data-ttu-id="e6b5b-103">状态表和状态对象</span><span class="sxs-lookup"><span data-stu-id="e6b5b-103">Status Table and Status Objects</span></span>

  
  
<span data-ttu-id="e6b5b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6b5b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6b5b-105">MAPI 提供了一个表，该表包含有关 MAPI 子系统、MAPI 后台处理程序、通讯簿或特定服务提供商的状态的信息。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-105">MAPI provides a table with information about the status of the MAPI subsystem, MAPI spooler, address book, or a particular service provider.</span></span> <span data-ttu-id="e6b5b-106">可以通过调用 [IMAPISession：：GetStatusTable 访问此表](imapisession-getstatustable.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-106">You can access this table by calling [IMAPISession::GetStatusTable](imapisession-getstatustable.md).</span></span>
  
<span data-ttu-id="e6b5b-107">状态表中的每一行都代表 MAPI 或服务提供商实现的状态对象。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-107">Each row in the status table represents a status object implemented by MAPI or a service provider.</span></span> <span data-ttu-id="e6b5b-108">可以使用 status 对象显示提供程序的配置属性表、更改提供程序密码、上载或下载邮件，以及与特定传输提供程序通信。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-108">You can use a status object to display a provider's configuration property sheet, to change a provider password, to upload or download messages, and to communicate with a particular transport provider.</span></span> 
  
<span data-ttu-id="e6b5b-109">有两种方法可以访问状态对象：</span><span class="sxs-lookup"><span data-stu-id="e6b5b-109">There are two ways to access a status object:</span></span>
  
- <span data-ttu-id="e6b5b-110">通过状态表</span><span class="sxs-lookup"><span data-stu-id="e6b5b-110">Through the status table</span></span>
    
- <span data-ttu-id="e6b5b-111">通过登录对象的 **OpenStatusEntry** 方法</span><span class="sxs-lookup"><span data-stu-id="e6b5b-111">Through a logon object's **OpenStatusEntry** method</span></span> 
    
<span data-ttu-id="e6b5b-112">由于客户端无法使用登录对象，因此必须使用状态表访问状态对象。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-112">Because logon objects are unavailable to clients, you must use the status table to access status objects.</span></span> <span data-ttu-id="e6b5b-113">状态表方法是间接的，在打开状态对象之前需要调用几个，并返回指向 **其 IMAPIStatus 实现** 指针。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-113">The status table approach is indirect, requiring a few calls before the status object is opened and a pointer to its **IMAPIStatus** implementation returned.</span></span> 
  
 <span data-ttu-id="e6b5b-114">**使用状态表打开状态对象**</span><span class="sxs-lookup"><span data-stu-id="e6b5b-114">**To use the status table to open a status object**</span></span>
  
1. <span data-ttu-id="e6b5b-115">调用 **IMAPIStatus：：GetStatusTable** 以检索 [IMAPITable](imapitableiunknown.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-115">Call **IMAPIStatus::GetStatusTable** to retrieve an [IMAPITable](imapitableiunknown.md) pointer.</span></span> 
    
2. <span data-ttu-id="e6b5b-116">调用状态表 [的 IMAPITable：：SetColumns](imapitable-setcolumns.md)方法，将列集限制为 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 、PR_RESOURCE_TYPE ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 和 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="e6b5b-116">Call the status table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)), and **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="e6b5b-117">将表视图限制为特定的状态对象。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-117">Limit the table view to a particular status object.</span></span> <span data-ttu-id="e6b5b-118">对于 MAPI 实现，客户端可以使用 PR_RESOURCE_TYPE 定义 **属性限制**。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-118">For MAPI implementations, a client can define a property restriction using **PR_RESOURCE_TYPE**.</span></span> <span data-ttu-id="e6b5b-119">对于服务提供商实现，客户端可以限制为 **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 、提供程序的名称或 **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) （提供程序 DLL 文件的名称）。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-119">For service provider implementations, a client can restrict on **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)), the name of the provider, or on **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)), the name of the provider DLL file.</span></span>
    
4. <span data-ttu-id="e6b5b-120">调用 [IMAPITable：：Restrict](imapitable-restrict.md) 以设置限制。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-120">Call [IMAPITable::Restrict](imapitable-restrict.md) to set the restriction.</span></span> 
    
5. <span data-ttu-id="e6b5b-121">调用 [HrQueryAllRows（](hrqueryallrows.md)传递 [SPropertyRestriction](spropertyrestriction.md) 结构）以检索表示提供程序状态的行。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-121">Call [HrQueryAllRows](hrqueryallrows.md), passing in the [SPropertyRestriction](spropertyrestriction.md) structure, to retrieve the row that represents the status of the provider.</span></span> 
    
6. <span data-ttu-id="e6b5b-122">调用 [IMAPISession：：OpenEntry，](imapisession-openentry.md)指定状态表行中的条目标识符，以打开状态对象并检索 **IMAPIStatus** 指针。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-122">Call [IMAPISession::OpenEntry](imapisession-openentry.md), specifying the entry identifier from the status table row, to open the status object and retrieve an **IMAPIStatus** pointer.</span></span> 
    
<span data-ttu-id="e6b5b-123">若要显示属性表，请为目标提供程序调用状态对象的 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-123">To display a property sheet, call the status object's [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method for the target provider.</span></span> <span data-ttu-id="e6b5b-124">**SettingsDialog** 显示属性表视图，在某些情况下，更改提供程序的配置属性。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-124">**SettingsDialog** displays a property sheet for viewing and in some cases, changing the configuration properties of a provider.</span></span> 
  
<span data-ttu-id="e6b5b-125">若要与传输提供程序通信，请调用其状态对象的 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-125">To communicate with a transport provider, call its status object's [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="e6b5b-126">**ValidateState** 可以重新配置传输提供程序，阻止提供程序显示用户界面，并控制涉及从远程服务器下载邮件头的会话，具体取决于您传递的标志。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-126">**ValidateState** can reconfigure a transport provider, prevent the provider from displaying a user interface, and control a session that involves downloading message headers from a remote server, depending on the flags that you pass in.</span></span> <span data-ttu-id="e6b5b-127">例如，若要取消下载远程邮件头，将 ABORT_XP_HEADER_OPERATION标志传递到 **ValidateState**。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-127">For example, to cancel the downloading of remote headers, pass the ABORT_XP_HEADER_OPERATION flag to **ValidateState**.</span></span> <span data-ttu-id="e6b5b-128">若要连接或断开与远程服务器的连接，请FORCE_XP_CONNECT或FORCE_XP_DISCONNECT。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-128">To connect or disconnect from the remote server, pass FORCE_XP_CONNECT or FORCE_XP_DISCONNECT.</span></span> <span data-ttu-id="e6b5b-129">若要重新配置提供程序，请传递CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-129">To reconfigure the provider, pass CONFIG_CHANGED.</span></span> 
  
<span data-ttu-id="e6b5b-130">实现按需发送或接收邮件的客户端调用传输提供程序或 MAPI 后台处理程序的 [IMAPIStatus：：FlushQueues](imapistatus-flushqueues.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-130">Clients that implement sending or receiving of messages on demand call either a transport provider's or the MAPI spooler's [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method.</span></span> <span data-ttu-id="e6b5b-131">可以将三个标志传递到 方法中：FLUSH_UPLOAD、FLUSH_DOWNLOAD 和 FLUSH_FORCE。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-131">You can pass three flags into the method: FLUSH_UPLOAD, FLUSH_DOWNLOAD, and FLUSH_FORCE.</span></span> <span data-ttu-id="e6b5b-132">FLUSH_UPLOAD指示提供程序或 MAPI 后台处理程序发送输出队列中等待的任何邮件，而 FLUSH_DOWNLOAD 指示提供程序或 MAPI 后台处理程序接收任何传入邮件。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-132">FLUSH_UPLOAD instructs the provider or the MAPI spooler to send any messages waiting in the output queue while FLUSH_DOWNLOAD instructs the provider or the MAPI spooler to receive any incoming messages.</span></span> <span data-ttu-id="e6b5b-133">FLUSH_FORCE可以使用其他任一标志进行设置，使状态对象执行刷新，而不考虑计时。</span><span class="sxs-lookup"><span data-stu-id="e6b5b-133">FLUSH_FORCE can be set with either of the other flags to cause the status object to perform the flush regardless of the timing.</span></span> 
  
<span data-ttu-id="e6b5b-134">不要期望能够在任何 MAPI 子系统、MAPI 后台处理程序或通讯簿状态对象上调用 **SettingsDialog** 或 [ChangePassword。](imapistatus-changepassword.md)</span><span class="sxs-lookup"><span data-stu-id="e6b5b-134">Do not expect to be able to call **SettingsDialog** or [ChangePassword](imapistatus-changepassword.md) on any of the MAPI subsystem, MAPI spooler, or address book status objects.</span></span> <span data-ttu-id="e6b5b-135">子系统和通讯簿状态对象都仅支持 **ValidateState**;MAPI 后台处理程序状态对象除了支持 ValidateState 之外，还支持 **FlushQueues。** </span><span class="sxs-lookup"><span data-stu-id="e6b5b-135">Both the subsystem and address book status objects only support **ValidateState**; the MAPI spooler status object supports **FlushQueues** in addition to **ValidateState**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e6b5b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6b5b-136">See also</span></span>



[<span data-ttu-id="e6b5b-137">状态表</span><span class="sxs-lookup"><span data-stu-id="e6b5b-137">Status Tables</span></span>](status-tables.md)
  
[<span data-ttu-id="e6b5b-138">MAPI 状态对象</span><span class="sxs-lookup"><span data-stu-id="e6b5b-138">MAPI Status Objects</span></span>](mapi-status-objects.md)

