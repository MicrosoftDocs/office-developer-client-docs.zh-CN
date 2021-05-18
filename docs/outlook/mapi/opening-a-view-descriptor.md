---
title: 打开视图描述符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1940feb0-9e0f-4d96-9fb9-b9a35a0aa661
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ce53e5a91f6fa340728872457eae7f6514e287aa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413036"
---
# <a name="opening-a-view-descriptor"></a><span data-ttu-id="cfdb2-103">打开视图描述符</span><span class="sxs-lookup"><span data-stu-id="cfdb2-103">Opening a view descriptor</span></span>
  
<span data-ttu-id="cfdb2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cfdb2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cfdb2-105">许多文件夹都可以使用普通视图、默认视图或任意数目的个性化视图打开。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-105">Many folders can be opened with a normal view, a default view, or any number of personalized views.</span></span> <span data-ttu-id="cfdb2-106">视图描述如何显示文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-106">A view describes how to display the contents of a folder.</span></span> <span data-ttu-id="cfdb2-107">如果没有备用视图，并且第一次打开文件夹，则使用普通视图。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-107">The normal view is used when there is no alternative view and when you are opening the folder for the first time.</span></span> <span data-ttu-id="cfdb2-108">当存在备用视图时，必须使用它打开文件夹。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-108">When an alternative view does exist, you must use it to open the folder.</span></span>
  
<span data-ttu-id="cfdb2-109">视图在称为视图描述符的消息中介绍。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-109">A view is described in a message known as a view descriptor.</span></span> <span data-ttu-id="cfdb2-110">视图描述符通常创建为关联邮件，并可以显示在公用或个人视图文件夹或任何 IPM 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-110">View descriptors are typically created as associated messages and can appear in either the common or personal view folders or in any IPM folder.</span></span>
  
### <a name="to-open-a-view-descriptor"></a><span data-ttu-id="cfdb2-111">打开视图描述符</span><span class="sxs-lookup"><span data-stu-id="cfdb2-111">To open a view descriptor</span></span>
  
1. <span data-ttu-id="cfdb2-112">调用 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 以检索文件夹的关联内容表。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-112">Call [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) to retrieve the associated contents table for the folder.</span></span> 
    
2. <span data-ttu-id="cfdb2-113">创建一个限制，以便仅查找具有保留用于视图描述符的邮件类的邮件，并调用 [IMAPITable：：Restrict](imapitable-restrict.md) 以限制表和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 检索相应的行，或者...</span><span class="sxs-lookup"><span data-stu-id="cfdb2-113">Create a restriction that locates only messages with the message class reserved for view descriptors and call [IMAPITable::Restrict](imapitable-restrict.md) to limit the table and [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the appropriate rows, or...</span></span>
    
   <span data-ttu-id="cfdb2-114">调用文件夹的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来 **检索其** PR_DEFAULT_VIEW_ENTRYID ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-114">Call the folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_DEFAULT_VIEW_ENTRYID** ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="cfdb2-115">**PR_DEFAULT_VIEW_ENTRYID** 包含包含文件夹的默认视图描述符的邮件的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-115">**PR_DEFAULT_VIEW_ENTRYID** contains the entry identifier for the message containing the default view descriptor for a folder.</span></span> <span data-ttu-id="cfdb2-116">如果文件夹支持在调用 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 和 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md)时使用 MAPI_ASSOCIATED 标志，此调用将成功。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-116">This call will succeed if the folder supports the use of the MAPI_ASSOCIATED flag on calls to [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) and [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md).</span></span>
    
3. <span data-ttu-id="cfdb2-117">使用视图描述符的条目标识符调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开它。</span><span class="sxs-lookup"><span data-stu-id="cfdb2-117">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) with the entry identifier of the view descriptor to open it.</span></span> 
    

