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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336328"
---
# <a name="status-table-and-status-objects"></a><span data-ttu-id="35b54-103">状态表和状态对象</span><span class="sxs-lookup"><span data-stu-id="35b54-103">Status Table and Status Objects</span></span>

  
  
<span data-ttu-id="35b54-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="35b54-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="35b54-105">mapi 提供了一个表, 其中包含有关 mapi 子系统、mapi 后台处理程序、通讯簿或特定服务提供商状态的信息。</span><span class="sxs-lookup"><span data-stu-id="35b54-105">MAPI provides a table with information about the status of the MAPI subsystem, MAPI spooler, address book, or a particular service provider.</span></span> <span data-ttu-id="35b54-106">您可以通过调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)来访问此表。</span><span class="sxs-lookup"><span data-stu-id="35b54-106">You can access this table by calling [IMAPISession::GetStatusTable](imapisession-getstatustable.md).</span></span>
  
<span data-ttu-id="35b54-107">status 表中的每一行都代表由 MAPI 或服务提供商实现的状态对象。</span><span class="sxs-lookup"><span data-stu-id="35b54-107">Each row in the status table represents a status object implemented by MAPI or a service provider.</span></span> <span data-ttu-id="35b54-108">您可以使用 status 对象显示提供程序的配置属性表、更改提供程序密码、上载或下载邮件以及与特定的传输提供程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="35b54-108">You can use a status object to display a provider's configuration property sheet, to change a provider password, to upload or download messages, and to communicate with a particular transport provider.</span></span> 
  
<span data-ttu-id="35b54-109">有两种访问状态对象的方法:</span><span class="sxs-lookup"><span data-stu-id="35b54-109">There are two ways to access a status object:</span></span>
  
- <span data-ttu-id="35b54-110">通过状态表</span><span class="sxs-lookup"><span data-stu-id="35b54-110">Through the status table</span></span>
    
- <span data-ttu-id="35b54-111">通过登录对象的**OpenStatusEntry**方法</span><span class="sxs-lookup"><span data-stu-id="35b54-111">Through a logon object's **OpenStatusEntry** method</span></span> 
    
<span data-ttu-id="35b54-112">由于客户端无法使用登录对象, 因此必须使用状态表访问 status 对象。</span><span class="sxs-lookup"><span data-stu-id="35b54-112">Because logon objects are unavailable to clients, you must use the status table to access status objects.</span></span> <span data-ttu-id="35b54-113">状态表方法是间接的, 在打开 status 对象和返回指向其**IMAPIStatus**实现的指针之前, 需要进行几次调用。</span><span class="sxs-lookup"><span data-stu-id="35b54-113">The status table approach is indirect, requiring a few calls before the status object is opened and a pointer to its **IMAPIStatus** implementation returned.</span></span> 
  
 <span data-ttu-id="35b54-114">**使用状态表打开状态对象**</span><span class="sxs-lookup"><span data-stu-id="35b54-114">**To use the status table to open a status object**</span></span>
  
1. <span data-ttu-id="35b54-115">调用**IMAPIStatus:: GetStatusTable**以检索[IMAPITable](imapitableiunknown.md)指针。</span><span class="sxs-lookup"><span data-stu-id="35b54-115">Call **IMAPIStatus::GetStatusTable** to retrieve an [IMAPITable](imapitableiunknown.md) pointer.</span></span> 
    
2. <span data-ttu-id="35b54-116">调用状态表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法来限制将列设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 和**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="35b54-116">Call the status table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)), and **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="35b54-117">将表视图限制为特定的状态对象。</span><span class="sxs-lookup"><span data-stu-id="35b54-117">Limit the table view to a particular status object.</span></span> <span data-ttu-id="35b54-118">对于 MAPI 实现, 客户端可以使用**PR_RESOURCE_TYPE**定义属性限制。</span><span class="sxs-lookup"><span data-stu-id="35b54-118">For MAPI implementations, a client can define a property restriction using **PR_RESOURCE_TYPE**.</span></span> <span data-ttu-id="35b54-119">对于服务提供程序实现, 客户端可以限制**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))、提供程序的名称或**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 上的提供程序 DLL 的名称。文本文件.</span><span class="sxs-lookup"><span data-stu-id="35b54-119">For service provider implementations, a client can restrict on **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)), the name of the provider, or on **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)), the name of the provider DLL file.</span></span>
    
4. <span data-ttu-id="35b54-120">调用[IMAPITable:: Restrict](imapitable-restrict.md)以设置限制。</span><span class="sxs-lookup"><span data-stu-id="35b54-120">Call [IMAPITable::Restrict](imapitable-restrict.md) to set the restriction.</span></span> 
    
5. <span data-ttu-id="35b54-121">调用[HrQueryAllRows](hrqueryallrows.md), 在[SPropertyRestriction](spropertyrestriction.md)结构中传递, 以检索表示提供程序状态的行。</span><span class="sxs-lookup"><span data-stu-id="35b54-121">Call [HrQueryAllRows](hrqueryallrows.md), passing in the [SPropertyRestriction](spropertyrestriction.md) structure, to retrieve the row that represents the status of the provider.</span></span> 
    
