---
title: 显示文件夹内容表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 14a4c123-776d-4a32-9688-8a4402dd1f53
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 30099e9fe645f810e08ba331717cff975f69b313
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774813"
---
# <a name="displaying-a-folder-contents-table"></a><span data-ttu-id="46087-103">显示文件夹内容表</span><span class="sxs-lookup"><span data-stu-id="46087-103">Displaying a folder contents table</span></span>

<span data-ttu-id="46087-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="46087-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="46087-105">文件夹的内容表包含有关的所有消息的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="46087-105">The contents table of a folder contains summary information about all of its messages.</span></span> <span data-ttu-id="46087-106">内容的接收文件夹的邮件类的表中显示有关新的传入消息的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="46087-106">Summary information about new incoming messages appears in the contents table of the receive folder for the message class.</span></span> <span data-ttu-id="46087-107">若要使此信息可供用户使用，检索表并根据需要显示的列和行。</span><span class="sxs-lookup"><span data-stu-id="46087-107">To make this information available to users, retrieve the table and display the columns and rows as appropriate.</span></span>
  
<span data-ttu-id="46087-108">**显示文件夹内容**</span><span class="sxs-lookup"><span data-stu-id="46087-108">**To display a folder contents table**</span></span>
  
1. <span data-ttu-id="46087-109">调用[IMsgStore::OpenEntry](imsgstore-openentry.md)，传递包含表的文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="46087-109">Call [IMsgStore::OpenEntry](imsgstore-openentry.md), passing the entry identifier of the folder containing the table.</span></span>
    
2. <span data-ttu-id="46087-110">调用该文件夹的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容的表格。</span><span class="sxs-lookup"><span data-stu-id="46087-110">Call the folder's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to open its contents table.</span></span> 
    
3. <span data-ttu-id="46087-111">如果需要通过调用表的[IMAPITable::SetColumns](imapitable-setcolumns.md)方法来指定特定的列，限制内容表的视图。</span><span class="sxs-lookup"><span data-stu-id="46087-111">Limit your view of the contents table if desired by calling the table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to specify particular columns.</span></span> 
    
4. <span data-ttu-id="46087-112">如果需要通过调用表的[IMAPITable::Restrict](imapitable-restrict.md)方法以筛选特定的行，限制内容表的视图。</span><span class="sxs-lookup"><span data-stu-id="46087-112">Limit your view of the contents table if desired by calling the table's [IMAPITable::Restrict](imapitable-restrict.md) method to filter particular rows.</span></span> <span data-ttu-id="46087-113">如果，例如，您想要显示仅尚未要读取的消息与特定的邮件类：</span><span class="sxs-lookup"><span data-stu-id="46087-113">If, for example, you want to show only messages with a specific message class that have yet to be read:</span></span> 
    
    1. <span data-ttu-id="46087-114">创建具有所需的邮件类的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性相匹配[SPropertyRestriction](spropertyrestriction.md)结构中属性限制。</span><span class="sxs-lookup"><span data-stu-id="46087-114">Create a property restriction in an [SPropertyRestriction](spropertyrestriction.md) structure that matches the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property with the desired message class.</span></span> 
        
    2. <span data-ttu-id="46087-115">创建使用**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 作为属性标记和 MSGFLAG_UNREAD 值作为掩码[SBitMaskRestriction](sbitmaskrestriction.md)结构中的位掩码限制。</span><span class="sxs-lookup"><span data-stu-id="46087-115">Create a bitmask restriction in an [SBitMaskRestriction](sbitmaskrestriction.md) structure that uses **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) as the property tag and the MSGFLAG_UNREAD value as the mask.</span></span>
        
    3. <span data-ttu-id="46087-116">创建加入属性和位掩码限制[SAndRestriction](sandrestriction.md)结构中的限制。</span><span class="sxs-lookup"><span data-stu-id="46087-116">Create a restriction in an [SAndRestriction](sandrestriction.md) structure that joins the property and bitmask restrictions.</span></span> 
    
5. <span data-ttu-id="46087-117">如果需要通过调用表的[IMAPITable::SortTable](imapitable-sorttable.md)方法，排序的内容表。</span><span class="sxs-lookup"><span data-stu-id="46087-117">Sort the contents table if desired by calling the table's [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
    
6. <span data-ttu-id="46087-118">调用[IMAPITable::QueryRows](imapitable-queryrows.md)处理的内容表中检索的所有行。</span><span class="sxs-lookup"><span data-stu-id="46087-118">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve all of the rows from the contents table for processing.</span></span> 
    

