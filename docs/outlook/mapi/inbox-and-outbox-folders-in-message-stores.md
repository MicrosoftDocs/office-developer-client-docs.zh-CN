---
title: 收件箱和发件箱文件夹中邮件存储
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
# <a name="inbox-and-outbox-folders-in-message-stores"></a><span data-ttu-id="b6789-103">收件箱和发件箱文件夹中邮件存储</span><span class="sxs-lookup"><span data-stu-id="b6789-103">Inbox and Outbox Folders in Message Stores</span></span>

  
  
<span data-ttu-id="b6789-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b6789-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b6789-105">若要将默认邮件存储区，消息存储提供程序必须实现收件箱并发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="b6789-105">To be the default message store, a message store provider must implement Inbox and Outbox folders.</span></span> <span data-ttu-id="b6789-106">他们通常存储在消息存储的 IPM 子树。</span><span class="sxs-lookup"><span data-stu-id="b6789-106">They are typically stored in the IPM subtree of a message store.</span></span> <span data-ttu-id="b6789-107">这些文件夹是特殊的它们被指定为邮件传递到并发送，但没有特殊功能都是必需的它们的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b6789-107">These folders are special in that they are designated as the folders that messages are delivered to and sent from, but no special functionality is required of them.</span></span> <span data-ttu-id="b6789-108">发送和接收消息发生通过客户端应用程序、 MAPI 后台处理程序，和的消息存储提供程序之间定义的调用序列。</span><span class="sxs-lookup"><span data-stu-id="b6789-108">Sending and receiving messages happens by way of defined call sequences between client applications, the MAPI spooler, and the message store provider.</span></span> <span data-ttu-id="b6789-109">收件箱和发件箱文件夹是只用于期间那些举行邮件的文件夹调用序列。</span><span class="sxs-lookup"><span data-stu-id="b6789-109">The Inbox and Outbox folders are simply folders that are used to hold messages during those call sequences.</span></span> <span data-ttu-id="b6789-110">重要的一点不是文件夹是特殊，或偶数收件箱和发件箱; 已命名重要的一点是，消息存储提供程序使用这些作为其支持的一部分的发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="b6789-110">The important point is not that the folders are special, or even that they are named Inbox and Outbox; the important point is that the message store provider uses them as part of its support for sending and receiving messages.</span></span>
  
<span data-ttu-id="b6789-111">若要支持接收邮件，消息存储提供程序必须实现的[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)和[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b6789-111">To support receiving messages, the message store provider must implement the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) and [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) methods.</span></span> <span data-ttu-id="b6789-112">有关详细信息，请参阅[通过使用消息存储提供程序接收的消息](receiving-messages-by-using-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="b6789-112">For more information, see [Receiving Messages by Using Message Store Providers](receiving-messages-by-using-message-store-providers.md).</span></span>
  
<span data-ttu-id="b6789-113">若要支持发送消息，消息存储提供程序必须支持的[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)方法，除了过程消息发送过程中使用 MAPI 后台处理程序的其他方法。</span><span class="sxs-lookup"><span data-stu-id="b6789-113">To support sending messages, the message store provider must support the [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md) method, in addition to the other methods used by the MAPI spooler during the message sending process.</span></span> <span data-ttu-id="b6789-114">消息存储库的传出队列不必对应于消息存储库文件夹树中的任意位置实际文件夹。</span><span class="sxs-lookup"><span data-stu-id="b6789-114">A message store's outgoing queue does not have to correspond to an actual folder anywhere in the message store's folder tree.</span></span> <span data-ttu-id="b6789-115">但是，就的消息存储提供程序，在发件箱文件夹中中, 显示的传出消息队列的内容，如果有习惯。</span><span class="sxs-lookup"><span data-stu-id="b6789-115">However, it is customary for a message store provider to show the contents of the outgoing message queue in the Outbox folder, if there is one.</span></span> <span data-ttu-id="b6789-116">这样做为客户端应用程序提供方便地指示用户已发送的邮件的状态，因为可以一起消息存储区中的所有其他文件夹显示发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="b6789-116">Doing so gives client applications a convenient way to indicate the status of messages that the user has sent, because an Outbox folder can be displayed along with all the other folders in a message store.</span></span> <span data-ttu-id="b6789-117">有关详细信息，请参阅[通过使用消息存储提供程序发送的邮件](sending-messages-by-using-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="b6789-117">For more information, see [Sending Messages by Using Message Store Providers](sending-messages-by-using-message-store-providers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6789-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6789-118">See also</span></span>



[<span data-ttu-id="b6789-119">消息存储库中实现文件夹</span><span class="sxs-lookup"><span data-stu-id="b6789-119">Implementing Folders in Message Stores</span></span>](implementing-folders-in-message-stores.md)

