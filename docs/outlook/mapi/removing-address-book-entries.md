---
title: 删除通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 107ebcd7-b612-4139-b676-c3851f15bc74
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1d5ae33b08c85c9ee93764d762c2ec251fddd265
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328348"
---
# <a name="removing-address-book-entries"></a><span data-ttu-id="71869-103">删除通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="71869-103">Removing address book entries</span></span>
  
<span data-ttu-id="71869-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="71869-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="71869-105">将调用容器的[IABContainer::D eleteentries](iabcontainer-deleteentries.md)方法以删除一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="71869-105">Your container's [IABContainer::DeleteEntries](iabcontainer-deleteentries.md) method is called to remove one or more recipients.</span></span> <span data-ttu-id="71869-106">**DeleteEntries**有两个参数: 条目标识符的数组, 这些标识符代表要删除的收件人和保留的标志值。</span><span class="sxs-lookup"><span data-stu-id="71869-106">**DeleteEntries** has two parameters: an array of entry identifiers representing the recipients to be deleted and a reserved flags value.</span></span> <span data-ttu-id="71869-107">删除收件人会影响容器的内容表;除了删除收件人, 容器必须删除代表收件人的内容表格行。</span><span class="sxs-lookup"><span data-stu-id="71869-107">Deleting a recipient affects the contents table of your container; in addition to deleting the recipient, your container must delete the contents table row that represents the recipient.</span></span> <span data-ttu-id="71869-108">当从表中删除行时, 您的容器必须向每个已注册的客户端发出表通知。</span><span class="sxs-lookup"><span data-stu-id="71869-108">When the row has been removed from the table, your container must issue a table notification to each registered client.</span></span> 
  
### <a name="to-implement-iabcontainerdeleteentries"></a><span data-ttu-id="71869-109">实现 IABContainer::D eleteentries</span><span class="sxs-lookup"><span data-stu-id="71869-109">To implement IABContainer::DeleteEntries</span></span>
  
1. <span data-ttu-id="71869-110">从容器中删除条目标识符代表的每个收件人。</span><span class="sxs-lookup"><span data-stu-id="71869-110">Delete each recipient represented by the entry identifier from your container.</span></span>
    
2. <span data-ttu-id="71869-111">如果容器的内容表处于打开状态:</span><span class="sxs-lookup"><span data-stu-id="71869-111">If your container's contents table is open:</span></span>
    
   - <span data-ttu-id="71869-112">向每个已删除内容表行的已注册客户端发送_fnevTableModified_通知, 并将**ulTableEvent**成员设置为 TABLE_ROW_DELETED。</span><span class="sxs-lookup"><span data-stu-id="71869-112">Send an  _fnevTableModified_ notification with the **ulTableEvent** member set to TABLE_ROW_DELETED to registered clients for each deleted contents table row.</span></span> <span data-ttu-id="71869-113">如果提供程序使用通知实用程序, 请调用[IMAPISupport:: Notify](imapisupport-notify.md)发送这些通知。</span><span class="sxs-lookup"><span data-stu-id="71869-113">If your provider uses the notification utility, call [IMAPISupport::Notify](imapisupport-notify.md) to send these notifications.</span></span> 
    
   - <span data-ttu-id="71869-114">如果您的提供程序支持对象通知, 则还要发送_fnevObjectDeleted_通知。</span><span class="sxs-lookup"><span data-stu-id="71869-114">If your provider supports object notifications, also send an  _fnevObjectDeleted_ notification.</span></span> 
    

