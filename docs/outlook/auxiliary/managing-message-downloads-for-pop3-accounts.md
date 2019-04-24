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
# <a name="managing-message-downloads-for-pop3-accounts"></a>管理邮件的 POP3 帐户下载

本部分介绍如何Outlook POP3 提供程序使用的唯一 ID 列表 （UIDL) 历史记录 POP3 帐户标识提供程序已下载或删除从 POP3 服务器，以避免多次下载相同的邮件的邮件。
  
## <a name="introduction-to-pop"></a>POP 简介

邮局协议 (POP) 指定的电子邮件客户端 （如Outlook从邮件服务器下载电子邮件的应用层协议。它允许用户下载到本地设备 （如智能手机或计算机），并可以保持的一份电子邮件服务器上的副本，或将其删除。该协议支持只有一个邮件客户端每次连接到邮箱。它指定仅如何检索但不是从邮件服务器发送电子邮件。当使用 POP 时，邮件客户端通常要检查新的电子邮件，连接到邮件服务器，只需下载新邮件，并且不会连接到服务器，以获取新邮件通知的时间量。POP 支持仅电子邮件但不是其他项目类型 （如联系人和约会，除非将它们封装在一封电子邮件。POP3 是协议的第 3 版。
  
POP 帐户的邮件都由唯一标识符 (Uid) 来标识。在服务器保留邮件的电子邮件客户端使用 UIDL 命令检索的 UIDL 映射相关联的每个消息，发送到该邮箱的 UID。客户端还获取已下载或删除在该客户端上的收件箱的邮件的 UIDL 历史记录。根据 UIDL 历史记录，客户机可以确定哪些邮件是新用户并且应下载。

- [查找 pop3 帐户的邮件下载历史记录](locating-the-message-download-history-for-a-pop3-account.md): 本主题介绍邮件客户端如何访问[PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性, 以获取 pop3 帐户的客户端收件箱中的邮件的 UIDL 历史记录。 
    
- [分析 pop3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md): 本主题介绍如何分析 pop3 BLOB, 该 BLOB 代表 pop3 帐户的客户端收件箱中的邮件的 UIDL 历史记录, 以标识已在其上下载或删除的邮件上级.
    
## <a name="see-also"></a>另请参阅

- [Outlook 帐户管理](outlook-account-management.md)    
- [查找一个 POP3 帐户的消息下载历史记录](locating-the-message-download-history-for-a-pop3-account.md) 
- [分析 POP3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)   
- [PROP_POP_LEAVE_ON_SERVER](prop_pop_leave_on_server.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)    
- [属性 （帐户管理 API）](properties-account-management-api.md)
    

