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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339933"
---
# <a name="displaying-a-folder-contents-table"></a><span data-ttu-id="75dd3-103">显示文件夹内容表</span><span class="sxs-lookup"><span data-stu-id="75dd3-103">Displaying a folder contents table</span></span>

<span data-ttu-id="75dd3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="75dd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="75dd3-105">文件夹的 "内容" 表包含有关其所有邮件的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="75dd3-105">The contents table of a folder contains summary information about all of its messages.</span></span> <span data-ttu-id="75dd3-106">有关新传入邮件的摘要信息显示在邮件类别的接收文件夹的 "目录" 表中。</span><span class="sxs-lookup"><span data-stu-id="75dd3-106">Summary information about new incoming messages appears in the contents table of the receive folder for the message class.</span></span> <span data-ttu-id="75dd3-107">若要使此信息对用户可用, 请检索表并根据需要显示列和行。</span><span class="sxs-lookup"><span data-stu-id="75dd3-107">To make this information available to users, retrieve the table and display the columns and rows as appropriate.</span></span>
  
<span data-ttu-id="75dd3-108">**显示文件夹内容表**</span><span class="sxs-lookup"><span data-stu-id="75dd3-108">**To display a folder contents table**</span></span>
  
1. <span data-ttu-id="75dd3-109">调用[IMsgStore:: OpenEntry](imsgstore-openentry.md), 并传递包含该表的文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="75dd3-109">Call [IMsgStore::OpenEntry](imsgstore-openentry.md), passing the entry identifier of the folder containing the table.</span></span>
    
2. <span data-ttu-id="75dd3-110">调用文件夹的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容表。</span><span class="sxs-lookup"><span data-stu-id="75dd3-110">Call the folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to open its contents table.</span></span> 
    
3. <span data-ttu-id="75dd3-111">如果需要, 请通过调用表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法来指定特定列来限制内容表的视图。</span><span class="sxs-lookup"><span data-stu-id="75dd3-111">Limit your view of the contents table if desired by calling the table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to specify particular columns.</span></span> 
    
4. <span data-ttu-id="75dd3-112">如果需要, 请通过调用表的[IMAPITable:: Restrict](imapitable-restrict.md)方法筛选特定行来限制内容表的视图。</span><span class="sxs-lookup"><span data-stu-id="75dd3-112">Limit your view of the contents table if desired by calling the table's [IMAPITable::Restrict](imapitable-restrict.md) method to filter particular rows.</span></span> <span data-ttu-id="75dd3-113">例如, 如果要仅显示具有要阅读的特定邮件类别的邮件, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="75dd3-113">If, for example, you want to show only messages with a specific message class that have yet to be read:</span></span> 
    
    1. <span data-ttu-id="75dd3-114">在[SPropertyRestriction](spropertyrestriction.md)结构中创建一个与所需的邮件类相匹配的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性的属性限制。</span><span class="sxs-lookup"><span data-stu-id="75dd3-114">Create a property restriction in an [SPropertyRestriction](spropertyrestriction.md) structure that matches the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property with the desired message class.</span></span> 
        
    2. <span data-ttu-id="75dd3-115">在[SBitMaskRestriction](sbitmaskrestriction.md)结构中创建一个位掩码限制, 该限制使用**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 作为属性标记, 将 MSGFLAG_UNREAD 值用作掩码。</span><span class="sxs-lookup"><span data-stu-id="75dd3-115">Create a bitmask restriction in an [SBitMaskRestriction](sbitmaskrestriction.md) structure that uses **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) as the property tag and the MSGFLAG_UNREAD value as the mask.</span></span>
        
    3. <span data-ttu-id="75dd3-116">在联接属性和位掩码限制的[SAndRestriction](sandrestriction.md)结构中创建限制。</span><span class="sxs-lookup"><span data-stu-id="75dd3-116">Create a restriction in an [SAndRestriction](sandrestriction.md) structure that joins the property and bitmask restrictions.</span></span> 
    
5. <span data-ttu-id="75dd3-117">如果需要, 通过调用表的[IMAPITable:: SortTable](imapitable-sorttable.md)方法来对内容表进行排序。</span><span class="sxs-lookup"><span data-stu-id="75dd3-117">Sort the contents table if desired by calling the table's [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
    
6. <span data-ttu-id="75dd3-118">调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索内容表中的所有行以进行处理。</span><span class="sxs-lookup"><span data-stu-id="75dd3-118">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve all of the rows from the contents table for processing.</span></span> 
    

