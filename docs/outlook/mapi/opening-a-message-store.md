---
title: 打开的消息存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 43b23fd7-999a-42c0-8f4d-47f5de266bdb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4bab31dbcd1f7139980d7df5559c1ee52a6f167f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563644"
---
# <a name="opening-a-message-store"></a><span data-ttu-id="ebbcd-103">打开的消息存储</span><span class="sxs-lookup"><span data-stu-id="ebbcd-103">Opening a message store</span></span>

<span data-ttu-id="ebbcd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ebbcd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ebbcd-105">配置文件中，根据客户端将需要在典型的会话过程中打开一个或多个邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-105">Depending on the profile, a client will need to open one or more message stores during a typical session.</span></span> <span data-ttu-id="ebbcd-106">打开的消息存储是指访问一个指向其[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)实现。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-106">Opening a message store means gaining access to a pointer to its [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) implementation.</span></span> <span data-ttu-id="ebbcd-107">**IMsgStore**接口提供通知，使文件夹分配，以及访问文件夹和邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-107">The **IMsgStore** interface provides methods for notification, making folder assignments, and accessing folders and messages.</span></span> 
  
<span data-ttu-id="ebbcd-108">客户端打开消息存储在登录和时要修改配置文件。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-108">Clients open message stores at logon and when a profile is being modified.</span></span> <span data-ttu-id="ebbcd-109">如果您的客户端允许用户在活动会话过程中添加到配置文件的消息存储，您可以立即打开它们或直到下一个会话中忽略。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-109">If your client allows users to add message stores to the profile during an active session, you can either open them immediately or ignore them until the next session.</span></span> <span data-ttu-id="ebbcd-110">通过注册消息存储表上的通知，通知您的新消息存储的可用性。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-110">By registering for notifications on the message store table, you will be alerted to the availability of a new message store.</span></span>
  
<span data-ttu-id="ebbcd-111">若要打开的消息存储，您必须具有其可用的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-111">To open a message store, you must have its entry identifier available.</span></span> <span data-ttu-id="ebbcd-112">大多数客户端访问他们希望通过消息存储表打开的消息存储的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-112">Most clients access the entry identifiers for the message stores they wish to open through the message store table.</span></span> <span data-ttu-id="ebbcd-113">但是，某些消息存储文档其条目标识符，从而启用客户端，以绕过邮件存储表，构造所需的项标识符的格式。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-113">However, some message stores document the format of their entry identifiers, thereby enabling clients to bypass the message store table and construct the necessary entry identifier.</span></span> <span data-ttu-id="ebbcd-114">它们可以直接向[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)传递此条目标识符并 MAPI 自动创建配置文件一节提供程序不关联任何消息服务。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-114">They can pass this entry identifier directly to [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) and MAPI automatically creates a profile section for the provider without associating it with any message service.</span></span> 
  
## <a name="retrieve-an-entry-identifier-from-the-message-store-table"></a><span data-ttu-id="ebbcd-115">消息存储表中检索的项标识符</span><span class="sxs-lookup"><span data-stu-id="ebbcd-115">Retrieve an entry identifier from the message store table</span></span>
  
1. <span data-ttu-id="ebbcd-116">调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)打开消息存储表。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-116">Call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to open the message store table.</span></span> 
    
2. <span data-ttu-id="ebbcd-117">呼叫**IMAPITable::SetColumns**限制到小型列集，其中包括以下各列的表：</span><span class="sxs-lookup"><span data-stu-id="ebbcd-117">Call **IMAPITable::SetColumns** to limit the table to a small column set that includes the following columns:</span></span> 
    
   - <span data-ttu-id="ebbcd-118">**PR_PROVIDER_DISPLAY**或**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-118">**PR_PROVIDER_DISPLAY** or **PR_DISPLAY_NAME**</span></span>
   - <span data-ttu-id="ebbcd-119">**PR_ENTRYID**属性</span><span class="sxs-lookup"><span data-stu-id="ebbcd-119">**PR_ENTRYID** properties</span></span> 
   - <span data-ttu-id="ebbcd-120">**PR_MDB_PROVIDER**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-120">**PR_MDB_PROVIDER**</span></span>
   - <span data-ttu-id="ebbcd-121">**PR_RESOURCE_FLAGS**</span><span class="sxs-lookup"><span data-stu-id="ebbcd-121">**PR_RESOURCE_FLAGS**</span></span>
    
