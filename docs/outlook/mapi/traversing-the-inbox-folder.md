---
title: 遍历收件箱文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2ad1459f-d59a-4784-94ea-4cad194e6e50
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5e93dbed0fe56ada5fc41c3e2e51aa3d0c3bef6d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594486"
---
# <a name="traversing-the-inbox-folder"></a><span data-ttu-id="138f3-103">遍历收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="138f3-103">Traversing the Inbox Folder</span></span>

  
  
<span data-ttu-id="138f3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="138f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="138f3-105">**若要循环进行所有收件箱中的消息**</span><span class="sxs-lookup"><span data-stu-id="138f3-105">**To cycle through all of the messages in the Inbox**</span></span>
  
1. <span data-ttu-id="138f3-106">调用[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)检索的收件箱的项标识符。</span><span class="sxs-lookup"><span data-stu-id="138f3-106">Call [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) to retrieve the entry identifier of the Inbox.</span></span> 
    
2. <span data-ttu-id="138f3-107">调用**IMAPIFolder::OpenEntry**打开收件箱。</span><span class="sxs-lookup"><span data-stu-id="138f3-107">Call **IMAPIFolder::OpenEntry** to open the Inbox.</span></span> 
    
3. <span data-ttu-id="138f3-108">调用收件箱的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法来检索内容表。</span><span class="sxs-lookup"><span data-stu-id="138f3-108">Call the Inbox's [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method to retrieve the contents table.</span></span> 
    
4. <span data-ttu-id="138f3-109">调用内容表的[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 的列和所需的任何其他列。</span><span class="sxs-lookup"><span data-stu-id="138f3-109">Call the contents table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) and any other columns you require.</span></span> 
    
5. <span data-ttu-id="138f3-110">调用[IMAPITable::QueryRows](imapitable-queryrows.md)检索一组行。</span><span class="sxs-lookup"><span data-stu-id="138f3-110">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve a group of rows.</span></span> 
    
6. <span data-ttu-id="138f3-111">直到内容表中不再有任何行：</span><span class="sxs-lookup"><span data-stu-id="138f3-111">Until there are no longer any rows in the contents table:</span></span>
    
1. <span data-ttu-id="138f3-112">调用[IMsgStore::OpenEntry](imsgstore-openentry.md)以打开由每一行中的项标识符的邮件。</span><span class="sxs-lookup"><span data-stu-id="138f3-112">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the message represented by the entry identifier from each row.</span></span> 
    
2. <span data-ttu-id="138f3-113">_LppUnk_参数分配一个本地**IMessage**接口指针。</span><span class="sxs-lookup"><span data-stu-id="138f3-113">Assign the  _lppUnk_ parameter to a local **IMessage** interface pointer.</span></span> 
    
3. <span data-ttu-id="138f3-114">处理邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="138f3-114">Work with the properties of the message.</span></span>
    
4. <span data-ttu-id="138f3-115">释放_lppUnk_参数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="138f3-115">Release the pointer pointed to by the  _lppUnk_ parameter.</span></span> 
    
5. <span data-ttu-id="138f3-116">调用[IMAPITable::QueryRows](imapitable-queryrows.md)若要检索的行下一步组。</span><span class="sxs-lookup"><span data-stu-id="138f3-116">Call [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the next group of rows.</span></span> 
    
7. <span data-ttu-id="138f3-117">发行版的内容表。</span><span class="sxs-lookup"><span data-stu-id="138f3-117">Release the contents table.</span></span>
    

