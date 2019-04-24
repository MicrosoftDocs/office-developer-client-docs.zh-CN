---
title: 遍历收件箱文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2ad1459f-d59a-4784-94ea-4cad194e6e50
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e954cb2d8029a31e7f69daaa7e8ed55a7953ac02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356579"
---
# <a name="traversing-the-inbox-folder"></a><span data-ttu-id="73af7-103">遍历收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="73af7-103">Traversing the Inbox Folder</span></span>

  
  
<span data-ttu-id="73af7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73af7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="73af7-105">**循环访问收件箱中的所有邮件**</span><span class="sxs-lookup"><span data-stu-id="73af7-105">**To cycle through all of the messages in the Inbox**</span></span>
  
1. <span data-ttu-id="73af7-106">调用[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)以检索收件箱的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="73af7-106">Call [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) to retrieve the entry identifier of the Inbox.</span></span> 
    
2. <span data-ttu-id="73af7-107">调用**IMAPIFolder:: OpenEntry**以打开收件箱。</span><span class="sxs-lookup"><span data-stu-id="73af7-107">Call **IMAPIFolder::OpenEntry** to open the Inbox.</span></span> 
    
3. <span data-ttu-id="73af7-108">调用收件箱的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法以检索内容表。</span><span class="sxs-lookup"><span data-stu-id="73af7-108">Call the Inbox's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to retrieve the contents table.</span></span> 
    
4. <span data-ttu-id="73af7-109">调用内容表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法将列设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和所需的任何其他列。</span><span class="sxs-lookup"><span data-stu-id="73af7-109">Call the contents table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) and any other columns you require.</span></span> 
    
5. <span data-ttu-id="73af7-110">调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索一组行。</span><span class="sxs-lookup"><span data-stu-id="73af7-110">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve a group of rows.</span></span> 
    
6. <span data-ttu-id="73af7-111">直到内容表中不再有任何行:</span><span class="sxs-lookup"><span data-stu-id="73af7-111">Until there are no longer any rows in the contents table:</span></span>
    
1. <span data-ttu-id="73af7-112">调用[IMsgStore:: OpenEntry](imsgstore-openentry.md)以打开每行中的条目标识符表示的邮件。</span><span class="sxs-lookup"><span data-stu-id="73af7-112">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the message represented by the entry identifier from each row.</span></span> 
    
2. <span data-ttu-id="73af7-113">将_lppUnk_参数分配给本地**IMessage**接口指针。</span><span class="sxs-lookup"><span data-stu-id="73af7-113">Assign the  _lppUnk_ parameter to a local **IMessage** interface pointer.</span></span> 
    
3. <span data-ttu-id="73af7-114">使用邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="73af7-114">Work with the properties of the message.</span></span>
    
4. <span data-ttu-id="73af7-115">释放_lppUnk_参数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="73af7-115">Release the pointer pointed to by the  _lppUnk_ parameter.</span></span> 
    
5. <span data-ttu-id="73af7-116">调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索下一组行。</span><span class="sxs-lookup"><span data-stu-id="73af7-116">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the next group of rows.</span></span> 
    
7. <span data-ttu-id="73af7-117">释放 "内容" 表。</span><span class="sxs-lookup"><span data-stu-id="73af7-117">Release the contents table.</span></span>
    

