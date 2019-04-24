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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326220"
---
# <a name="opening-a-message-store"></a><span data-ttu-id="48357-103">打开邮件存储</span><span class="sxs-lookup"><span data-stu-id="48357-103">Opening a message store</span></span>

<span data-ttu-id="48357-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48357-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48357-105">根据配置文件的不同, 客户端将需要在典型会话期间打开一个或多个邮件存储。</span><span class="sxs-lookup"><span data-stu-id="48357-105">Depending on the profile, a client will need to open one or more message stores during a typical session.</span></span> <span data-ttu-id="48357-106">打开邮件存储区意味着获取指向其[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)实现的指针的访问权限。</span><span class="sxs-lookup"><span data-stu-id="48357-106">Opening a message store means gaining access to a pointer to its [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) implementation.</span></span> <span data-ttu-id="48357-107">**IMsgStore**接口提供通知的方法, 从而执行文件夹分配以及访问文件夹和邮件。</span><span class="sxs-lookup"><span data-stu-id="48357-107">The **IMsgStore** interface provides methods for notification, making folder assignments, and accessing folders and messages.</span></span> 
  
<span data-ttu-id="48357-108">客户端在登录时打开邮件存储, 并在修改配置文件时打开。</span><span class="sxs-lookup"><span data-stu-id="48357-108">Clients open message stores at logon and when a profile is being modified.</span></span> <span data-ttu-id="48357-109">如果您的客户端允许用户在活动会话期间向配置文件添加邮件存储区, 则可以立即打开它们, 也可以忽略它们, 直到下一个会话。</span><span class="sxs-lookup"><span data-stu-id="48357-109">If your client allows users to add message stores to the profile during an active session, you can either open them immediately or ignore them until the next session.</span></span> <span data-ttu-id="48357-110">通过在邮件存储表上注册通知, 您将收到新邮件存储的可用警报。</span><span class="sxs-lookup"><span data-stu-id="48357-110">By registering for notifications on the message store table, you will be alerted to the availability of a new message store.</span></span>
  
<span data-ttu-id="48357-111">若要打开邮件存储区, 您必须具有可用的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="48357-111">To open a message store, you must have its entry identifier available.</span></span> <span data-ttu-id="48357-112">大多数客户端访问要通过邮件存储库表打开的邮件存储区的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="48357-112">Most clients access the entry identifiers for the message stores they wish to open through the message store table.</span></span> <span data-ttu-id="48357-113">但是, 某些邮件将文档存储在其条目标识符的格式中, 从而使客户端可以绕过邮件存储表并构造必要的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="48357-113">However, some message stores document the format of their entry identifiers, thereby enabling clients to bypass the message store table and construct the necessary entry identifier.</span></span> <span data-ttu-id="48357-114">它们可以将此条目标识符直接传递给[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)和 MAPI 会自动为提供程序创建配置文件部分, 而无需将其与任何邮件服务相关联。</span><span class="sxs-lookup"><span data-stu-id="48357-114">They can pass this entry identifier directly to [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) and MAPI automatically creates a profile section for the provider without associating it with any message service.</span></span> 
  
## <a name="retrieve-an-entry-identifier-from-the-message-store-table"></a><span data-ttu-id="48357-115">从邮件存储库表中检索条目标识符</span><span class="sxs-lookup"><span data-stu-id="48357-115">Retrieve an entry identifier from the message store table</span></span>
  
1. <span data-ttu-id="48357-116">调用[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)以打开邮件存储库表。</span><span class="sxs-lookup"><span data-stu-id="48357-116">Call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to open the message store table.</span></span> 
    
2. <span data-ttu-id="48357-117">调用**IMAPITable:: SetColumns**将表限制为包含以下列的小列集:</span><span class="sxs-lookup"><span data-stu-id="48357-117">Call **IMAPITable::SetColumns** to limit the table to a small column set that includes the following columns:</span></span> 
    
   - <span data-ttu-id="48357-118">**PR_PROVIDER_DISPLAY**或**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="48357-118">**PR_PROVIDER_DISPLAY** or **PR_DISPLAY_NAME**</span></span>
   - <span data-ttu-id="48357-119">**PR_ENTRYID**属性</span><span class="sxs-lookup"><span data-stu-id="48357-119">**PR_ENTRYID** properties</span></span> 
   - <span data-ttu-id="48357-120">**PR_MDB_PROVIDER**</span><span class="sxs-lookup"><span data-stu-id="48357-120">**PR_MDB_PROVIDER**</span></span>
   - <span data-ttu-id="48357-121">**PR_RESOURCE_FLAGS**</span><span class="sxs-lookup"><span data-stu-id="48357-121">**PR_RESOURCE_FLAGS**</span></span>
    
