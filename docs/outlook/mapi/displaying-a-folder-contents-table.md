---
title: 显示文件夹内容表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 14a4c123-776d-4a32-9688-8a4402dd1f53
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 56847283afaf41c1d45cdb875ddf49eaa5881175
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412392"
---
# <a name="displaying-a-folder-contents-table"></a><span data-ttu-id="9fcc4-103">显示文件夹内容表</span><span class="sxs-lookup"><span data-stu-id="9fcc4-103">Displaying a folder contents table</span></span>

<span data-ttu-id="9fcc4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9fcc4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9fcc4-105">文件夹的内容表包含有关其所有邮件的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-105">The contents table of a folder contains summary information about all of its messages.</span></span> <span data-ttu-id="9fcc4-106">有关新传入邮件的摘要信息将显示在邮件类的接收文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-106">Summary information about new incoming messages appears in the contents table of the receive folder for the message class.</span></span> <span data-ttu-id="9fcc4-107">若要使此信息可供用户使用，请检索该表并显示相应的列和行。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-107">To make this information available to users, retrieve the table and display the columns and rows as appropriate.</span></span>
  
<span data-ttu-id="9fcc4-108">**显示文件夹内容表**</span><span class="sxs-lookup"><span data-stu-id="9fcc4-108">**To display a folder contents table**</span></span>
  
1. <span data-ttu-id="9fcc4-109">调用 [IMsgStore：：OpenEntry](imsgstore-openentry.md)，传递包含表的文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-109">Call [IMsgStore::OpenEntry](imsgstore-openentry.md), passing the entry identifier of the folder containing the table.</span></span>
    
2. <span data-ttu-id="9fcc4-110">调用文件夹的 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法以打开其内容表。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-110">Call the folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to open its contents table.</span></span> 
    
3. <span data-ttu-id="9fcc4-111">如果需要，请通过调用表的 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法指定特定列来限制目录视图。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-111">Limit your view of the contents table if desired by calling the table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to specify particular columns.</span></span> 
    
4. <span data-ttu-id="9fcc4-112">如果需要，请通过调用表的 [IMAPITable：：Restrict](imapitable-restrict.md) 方法来筛选特定行，从而限制内容表的视图。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-112">Limit your view of the contents table if desired by calling the table's [IMAPITable::Restrict](imapitable-restrict.md) method to filter particular rows.</span></span> <span data-ttu-id="9fcc4-113">例如，如果要只显示具有尚未读取的特定邮件类的邮件：</span><span class="sxs-lookup"><span data-stu-id="9fcc4-113">If, for example, you want to show only messages with a specific message class that have yet to be read:</span></span> 
    
    1. <span data-ttu-id="9fcc4-114">在 [SPropertyRestriction](spropertyrestriction.md) 结构中创建一个与 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性匹配所需的邮件类的属性限制。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-114">Create a property restriction in an [SPropertyRestriction](spropertyrestriction.md) structure that matches the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property with the desired message class.</span></span> 
        
    2. <span data-ttu-id="9fcc4-115">在 [SBitMaskRestriction](sbitmaskrestriction.md) 结构中创建位掩码限制，该结构使用 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 作为属性标记，将 MSGFLAG_UNREAD 值用作掩码。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-115">Create a bitmask restriction in an [SBitMaskRestriction](sbitmaskrestriction.md) structure that uses **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) as the property tag and the MSGFLAG_UNREAD value as the mask.</span></span>
        
    3. <span data-ttu-id="9fcc4-116">在连接属性和位掩码限制的 [SAndRestriction](sandrestriction.md) 结构中创建限制。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-116">Create a restriction in an [SAndRestriction](sandrestriction.md) structure that joins the property and bitmask restrictions.</span></span> 
    
5. <span data-ttu-id="9fcc4-117">如果需要，通过调用表的 [IMAPITable：：SortTable](imapitable-sorttable.md) 方法对内容表进行排序。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-117">Sort the contents table if desired by calling the table's [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
    
6. <span data-ttu-id="9fcc4-118">调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 从内容表中检索所有行进行处理。</span><span class="sxs-lookup"><span data-stu-id="9fcc4-118">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve all of the rows from the contents table for processing.</span></span> 
    

