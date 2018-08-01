---
title: 邮件存储区的收件箱和发件箱文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8e4ce129-137d-4618-80a6-88781a578d01
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2bd71ee4fca53fbf3d309cbaf9d33835b84c0c2d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775930"
---
# <a name="inbox-and-outbox-folders-in-message-stores"></a>邮件存储区的收件箱和发件箱文件夹

  
  
**适用于**： Outlook 
  
若要将默认邮件存储区，消息存储提供程序必须实现收件箱并发件箱文件夹。 他们通常存储在消息存储的 IPM 子树。 这些文件夹是特殊的它们被指定为邮件传递到并发送，但没有特殊功能都是必需的它们的文件夹。 发送和接收消息发生通过客户端应用程序、 MAPI 后台处理程序，和的消息存储提供程序之间定义的调用序列。 收件箱和发件箱文件夹是只用于期间那些举行邮件的文件夹调用序列 （英文）。 重要的一点不是文件夹是特殊，或偶数收件箱和发件箱; 已命名重要的一点是，消息存储提供程序使用这些作为其支持的一部分的发送和接收消息。
  
若要支持接收邮件，消息存储提供程序必须实现的[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)和[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)方法。 有关详细信息，请参阅[通过使用消息存储提供程序接收的消息](receiving-messages-by-using-message-store-providers.md)。
  
若要支持发送消息，消息存储提供程序必须支持的[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)方法，除了过程消息发送过程中使用 MAPI 后台处理程序的其他方法。 消息存储库的传出队列不必对应于消息存储库文件夹树中的任意位置实际文件夹。 但是，就的消息存储提供程序，在发件箱文件夹中中, 显示的传出消息队列的内容，如果有习惯。 这样做为客户端应用程序提供方便地指示用户已发送的邮件的状态，因为可以一起消息存储区中的所有其他文件夹显示发件箱文件夹。 有关详细信息，请参阅[通过使用消息存储提供程序发送的邮件](sending-messages-by-using-message-store-providers.md)。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储区中的文件夹](implementing-folders-in-message-stores.md)

