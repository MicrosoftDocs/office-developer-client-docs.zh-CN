---
title: 删除通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 107ebcd7-b612-4139-b676-c3851f15bc74
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1fb7224e110bbee6844cf2820782aac8be213ba3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778602"
---
# <a name="removing-address-book-entries"></a><span data-ttu-id="4f752-103">删除通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="4f752-103">Removing address book entries</span></span>
  
<span data-ttu-id="4f752-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4f752-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4f752-105">调用容器的[IABContainer::DeleteEntries](iabcontainer-deleteentries.md)方法，以删除一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="4f752-105">Your container's [IABContainer::DeleteEntries](iabcontainer-deleteentries.md) method is called to remove one or more recipients.</span></span> <span data-ttu-id="4f752-106">**DeleteEntries**有两个参数： 一个表示要删除的收件人的项标识符和保留的标志值的数组。</span><span class="sxs-lookup"><span data-stu-id="4f752-106">**DeleteEntries** has two parameters: an array of entry identifiers representing the recipients to be deleted and a reserved flags value.</span></span> <span data-ttu-id="4f752-107">删除收件人会影响您的容器; 将目录除了删除收件人，您的容器必须删除代表收件人的内容表行。</span><span class="sxs-lookup"><span data-stu-id="4f752-107">Deleting a recipient affects the contents table of your container; in addition to deleting the recipient, your container must delete the contents table row that represents the recipient.</span></span> <span data-ttu-id="4f752-108">时行已从表中，您的容器必须为每个已注册的客户端发出表通知。</span><span class="sxs-lookup"><span data-stu-id="4f752-108">When the row has been removed from the table, your container must issue a table notification to each registered client.</span></span> 
  
### <a name="to-implement-iabcontainerdeleteentries"></a><span data-ttu-id="4f752-109">若要实现 IABContainer::DeleteEntries</span><span class="sxs-lookup"><span data-stu-id="4f752-109">To implement IABContainer::DeleteEntries</span></span>
  
1. <span data-ttu-id="4f752-110">删除由您的容器中的项标识符的每个收件人。</span><span class="sxs-lookup"><span data-stu-id="4f752-110">Delete each recipient represented by the entry identifier from your container.</span></span>
    
2. <span data-ttu-id="4f752-111">如果您的容器内容表处于打开状态：</span><span class="sxs-lookup"><span data-stu-id="4f752-111">If your container's contents table is open:</span></span>
    
   - <span data-ttu-id="4f752-112">与将设置为 TABLE_ROW_DELETED 以注册的每个已删除的内容的表格行的客户端的**ulTableEvent**成员发送_fnevTableModified_通知。</span><span class="sxs-lookup"><span data-stu-id="4f752-112">Send an  _fnevTableModified_ notification with the **ulTableEvent** member set to TABLE_ROW_DELETED to registered clients for each deleted contents table row.</span></span> <span data-ttu-id="4f752-113">如果您的提供商使用通知实用工具，调用[IMAPISupport::Notify](imapisupport-notify.md)发送这些通知。</span><span class="sxs-lookup"><span data-stu-id="4f752-113">If your provider uses the notification utility, call [IMAPISupport::Notify](imapisupport-notify.md) to send these notifications.</span></span> 
    
   - <span data-ttu-id="4f752-114">如果您的提供商支持对象通知，还可以发送_fnevObjectDeleted_通知。</span><span class="sxs-lookup"><span data-stu-id="4f752-114">If your provider supports object notifications, also send an  _fnevObjectDeleted_ notification.</span></span> 
    

