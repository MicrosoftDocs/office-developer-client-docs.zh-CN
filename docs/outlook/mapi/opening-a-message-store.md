---
title: 打开邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 43b23fd7-999a-42c0-8f4d-47f5de266bdb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 665c14b285db166e4f2a421d46e57f23e2f7ad52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432371"
---
# <a name="opening-a-message-store"></a><span data-ttu-id="70147-103">打开邮件存储</span><span class="sxs-lookup"><span data-stu-id="70147-103">Opening a message store</span></span>

<span data-ttu-id="70147-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70147-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70147-105">根据配置文件，客户端将需要在典型会话期间打开一个或多个邮件存储。</span><span class="sxs-lookup"><span data-stu-id="70147-105">Depending on the profile, a client will need to open one or more message stores during a typical session.</span></span> <span data-ttu-id="70147-106">打开消息存储意味着获取指向其 [IMsgStore： IMAPIProp](imsgstoreimapiprop.md) 实现指针的访问权限。</span><span class="sxs-lookup"><span data-stu-id="70147-106">Opening a message store means gaining access to a pointer to its [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) implementation.</span></span> <span data-ttu-id="70147-107">**IMsgStore** 接口提供用于通知、进行文件夹分配以及访问文件夹和邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="70147-107">The **IMsgStore** interface provides methods for notification, making folder assignments, and accessing folders and messages.</span></span> 
  
<span data-ttu-id="70147-108">客户端在登录时和修改配置文件时打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="70147-108">Clients open message stores at logon and when a profile is being modified.</span></span> <span data-ttu-id="70147-109">如果客户端允许用户在活动会话期间将邮件存储添加到配置文件，您可以立即打开它们，也可以忽略它们，直到下一个会话。</span><span class="sxs-lookup"><span data-stu-id="70147-109">If your client allows users to add message stores to the profile during an active session, you can either open them immediately or ignore them until the next session.</span></span> <span data-ttu-id="70147-110">通过注册邮件存储表上的通知，将提醒您新邮件存储的可用性。</span><span class="sxs-lookup"><span data-stu-id="70147-110">By registering for notifications on the message store table, you will be alerted to the availability of a new message store.</span></span>
  
<span data-ttu-id="70147-111">若要打开邮件存储，您必须具有其条目标识符可用。</span><span class="sxs-lookup"><span data-stu-id="70147-111">To open a message store, you must have its entry identifier available.</span></span> <span data-ttu-id="70147-112">大多数客户端访问要通过邮件存储表打开的邮件存储的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="70147-112">Most clients access the entry identifiers for the message stores they wish to open through the message store table.</span></span> <span data-ttu-id="70147-113">但是，某些邮件存储记录其条目标识符的格式，从而使客户端可以绕过邮件存储表并构造必要的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="70147-113">However, some message stores document the format of their entry identifiers, thereby enabling clients to bypass the message store table and construct the necessary entry identifier.</span></span> <span data-ttu-id="70147-114">他们可以将此条目标识符直接传递到 [IMAPISession：：OpenMsgStore，MAPI](imapisession-openmsgstore.md) 会自动为提供程序创建配置文件节，而不将其与任何邮件服务关联。</span><span class="sxs-lookup"><span data-stu-id="70147-114">They can pass this entry identifier directly to [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) and MAPI automatically creates a profile section for the provider without associating it with any message service.</span></span> 
  
## <a name="retrieve-an-entry-identifier-from-the-message-store-table"></a><span data-ttu-id="70147-115">从邮件存储表中检索条目标识符</span><span class="sxs-lookup"><span data-stu-id="70147-115">Retrieve an entry identifier from the message store table</span></span>
  
1. <span data-ttu-id="70147-116">调用 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 以打开消息存储表。</span><span class="sxs-lookup"><span data-stu-id="70147-116">Call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to open the message store table.</span></span> 
    
2. <span data-ttu-id="70147-117">调用 **IMAPITable：：SetColumns** 将表限制为包含以下列的小列集：</span><span class="sxs-lookup"><span data-stu-id="70147-117">Call **IMAPITable::SetColumns** to limit the table to a small column set that includes the following columns:</span></span> 
    
   - <span data-ttu-id="70147-118">**PR_PROVIDER_DISPLAY** 或 **PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="70147-118">**PR_PROVIDER_DISPLAY** or **PR_DISPLAY_NAME**</span></span>
   - <span data-ttu-id="70147-119">**PR_ENTRYID** 属性</span><span class="sxs-lookup"><span data-stu-id="70147-119">**PR_ENTRYID** properties</span></span> 
   - <span data-ttu-id="70147-120">**PR_MDB_PROVIDER**</span><span class="sxs-lookup"><span data-stu-id="70147-120">**PR_MDB_PROVIDER**</span></span>
   - <span data-ttu-id="70147-121">**PR_RESOURCE_FLAGS**</span><span class="sxs-lookup"><span data-stu-id="70147-121">**PR_RESOURCE_FLAGS**</span></span>
    
