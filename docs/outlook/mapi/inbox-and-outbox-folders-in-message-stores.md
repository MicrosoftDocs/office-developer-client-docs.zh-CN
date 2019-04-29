---
title: 邮件存储区中的收件箱和发件箱文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8e4ce129-137d-4618-80a6-88781a578d01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 95a2b7b9bac11404817fb6848d58c45251c141f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414240"
---
# <a name="inbox-and-outbox-folders-in-message-stores"></a>邮件存储区中的收件箱和发件箱文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要成为默认邮件存储区, 邮件存储提供程序必须实现 "收件箱" 和 "发件箱" 文件夹。 它们通常存储在邮件存储区的 IPM 子树中。 这些文件夹是特殊的, 因为它们被指定为邮件传递到和发送的文件夹, 但不需要特殊的功能。 通过在客户端应用程序、MAPI 后台处理程序和邮件存储提供程序之间定义呼叫序列的方式发送和接收邮件。 "收件箱" 和 "发件箱" 文件夹只是用于在这些呼叫序列中保存邮件的文件夹。 重要的一点是, 这些文件夹是特殊的, 甚至它们被命名为 "收件箱" 和 "发件箱";重要的是, 邮件存储区提供程序将其作为支持发送和接收邮件的一部分使用。
  
若要支持接收邮件, 邮件存储提供程序必须实现[IMsgStore:: GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)和[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)方法。 有关详细信息, 请参阅[使用邮件存储提供程序接收邮件](receiving-messages-by-using-message-store-providers.md)。
  
若要支持发送邮件, 邮件存储提供程序必须支持[IMsgStore:: GetOutgoingQueue](imsgstore-getoutgoingqueue.md)方法, 以及邮件发送过程中 MAPI 后台处理程序使用的其他方法。 邮件存储的传出队列并不一定对应于邮件存储区的文件夹树中的实际文件夹。 但是, 邮件存储提供程序在 "发件箱" 文件夹中显示传出邮件队列的内容 (如果有的话) 是习惯的。 这样做使客户端应用程序能够方便地指示用户已发送的邮件的状态, 因为 "发件箱" 文件夹可以与邮件存储区中的所有其他文件夹一起显示。 有关详细信息, 请参阅[使用邮件存储提供程序发送邮件](sending-messages-by-using-message-store-providers.md)。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储中的文件夹](implementing-folders-in-message-stores.md)