6. <span data-ttu-id="35b54-122">调用[IMAPISession:: OpenEntry](imapisession-openentry.md), 从状态表行指定条目标识符, 以打开 status 对象并检索**IMAPIStatus**指针。</span><span class="sxs-lookup"><span data-stu-id="35b54-122">Call [IMAPISession::OpenEntry](imapisession-openentry.md), specifying the entry identifier from the status table row, to open the status object and retrieve an **IMAPIStatus** pointer.</span></span> 
    
<span data-ttu-id="35b54-123">若要显示属性表, 请调用目标提供程序的 status 对象的[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法。</span><span class="sxs-lookup"><span data-stu-id="35b54-123">To display a property sheet, call the status object's [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method for the target provider.</span></span> <span data-ttu-id="35b54-124">**SettingsDialog**显示用于查看的属性表, 在某些情况下, 更改提供程序的配置属性。</span><span class="sxs-lookup"><span data-stu-id="35b54-124">**SettingsDialog** displays a property sheet for viewing and in some cases, changing the configuration properties of a provider.</span></span> 
  
<span data-ttu-id="35b54-125">若要与传输提供程序通信, 请调用其 status 对象的[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法。</span><span class="sxs-lookup"><span data-stu-id="35b54-125">To communicate with a transport provider, call its status object's [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> <span data-ttu-id="35b54-126">**ValidateState**可以重新配置传输提供程序, 阻止提供程序显示用户界面, 并控制包含从远程服务器下载邮件头的会话, 具体取决于您传入的标志。</span><span class="sxs-lookup"><span data-stu-id="35b54-126">**ValidateState** can reconfigure a transport provider, prevent the provider from displaying a user interface, and control a session that involves downloading message headers from a remote server, depending on the flags that you pass in.</span></span> <span data-ttu-id="35b54-127">例如, 若要取消远程头的下载, 请将 ABORT_XP_HEADER_OPERATION 标志传递给**ValidateState**。</span><span class="sxs-lookup"><span data-stu-id="35b54-127">For example, to cancel the downloading of remote headers, pass the ABORT_XP_HEADER_OPERATION flag to **ValidateState**.</span></span> <span data-ttu-id="35b54-128">若要连接或断开与远程服务器的连接, 请传递 FORCE_XP_CONNECT 或 FORCE_XP_DISCONNECT。</span><span class="sxs-lookup"><span data-stu-id="35b54-128">To connect or disconnect from the remote server, pass FORCE_XP_CONNECT or FORCE_XP_DISCONNECT.</span></span> <span data-ttu-id="35b54-129">若要重新配置提供程序, 请传递 CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="35b54-129">To reconfigure the provider, pass CONFIG_CHANGED.</span></span> 
  
<span data-ttu-id="35b54-130">按需调用邮件发送或接收邮件的客户端传输提供程序或 MAPI 后台处理程序的[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法。</span><span class="sxs-lookup"><span data-stu-id="35b54-130">Clients that implement sending or receiving of messages on demand call either a transport provider's or the MAPI spooler's [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method.</span></span> <span data-ttu-id="35b54-131">您可以将三个标志传递到方法中: FLUSH_UPLOAD、FLUSH_DOWNLOAD 和 FLUSH_FORCE。</span><span class="sxs-lookup"><span data-stu-id="35b54-131">You can pass three flags into the method: FLUSH_UPLOAD, FLUSH_DOWNLOAD, and FLUSH_FORCE.</span></span> <span data-ttu-id="35b54-132">FLUSH_UPLOAD 指示提供程序或 mapi 后台处理程序发送在输出队列中等待的任何邮件, 同时 FLUSH_DOWNLOAD 指示提供程序或 mapi 后台处理程序接收任何传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="35b54-132">FLUSH_UPLOAD instructs the provider or the MAPI spooler to send any messages waiting in the output queue while FLUSH_DOWNLOAD instructs the provider or the MAPI spooler to receive any incoming messages.</span></span> <span data-ttu-id="35b54-133">可以使用任何其他标志设置 FLUSH_FORCE, 以使 status 对象执行刷新, 而不考虑计时。</span><span class="sxs-lookup"><span data-stu-id="35b54-133">FLUSH_FORCE can be set with either of the other flags to cause the status object to perform the flush regardless of the timing.</span></span> 
  
<span data-ttu-id="35b54-134">不希望能够在任何 mapi 子系统、mapi 后台处理程序或通讯簿状态对象上调用**SettingsDialog**或[ChangePassword](imapistatus-changepassword.md) 。</span><span class="sxs-lookup"><span data-stu-id="35b54-134">Do not expect to be able to call **SettingsDialog** or [ChangePassword](imapistatus-changepassword.md) on any of the MAPI subsystem, MAPI spooler, or address book status objects.</span></span> <span data-ttu-id="35b54-135">"子系统" 和 "通讯簿" 状态对象仅支持**ValidateState**;MAPI 后台处理程序状态对象支持**FlushQueues**以及**ValidateState**。</span><span class="sxs-lookup"><span data-stu-id="35b54-135">Both the subsystem and address book status objects only support **ValidateState**; the MAPI spooler status object supports **FlushQueues** in addition to **ValidateState**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35b54-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35b54-136">See also</span></span>



[<span data-ttu-id="35b54-137">状态表</span><span class="sxs-lookup"><span data-stu-id="35b54-137">Status Tables</span></span>](status-tables.md)
  
[<span data-ttu-id="35b54-138">MAPI 状态对象</span><span class="sxs-lookup"><span data-stu-id="35b54-138">MAPI Status Objects</span></span>](mapi-status-objects.md)

