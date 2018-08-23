---
title: 删除收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f7495030-e3b8-4c7c-9e19-284ba820e846
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 03917ad52f1dc1ce4d0b59cd54fe33f58f352061
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582943"
---
# <a name="deleting-a-recipient"></a><span data-ttu-id="f855c-103">删除收件人</span><span class="sxs-lookup"><span data-stu-id="f855c-103">Deleting a Recipient</span></span>

  
  
<span data-ttu-id="f855c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f855c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="f855c-105">**若要从可修改容器中删除一个或多个通讯簿条目**</span><span class="sxs-lookup"><span data-stu-id="f855c-105">**To remove one or more address book entries from a modifiable container**</span></span>
  
- <span data-ttu-id="f855c-106">调用[IABContainer::DeleteEntries](iabcontainer-deleteentries.md)方法，传递表示通讯簿条目，要删除的项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="f855c-106">Call the [IABContainer::DeleteEntries](iabcontainer-deleteentries.md) method, passing an array of entry identifiers that represent the address book entries to be deleted.</span></span> <span data-ttu-id="f855c-107">**DeleteEntries**可以返回一个警告，MAPI_W_PARTIAL_COMPLETION，以指明它无法删除一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="f855c-107">**DeleteEntries** can return a warning, MAPI_W_PARTIAL_COMPLETION, to indicate that it couldn't delete one or more of the entries.</span></span> <span data-ttu-id="f855c-108">测试此返回值与**HR_FAILED**宏，并调用容器的[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法，如果需要有关问题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f855c-108">Test for this return value with the **HR_FAILED** macro and call the container's [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method if more information about the problem is needed.</span></span> 
    
<span data-ttu-id="f855c-109">当您在缓存中已删除的条目[ADRENTRY](adrentry.md)结构容纳的指针时，您仍然能够检索使用其项标识符的属性。</span><span class="sxs-lookup"><span data-stu-id="f855c-109">When you hold a pointer to a deleted entry's [ADRENTRY](adrentry.md) structure in your cache, you will still be able to retrieve properties using its entry identifier.</span></span> <span data-ttu-id="f855c-110">这是因为该条目仅标记为删除。</span><span class="sxs-lookup"><span data-stu-id="f855c-110">This is because the entry is only marked for deletion.</span></span> <span data-ttu-id="f855c-111">MAPI 设计维护对这些标记的项的访问级别。</span><span class="sxs-lookup"><span data-stu-id="f855c-111">MAPI maintains a level of access to these marked entries by design.</span></span> 
  