3. <span data-ttu-id="70147-122">构建限制以筛选出代表要打开的邮件存储的行。</span><span class="sxs-lookup"><span data-stu-id="70147-122">Build a restriction to filter out the row that represents the message store to be opened.</span></span> <span data-ttu-id="70147-123">有关查找默认邮件存储的信息，请参阅打开 [默认邮件存储](opening-the-default-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="70147-123">For more information about looking for the default message store, see [Opening the Default Message Store](opening-the-default-message-store.md).</span></span> <span data-ttu-id="70147-124">若要按名称查找邮件存储，请应用以下任一属性限制：</span><span class="sxs-lookup"><span data-stu-id="70147-124">To look for a message store by name, apply any of the following property restrictions:</span></span>
    
   - <span data-ttu-id="70147-125">将 **PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 与这种类型的邮件存储的常规名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="70147-125">Match **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) with the general name for this type of message store.</span></span> <span data-ttu-id="70147-126">例如，PR_PROVIDER_DISPLAY设置为"个人文件夹"。</span><span class="sxs-lookup"><span data-stu-id="70147-126">For example, PR_PROVIDER_DISPLAY might be set to "Personal Folders".</span></span>
    
   - <span data-ttu-id="70147-127">将 **PR_MDB_PROVIDER (** [PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 与这种类型的邮件存储的特定 **MAPIUID** 相匹配。</span><span class="sxs-lookup"><span data-stu-id="70147-127">Match **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) with the specific **MAPIUID** for this type of message store.</span></span> 
    
   - <span data-ttu-id="70147-128">将 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 匹配为此特定邮件存储的名称。</span><span class="sxs-lookup"><span data-stu-id="70147-128">Match **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name for this particular message store.</span></span> <span data-ttu-id="70147-129">例如 **，PR_DISPLAY_NAME** 设置为"My Messages for Fiscal Year 2010"。</span><span class="sxs-lookup"><span data-stu-id="70147-129">For example, **PR_DISPLAY_NAME** might be set to "My Messages for Fiscal Year 2010."</span></span> 
    
4. <span data-ttu-id="70147-130">调用 [HrQueryAllRows](hrqueryallrows.md) 从邮件存储表中检索相应的行。</span><span class="sxs-lookup"><span data-stu-id="70147-130">Call [HrQueryAllRows](hrqueryallrows.md) to retrieve the appropriate row from the message store table.</span></span> <span data-ttu-id="70147-131">行的条目标识符将包含在 _pprows_ 参数指向的行集的 **aRow** 成员属性值数组中。</span><span class="sxs-lookup"><span data-stu-id="70147-131">The entry identifier for the row will be included in the property value array for the **aRow** member of the row set pointed to by the  _pprows_ parameter.</span></span> 
    
5. <span data-ttu-id="70147-132">调用 [FreeProws](freeprows.md) 以释放  _pprows 指向的行集_。</span><span class="sxs-lookup"><span data-stu-id="70147-132">Call [FreeProws](freeprows.md) to free the row set pointed to by  _pprows_.</span></span>
    
6. <span data-ttu-id="70147-133">通过调用其 **IUnknown：：Release** 方法释放邮件存储表。</span><span class="sxs-lookup"><span data-stu-id="70147-133">Release the message store table by calling its **IUnknown::Release** method.</span></span> 
    
<span data-ttu-id="70147-134">如果已创建要打开的邮件存储的自定义条目标识符，请调用 [WrapStoreEntryID](wrapstoreentryid.md) 函数将其转换为标准条目标识符。</span><span class="sxs-lookup"><span data-stu-id="70147-134">If you have created a custom entry identifier for the message store to be opened, call the [WrapStoreEntryID](wrapstoreentryid.md) function to convert it to a standard entry identifier.</span></span> 
  
<span data-ttu-id="70147-135">在拥有邮件存储的条目标识符后，调用以下方法之一以打开它：</span><span class="sxs-lookup"><span data-stu-id="70147-135">After you have a message store's entry identifier, call one of the following methods to open it:</span></span>
  
- [<span data-ttu-id="70147-136">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="70147-136">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
- [<span data-ttu-id="70147-137">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="70147-137">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
    
<span data-ttu-id="70147-138">如果需要为邮件存储指定各种特殊选项，请调用 **OpenMsgStore。**</span><span class="sxs-lookup"><span data-stu-id="70147-138">Call **OpenMsgStore** if you need to specify a variety of special options for the message store.</span></span> <span data-ttu-id="70147-139">**OpenMsgStore** 允许您禁止显示对话框、将邮件存储标识为临时存储区或非邮件存储、设置访问级别以及延迟错误。</span><span class="sxs-lookup"><span data-stu-id="70147-139">**OpenMsgStore** allows you to suppress the display of dialog boxes, identify the message store as temporary or as a nonmessaging store, set access levels, and to defer errors.</span></span> <span data-ttu-id="70147-140">**OpenEntry** 仅允许设置访问级别和延迟错误。</span><span class="sxs-lookup"><span data-stu-id="70147-140">**OpenEntry** allows you only to set access levels and defer errors.</span></span> 
  
<span data-ttu-id="70147-141">设置 MDB_NO_MAIL 标志将指示 MAPI 邮件存储不用于发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="70147-141">Setting the MDB_NO_MAIL flag indicates to MAPI that the message store will not be used for sending or receiving messages.</span></span> <span data-ttu-id="70147-142">MAPI 不会通知 MAPI 后台处理程序存在此消息存储。</span><span class="sxs-lookup"><span data-stu-id="70147-142">MAPI does not inform the MAPI spooler about the existence of this message store.</span></span> <span data-ttu-id="70147-143">此MDB_TEMPORARY标志将邮件存储指定为临时存储，表示它不能用于存储永久信息。</span><span class="sxs-lookup"><span data-stu-id="70147-143">The MDB_TEMPORARY flag designates a message store as temporary, implying that it cannot be used to store permanent information.</span></span> <span data-ttu-id="70147-144">临时邮件存储不显示在邮件存储表中。</span><span class="sxs-lookup"><span data-stu-id="70147-144">Temporary message stores do not appear in the message store table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="70147-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70147-145">See also</span></span>

- [<span data-ttu-id="70147-146">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="70147-146">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)

