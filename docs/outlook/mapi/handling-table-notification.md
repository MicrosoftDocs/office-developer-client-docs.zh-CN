---
title: 处理表通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: edc9bc71-4885-4783-b465-0bafa20eff73
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6e6c24c3836f295054c1880dc506c5051078a9ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299487"
---
# <a name="handling-table-notification"></a><span data-ttu-id="f0a20-103">处理表通知</span><span class="sxs-lookup"><span data-stu-id="f0a20-103">Handling table notification</span></span>

<span data-ttu-id="f0a20-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0a20-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0a20-105">作为直接注册到建议源对象 (如文件夹或邮件用户) 的替代方法, 客户端可以为内容或层次结构表注册通知。</span><span class="sxs-lookup"><span data-stu-id="f0a20-105">As an alternative to registering directly with an advise source object, such as a folder or a messaging user, a client can register for notifications on a contents or hierarchy table.</span></span> <span data-ttu-id="f0a20-106">通过内容或层次结构表跟踪对通讯簿条目、文件夹和邮件所做的更改可能比通过单个对象更简单、更直接。</span><span class="sxs-lookup"><span data-stu-id="f0a20-106">Tracking changes to address book entries, folders, and messages through a contents or hierarchy table can be simpler and more straightforward than through individual objects.</span></span> 

<span data-ttu-id="f0a20-107">例如, 可以对文件夹的层次结构表调用[IMAPITable:: Advise](imapitable-advise.md) , 以发现它的一个子文件夹发生更改的情况。</span><span class="sxs-lookup"><span data-stu-id="f0a20-107">For example, you can call [IMAPITable::Advise](imapitable-advise.md) on a folder's hierarchy table to discover when changes occur to one of its subfolders.</span></span> <span data-ttu-id="f0a20-108">如果您支持查看远程消息, 请向状态表注册, 以观察传输提供程序和 MAPI 后台处理程序的活动。</span><span class="sxs-lookup"><span data-stu-id="f0a20-108">If you support the viewing of remote messages, register with the status table to observe activity by transport providers and the MAPI spooler.</span></span> 
  
<span data-ttu-id="f0a20-109">但是, 并不总是最好使用表通知而不是对象通知。</span><span class="sxs-lookup"><span data-stu-id="f0a20-109">However, it is not always preferable to use table notifications instead of object notifications.</span></span> <span data-ttu-id="f0a20-110">如果您的客户端可能需要在文件夹上注册对象通知, 而不是在由该文件夹实现的表上注册对象通知, 则监视文件夹中的邮件数量的更改就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="f0a20-110">Monitoring changes in the number of messages in a folder is an example of when your client might need to register for object notifications on a folder rather than on a table implemented by the folder.</span></span>
  

