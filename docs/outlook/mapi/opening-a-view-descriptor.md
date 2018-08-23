---
title: 打开视图描述符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1940feb0-9e0f-4d96-9fb9-b9a35a0aa661
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 680d80c0827399f3b7a0ea5819e51be654a05810
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592477"
---
# <a name="opening-a-view-descriptor"></a><span data-ttu-id="e4e79-103">打开视图描述符</span><span class="sxs-lookup"><span data-stu-id="e4e79-103">Opening a view descriptor</span></span>
  
<span data-ttu-id="e4e79-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4e79-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4e79-105">很多文件夹可以打开与普通视图、 默认视图或任意数量的个性化视图。</span><span class="sxs-lookup"><span data-stu-id="e4e79-105">Many folders can be opened with a normal view, a default view, or any number of personalized views.</span></span> <span data-ttu-id="e4e79-106">视图介绍如何显示文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="e4e79-106">A view describes how to display the contents of a folder.</span></span> <span data-ttu-id="e4e79-107">普通视图时没有替代视图和首次打开文件夹时使用。</span><span class="sxs-lookup"><span data-stu-id="e4e79-107">The normal view is used when there is no alternative view and when you are opening the folder for the first time.</span></span> <span data-ttu-id="e4e79-108">存在另一个视图，必须使用它以打开文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4e79-108">When an alternative view does exist, you must use it to open the folder.</span></span>
  
<span data-ttu-id="e4e79-109">视图所述称为视图描述符一条消息。</span><span class="sxs-lookup"><span data-stu-id="e4e79-109">A view is described in a message known as a view descriptor.</span></span> <span data-ttu-id="e4e79-110">视图描述符通常创建作为相关联的邮件，并可以显示在公共或个人视图文件夹或任何 IPM 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e4e79-110">View descriptors are typically created as associated messages and can appear in either the common or personal view folders or in any IPM folder.</span></span>
  
### <a name="to-open-a-view-descriptor"></a><span data-ttu-id="e4e79-111">要打开视图描述符</span><span class="sxs-lookup"><span data-stu-id="e4e79-111">To open a view descriptor</span></span>
  
1. <span data-ttu-id="e4e79-112">调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)用于检索文件夹关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="e4e79-112">Call [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) to retrieve the associated contents table for the folder.</span></span> 
    
2. <span data-ttu-id="e4e79-113">创建与供视图描述符邮件类的定位仅邮件限制和呼叫[IMAPITable::Restrict](imapitable-restrict.md)限制表和[IMAPITable::QueryRows](imapitable-queryrows.md)检索合适的行，或...</span><span class="sxs-lookup"><span data-stu-id="e4e79-113">Create a restriction that locates only messages with the message class reserved for view descriptors and call [IMAPITable::Restrict](imapitable-restrict.md) to limit the table and [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the appropriate rows, or...</span></span>
    
   <span data-ttu-id="e4e79-114">调用该文件夹的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_DEFAULT_VIEW_ENTRYID** ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e4e79-114">Call the folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_DEFAULT_VIEW_ENTRYID** ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="e4e79-115">**PR_DEFAULT_VIEW_ENTRYID**包含包含的文件夹的默认视图描述符的消息的项标识符。</span><span class="sxs-lookup"><span data-stu-id="e4e79-115">**PR_DEFAULT_VIEW_ENTRYID** contains the entry identifier for the message containing the default view descriptor for a folder.</span></span> <span data-ttu-id="e4e79-116">如果文件夹上调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)和[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)支持 MAPI_ASSOCIATED 标志的使用，将会成功此呼叫。</span><span class="sxs-lookup"><span data-stu-id="e4e79-116">This call will succeed if the folder supports the use of the MAPI_ASSOCIATED flag on calls to [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) and [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md).</span></span>
    
3. <span data-ttu-id="e4e79-117">调用[IMsgStore::OpenEntry](imsgstore-openentry.md)视图描述符，以将其打开的项标识符。</span><span class="sxs-lookup"><span data-stu-id="e4e79-117">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) with the entry identifier of the view descriptor to open it.</span></span> 
    

