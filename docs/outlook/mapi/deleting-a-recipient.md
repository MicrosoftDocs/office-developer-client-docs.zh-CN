---
title: 删除收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f7495030-e3b8-4c7c-9e19-284ba820e846
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bd01c66d9fff7c94ffb1ce9f956f1951bc482020
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316812"
---
# <a name="deleting-a-recipient"></a><span data-ttu-id="29688-103">删除收件人</span><span class="sxs-lookup"><span data-stu-id="29688-103">Deleting a Recipient</span></span>

  
  
<span data-ttu-id="29688-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29688-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="29688-105">**从可修改的容器中删除一个或多个通讯簿条目**</span><span class="sxs-lookup"><span data-stu-id="29688-105">**To remove one or more address book entries from a modifiable container**</span></span>
  
- <span data-ttu-id="29688-106">调用[IABContainer::D eleteentries](iabcontainer-deleteentries.md)方法, 传递表示要删除的通讯簿条目的条目标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="29688-106">Call the [IABContainer::DeleteEntries](iabcontainer-deleteentries.md) method, passing an array of entry identifiers that represent the address book entries to be deleted.</span></span> <span data-ttu-id="29688-107">**DeleteEntries**可以返回一个警告 MAPI_W_PARTIAL_COMPLETION, 以指示它无法删除一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="29688-107">**DeleteEntries** can return a warning, MAPI_W_PARTIAL_COMPLETION, to indicate that it couldn't delete one or more of the entries.</span></span> <span data-ttu-id="29688-108">如果需要有关该问题的详细信息, 请使用**HR_FAILED**宏测试此返回值并调用容器的[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="29688-108">Test for this return value with the **HR_FAILED** macro and call the container's [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method if more information about the problem is needed.</span></span> 
    
<span data-ttu-id="29688-109">当您将指向已删除项的[ADRENTRY](adrentry.md)结构的指针保存在缓存中时, 您仍可以使用其条目标识符检索属性。</span><span class="sxs-lookup"><span data-stu-id="29688-109">When you hold a pointer to a deleted entry's [ADRENTRY](adrentry.md) structure in your cache, you will still be able to retrieve properties using its entry identifier.</span></span> <span data-ttu-id="29688-110">这是因为该条目仅标记为删除。</span><span class="sxs-lookup"><span data-stu-id="29688-110">This is because the entry is only marked for deletion.</span></span> <span data-ttu-id="29688-111">MAPI 通过设计维护对这些标记的项的访问级别。</span><span class="sxs-lookup"><span data-stu-id="29688-111">MAPI maintains a level of access to these marked entries by design.</span></span> 
  

