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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425258"
---
# <a name="removing-address-book-entries"></a><span data-ttu-id="50746-103">删除通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="50746-103">Removing address book entries</span></span>
  
<span data-ttu-id="50746-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50746-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50746-105">调用容器的 [IABContainer：:D eleteEntries](iabcontainer-deleteentries.md) 方法以删除一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="50746-105">Your container's [IABContainer::DeleteEntries](iabcontainer-deleteentries.md) method is called to remove one or more recipients.</span></span> <span data-ttu-id="50746-106">**DeleteEntries** 有两个参数：表示要删除的收件人的条目标识符数组和保留标志值。</span><span class="sxs-lookup"><span data-stu-id="50746-106">**DeleteEntries** has two parameters: an array of entry identifiers representing the recipients to be deleted and a reserved flags value.</span></span> <span data-ttu-id="50746-107">删除收件人会影响容器的内容表;除了删除收件人之外，容器还必须删除表示收件人的内容表行。</span><span class="sxs-lookup"><span data-stu-id="50746-107">Deleting a recipient affects the contents table of your container; in addition to deleting the recipient, your container must delete the contents table row that represents the recipient.</span></span> <span data-ttu-id="50746-108">从表中删除行后，容器必须向每个注册的客户端发出表通知。</span><span class="sxs-lookup"><span data-stu-id="50746-108">When the row has been removed from the table, your container must issue a table notification to each registered client.</span></span> 
  
### <a name="to-implement-iabcontainerdeleteentries"></a><span data-ttu-id="50746-109">实现 IABContainer：:D eleteEntries</span><span class="sxs-lookup"><span data-stu-id="50746-109">To implement IABContainer::DeleteEntries</span></span>
  
1. <span data-ttu-id="50746-110">从容器中删除条目标识符表示的每个收件人。</span><span class="sxs-lookup"><span data-stu-id="50746-110">Delete each recipient represented by the entry identifier from your container.</span></span>
    
2. <span data-ttu-id="50746-111">如果容器的内容表已打开：</span><span class="sxs-lookup"><span data-stu-id="50746-111">If your container's contents table is open:</span></span>
    
   - <span data-ttu-id="50746-112">将  _fnevTableModified_ 通知与 **ulTableEvent** 成员集一TABLE_ROW_DELETED每个已删除内容表行的注册客户端。</span><span class="sxs-lookup"><span data-stu-id="50746-112">Send an  _fnevTableModified_ notification with the **ulTableEvent** member set to TABLE_ROW_DELETED to registered clients for each deleted contents table row.</span></span> <span data-ttu-id="50746-113">如果提供程序使用通知实用工具，请调用 [IMAPISupport：：Notify](imapisupport-notify.md) 以发送这些通知。</span><span class="sxs-lookup"><span data-stu-id="50746-113">If your provider uses the notification utility, call [IMAPISupport::Notify](imapisupport-notify.md) to send these notifications.</span></span> 
    
   - <span data-ttu-id="50746-114">如果提供程序支持对象通知，还应发送  _fnevObjectDeleted_ 通知。</span><span class="sxs-lookup"><span data-stu-id="50746-114">If your provider supports object notifications, also send an  _fnevObjectDeleted_ notification.</span></span> 
    

