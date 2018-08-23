---
title: 处理表通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: edc9bc71-4885-4783-b465-0bafa20eff73
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b36e4697bfd4360f4ea6ea47c70eaaae434696d8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595130"
---
# <a name="handling-table-notification"></a><span data-ttu-id="e1f39-103">处理表通知</span><span class="sxs-lookup"><span data-stu-id="e1f39-103">Handling table notification</span></span>

<span data-ttu-id="e1f39-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1f39-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1f39-105">作为的替代方式直接注册 advise source 对象，如文件夹或消息的用户，客户端可以在内容通知注册或层次结构表。</span><span class="sxs-lookup"><span data-stu-id="e1f39-105">As an alternative to registering directly with an advise source object, such as a folder or a messaging user, a client can register for notifications on a contents or hierarchy table.</span></span> <span data-ttu-id="e1f39-106">跟踪更改通讯簿条目、 文件夹和邮件内容或层次结构表可以更简单、 更加比通过单个对象。</span><span class="sxs-lookup"><span data-stu-id="e1f39-106">Tracking changes to address book entries, folders, and messages through a contents or hierarchy table can be simpler and more straightforward than through individual objects.</span></span> 

<span data-ttu-id="e1f39-107">例如，您可以在文件夹层次结构表，寻找到它的子文件夹发生更改时呼叫[IMAPITable::Advise](imapitable-advise.md) 。</span><span class="sxs-lookup"><span data-stu-id="e1f39-107">For example, you can call [IMAPITable::Advise](imapitable-advise.md) on a folder's hierarchy table to discover when changes occur to one of its subfolders.</span></span> <span data-ttu-id="e1f39-108">如果您支持查看的远程邮件，使用状态表，以查看由传输提供程序的活动和 MAPI 后台处理程序注册。</span><span class="sxs-lookup"><span data-stu-id="e1f39-108">If you support the viewing of remote messages, register with the status table to observe activity by transport providers and the MAPI spooler.</span></span> 
  
<span data-ttu-id="e1f39-109">但是，它并不总是首选而不是对象通知使用表通知。</span><span class="sxs-lookup"><span data-stu-id="e1f39-109">However, it is not always preferable to use table notifications instead of object notifications.</span></span> <span data-ttu-id="e1f39-110">监控的文件夹中的消息数的变化时的示例可能需要您的客户端注册对象通知的文件夹，而不是在该文件夹所实现的表格。</span><span class="sxs-lookup"><span data-stu-id="e1f39-110">Monitoring changes in the number of messages in a folder is an example of when your client might need to register for object notifications on a folder rather than on a table implemented by the folder.</span></span>
  

