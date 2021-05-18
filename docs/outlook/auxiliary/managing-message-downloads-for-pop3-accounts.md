---
title: 管理邮件的 POP3 帐户下载
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b4218aa6-1591-49db-9782-f286135fc79a
description: 本部分介绍如何Outlook POP3 提供程序使用的唯一 ID 列表 （UIDL) 历史记录 POP3 帐户标识提供程序已下载或删除从 POP3 服务器，以避免多次下载相同的邮件的邮件。
ms.openlocfilehash: 35c50d83c317ebefa52fd9bfcb348c8411a06f25
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322244"
---
# <a name="managing-message-downloads-for-pop3-accounts"></a><span data-ttu-id="827f0-103">管理邮件的 POP3 帐户下载</span><span class="sxs-lookup"><span data-stu-id="827f0-103">Managing message downloads for POP3 accounts</span></span>

<span data-ttu-id="827f0-104">本部分介绍如何Outlook POP3 提供程序使用的唯一 ID 列表 （UIDL) 历史记录 POP3 帐户标识提供程序已下载或删除从 POP3 服务器，以避免多次下载相同的邮件的邮件。</span><span class="sxs-lookup"><span data-stu-id="827f0-104">This section describes how the POP3 provider of Outlook uses the Unique ID Listing (UIDL) history on a POP3 account to identify messages that the provider has downloaded or deleted from the POP3 server, to avoid downloading the same message more than once.</span></span>
  
## <a name="introduction-to-pop"></a><span data-ttu-id="827f0-105">POP 简介</span><span class="sxs-lookup"><span data-stu-id="827f0-105">Introduction to POP</span></span>

<span data-ttu-id="827f0-p101">邮局协议 (POP) 指定的电子邮件客户端 （如Outlook从邮件服务器下载电子邮件的应用层协议。它允许用户下载到本地设备 （如智能手机或计算机），并可以保持的一份电子邮件服务器上的副本，或将其删除。该协议支持只有一个邮件客户端每次连接到邮箱。它指定仅如何检索但不是从邮件服务器发送电子邮件。当使用 POP 时，邮件客户端通常要检查新的电子邮件，连接到邮件服务器，只需下载新邮件，并且不会连接到服务器，以获取新邮件通知的时间量。POP 支持仅电子邮件但不是其他项目类型 （如联系人和约会，除非将它们封装在一封电子邮件。POP3 是协议的第 3 版。</span><span class="sxs-lookup"><span data-stu-id="827f0-p101">The Post Office Protocol (POP) specifies an application layer protocol for an email client such as Outlook to download email messages from a mail server. It allows a user to download a copy of an email message to a local device (such as a smart phone or computer), and either leave a copy on the server or delete it. The protocol supports only one mail client to be connected to the mailbox at one time. It specifies only how to retrieve but not send email messages from the mail server. When using POP, a mail client typically has to check for new email messages, connects to the mail server for only the amount of time it takes to download new messages, and does not stay connected to the server to get new mail notifications. POP supports only email messages but not other item types such as contacts and appointments unless they are encapsulated in an email. POP3 is version 3 of the protocol.</span></span>
  
<span data-ttu-id="827f0-p102">POP 帐户的邮件都由唯一标识符 (Uid) 来标识。在服务器保留邮件的电子邮件客户端使用 UIDL 命令检索的 UIDL 映射相关联的每个消息，发送到该邮箱的 UID。客户端还获取已下载或删除在该客户端上的收件箱的邮件的 UIDL 历史记录。根据 UIDL 历史记录，客户机可以确定哪些邮件是新用户并且应下载。</span><span class="sxs-lookup"><span data-stu-id="827f0-p102">Messages for a POP account are identified by unique identifiers (UIDs). An email client that leaves mail on the server uses the UIDL command to retrieve the UIDL map that associates each message that has been delivered to the mailbox to its UID. The client also gets the UIDL history for messages that have been downloaded or deleted for the Inbox on that client. Based on the UIDL history, the client can determine which messages are new and should be downloaded.</span></span>

- <span data-ttu-id="827f0-117">[找到 POP3](locating-the-message-download-history-for-a-pop3-account.md)帐户的邮件下载历史记录 ：本主题介绍邮件客户端如何访问 [PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx) 属性，获取 POP3 帐户的客户端收件箱中邮件的 UIDL 历史记录。</span><span class="sxs-lookup"><span data-stu-id="827f0-117">[Locating the message download history for a POP3 account](locating-the-message-download-history-for-a-pop3-account.md): This topic describes how a mail client accesses the [PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx) property to get the UIDL history for messages in the client Inbox of a POP3 account.</span></span> 
    
- <span data-ttu-id="827f0-118">分析[POP3](parsing-the-message-download-history-for-a-pop3-account.md)帐户的邮件下载历史记录：本主题介绍如何分析表示 POP3 帐户的客户端收件箱中邮件的 UIDL 历史记录的 POP3 BLOB，以确定已在该帐户上下载或删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="827f0-118">[Parsing the message download history for a POP3 account](parsing-the-message-download-history-for-a-pop3-account.md): This topic describes how to parse the POP3 BLOB that represents the UIDL history for messages in the client Inbox of a POP3 account, to identify the messages that have been downloaded or deleted on that account.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="827f0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="827f0-119">See also</span></span>

- [<span data-ttu-id="827f0-120">Outlook 帐户管理</span><span class="sxs-lookup"><span data-stu-id="827f0-120">Outlook account management</span></span>](outlook-account-management.md)    
- [<span data-ttu-id="827f0-121">查找一个 POP3 帐户的消息下载历史记录</span><span class="sxs-lookup"><span data-stu-id="827f0-121">Locating the message download history for a POP3 account</span></span>](locating-the-message-download-history-for-a-pop3-account.md) 
- [<span data-ttu-id="827f0-122">分析 POP3 帐户的邮件下载历史记录</span><span class="sxs-lookup"><span data-stu-id="827f0-122">Parsing the message download history for a POP3 account</span></span>](parsing-the-message-download-history-for-a-pop3-account.md)   
- [<span data-ttu-id="827f0-123">PROP_POP_LEAVE_ON_SERVER</span><span class="sxs-lookup"><span data-stu-id="827f0-123">PROP_POP_LEAVE_ON_SERVER</span></span>](prop_pop_leave_on_server.md)  
- [<span data-ttu-id="827f0-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="827f0-124">Constants (Account management API)</span></span>](constants-account-management-api.md)    
- [<span data-ttu-id="827f0-125">属性 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="827f0-125">Properties (Account management API)</span></span>](properties-account-management-api.md)
    