3. <span data-ttu-id="ebbcd-122">构建筛选出的行值，该值代表要打开的消息存储限制。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-122">Build a restriction to filter out the row that represents the message store to be opened.</span></span> <span data-ttu-id="ebbcd-123">有关查找默认的邮件存储的详细信息，请参阅[打开默认邮件存储区](opening-the-default-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-123">For more information about looking for the default message store, see [Opening the Default Message Store](opening-the-default-message-store.md).</span></span> <span data-ttu-id="ebbcd-124">若要查找按名称的消息存储，应用任何属性存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="ebbcd-124">To look for a message store by name, apply any of the following property restrictions:</span></span>
    
   - <span data-ttu-id="ebbcd-125">为此类型的消息存储的常规名称匹配**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-125">Match **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) with the general name for this type of message store.</span></span> <span data-ttu-id="ebbcd-126">例如，PR_PROVIDER_DISPLAY 可能将设置为"个人文件夹"。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-126">For example, PR_PROVIDER_DISPLAY might be set to "Personal Folders".</span></span>
    
   - <span data-ttu-id="ebbcd-127">此类型的消息存储匹配**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 与特定**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-127">Match **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) with the specific **MAPIUID** for this type of message store.</span></span> 
    
   - <span data-ttu-id="ebbcd-128">为此特定邮件存储的名称匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-128">Match **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name for this particular message store.</span></span> <span data-ttu-id="ebbcd-129">例如， **PR_DISPLAY_NAME**可能会设置为"会计年度 2010年我邮件。"</span><span class="sxs-lookup"><span data-stu-id="ebbcd-129">For example, **PR_DISPLAY_NAME** might be set to "My Messages for Fiscal Year 2010."</span></span> 
    
4. <span data-ttu-id="ebbcd-130">调用[HrQueryAllRows](hrqueryallrows.md)消息存储表中检索相应行。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-130">Call [HrQueryAllRows](hrqueryallrows.md) to retrieve the appropriate row from the message store table.</span></span> <span data-ttu-id="ebbcd-131">将**aRow**成员_pprows_参数指向的行集的属性值数组中包含行中的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-131">The entry identifier for the row will be included in the property value array for the **aRow** member of the row set pointed to by the  _pprows_ parameter.</span></span> 
    
5. <span data-ttu-id="ebbcd-132">调用[FreeProws](freeprows.md)以释放所指的_pprows_行集。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-132">Call [FreeProws](freeprows.md) to free the row set pointed to by  _pprows_.</span></span>
    
6. <span data-ttu-id="ebbcd-133">发布消息存储表通过调用其**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-133">Release the message store table by calling its **IUnknown::Release** method.</span></span> 
    
<span data-ttu-id="ebbcd-134">如果您已创建要在打开的消息存储的自定义项标识符，调用[WrapStoreEntryID](wrapstoreentryid.md)函数，以将其转换为标准的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-134">If you have created a custom entry identifier for the message store to be opened, call the [WrapStoreEntryID](wrapstoreentryid.md) function to convert it to a standard entry identifier.</span></span> 
  
<span data-ttu-id="ebbcd-135">消息存储的项标识符后，呼叫以将其打开的以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="ebbcd-135">After you have a message store's entry identifier, call one of the following methods to open it:</span></span>
  
- [<span data-ttu-id="ebbcd-136">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="ebbcd-136">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
- [<span data-ttu-id="ebbcd-137">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="ebbcd-137">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
    
<span data-ttu-id="ebbcd-138">如果您需要指定多种消息存储的特殊选项，请调用**OpenMsgStore** 。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-138">Call **OpenMsgStore** if you need to specify a variety of special options for the message store.</span></span> <span data-ttu-id="ebbcd-139">**OpenMsgStore**可以取消显示的对话框，请确定的消息存储临时作为或非邮件存储区中，设置访问级别，并推迟错误。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-139">**OpenMsgStore** allows you to suppress the display of dialog boxes, identify the message store as temporary or as a nonmessaging store, set access levels, and to defer errors.</span></span> <span data-ttu-id="ebbcd-140">**OpenEntry**允许您仅可以设置访问级别，并推迟错误。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-140">**OpenEntry** allows you only to set access levels and defer errors.</span></span> 
  
<span data-ttu-id="ebbcd-141">设置 MDB_NO_MAIL 标志指示为 MAPI 消息存储将不使用发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-141">Setting the MDB_NO_MAIL flag indicates to MAPI that the message store will not be used for sending or receiving messages.</span></span> <span data-ttu-id="ebbcd-142">MAPI 不会存在此消息存储有关通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-142">MAPI does not inform the MAPI spooler about the existence of this message store.</span></span> <span data-ttu-id="ebbcd-143">MDB_TEMPORARY 标志指定邮件存储为临时，这意味着它不能用于存储永久性信息。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-143">The MDB_TEMPORARY flag designates a message store as temporary, implying that it cannot be used to store permanent information.</span></span> <span data-ttu-id="ebbcd-144">消息存储表中不显示临时邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ebbcd-144">Temporary message stores do not appear in the message store table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ebbcd-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebbcd-145">See also</span></span>

- [<span data-ttu-id="ebbcd-146">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="ebbcd-146">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)