3. <span data-ttu-id="48357-122">生成限制以筛选出表示要打开的邮件存储的行。</span><span class="sxs-lookup"><span data-stu-id="48357-122">Build a restriction to filter out the row that represents the message store to be opened.</span></span> <span data-ttu-id="48357-123">有关查找默认邮件存储区的详细信息, 请参阅[打开默认邮件存储](opening-the-default-message-store.md)。</span><span class="sxs-lookup"><span data-stu-id="48357-123">For more information about looking for the default message store, see [Opening the Default Message Store](opening-the-default-message-store.md).</span></span> <span data-ttu-id="48357-124">若要按名称查找邮件存储, 请应用以下任一属性限制:</span><span class="sxs-lookup"><span data-stu-id="48357-124">To look for a message store by name, apply any of the following property restrictions:</span></span>
    
   - <span data-ttu-id="48357-125">将**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 与此类型邮件存储的常规名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="48357-125">Match **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) with the general name for this type of message store.</span></span> <span data-ttu-id="48357-126">例如, PR_PROVIDER_DISPLAY 可能设置为 "个人文件夹"。</span><span class="sxs-lookup"><span data-stu-id="48357-126">For example, PR_PROVIDER_DISPLAY might be set to "Personal Folders".</span></span>
    
   - <span data-ttu-id="48357-127">将**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 与此类型邮件存储的特定**MAPIUID**进行匹配。</span><span class="sxs-lookup"><span data-stu-id="48357-127">Match **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) with the specific **MAPIUID** for this type of message store.</span></span> 
    
   - <span data-ttu-id="48357-128">将**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 与此特定邮件存储区的名称进行匹配。</span><span class="sxs-lookup"><span data-stu-id="48357-128">Match **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name for this particular message store.</span></span> <span data-ttu-id="48357-129">例如, **PR_DISPLAY_NAME**可能设置为 "我的会计年度2010的邮件"。</span><span class="sxs-lookup"><span data-stu-id="48357-129">For example, **PR_DISPLAY_NAME** might be set to "My Messages for Fiscal Year 2010."</span></span> 
    
4. <span data-ttu-id="48357-130">调用[HrQueryAllRows](hrqueryallrows.md)以检索邮件存储表中的相应行。</span><span class="sxs-lookup"><span data-stu-id="48357-130">Call [HrQueryAllRows](hrqueryallrows.md) to retrieve the appropriate row from the message store table.</span></span> <span data-ttu-id="48357-131">行的条目标识符将包含在由_pprows_参数指向的行集的**aRow**成员的属性值数组中。</span><span class="sxs-lookup"><span data-stu-id="48357-131">The entry identifier for the row will be included in the property value array for the **aRow** member of the row set pointed to by the  _pprows_ parameter.</span></span> 
    
5. <span data-ttu-id="48357-132">调用[FreeProws](freeprows.md)以释放_pprows_指向的行集。</span><span class="sxs-lookup"><span data-stu-id="48357-132">Call [FreeProws](freeprows.md) to free the row set pointed to by  _pprows_.</span></span>
    
6. <span data-ttu-id="48357-133">通过调用其**IUnknown:: Release**方法释放邮件存储库表。</span><span class="sxs-lookup"><span data-stu-id="48357-133">Release the message store table by calling its **IUnknown::Release** method.</span></span> 
    
<span data-ttu-id="48357-134">如果已为要打开的邮件存储区创建了自定义条目标识符, 请调用[WrapStoreEntryID](wrapstoreentryid.md)函数将其转换为标准条目标识符。</span><span class="sxs-lookup"><span data-stu-id="48357-134">If you have created a custom entry identifier for the message store to be opened, call the [WrapStoreEntryID](wrapstoreentryid.md) function to convert it to a standard entry identifier.</span></span> 
  
<span data-ttu-id="48357-135">拥有邮件存储区的条目标识符后, 请调用以下方法之一将其打开:</span><span class="sxs-lookup"><span data-stu-id="48357-135">After you have a message store's entry identifier, call one of the following methods to open it:</span></span>
  
- [<span data-ttu-id="48357-136">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="48357-136">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
- [<span data-ttu-id="48357-137">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="48357-137">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
    
<span data-ttu-id="48357-138">如果需要为邮件存储区指定各种特殊选项, 请调用**OpenMsgStore** 。</span><span class="sxs-lookup"><span data-stu-id="48357-138">Call **OpenMsgStore** if you need to specify a variety of special options for the message store.</span></span> <span data-ttu-id="48357-139">**OpenMsgStore**允许您禁止显示对话框、将邮件存储区标识为临时或作为 nonmessaging 存储区、设置访问级别和延迟错误。</span><span class="sxs-lookup"><span data-stu-id="48357-139">**OpenMsgStore** allows you to suppress the display of dialog boxes, identify the message store as temporary or as a nonmessaging store, set access levels, and to defer errors.</span></span> <span data-ttu-id="48357-140">**OpenEntry**仅允许您设置访问级别和延迟错误。</span><span class="sxs-lookup"><span data-stu-id="48357-140">**OpenEntry** allows you only to set access levels and defer errors.</span></span> 
  
<span data-ttu-id="48357-141">设置 MDB_NO_MAIL 标志指示 MAPI 邮件存储将不用于发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="48357-141">Setting the MDB_NO_MAIL flag indicates to MAPI that the message store will not be used for sending or receiving messages.</span></span> <span data-ttu-id="48357-142">mapi 不会通知 mapi 后台处理程序是否存在此邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="48357-142">MAPI does not inform the MAPI spooler about the existence of this message store.</span></span> <span data-ttu-id="48357-143">MDB_TEMPORARY 标志将邮件存储区指定为临时邮件, 这意味着它不能用于存储永久信息。</span><span class="sxs-lookup"><span data-stu-id="48357-143">The MDB_TEMPORARY flag designates a message store as temporary, implying that it cannot be used to store permanent information.</span></span> <span data-ttu-id="48357-144">临时邮件存储不会出现在邮件存储库表中。</span><span class="sxs-lookup"><span data-stu-id="48357-144">Temporary message stores do not appear in the message store table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="48357-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48357-145">See also</span></span>

- [<span data-ttu-id="48357-146">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="48357-146">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)

