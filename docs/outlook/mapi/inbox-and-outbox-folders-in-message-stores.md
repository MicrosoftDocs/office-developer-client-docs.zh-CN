---
title: 邮件存储中的收件箱和发件箱文件夹
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
# <a name="inbox-and-outbox-folders-in-message-stores"></a><span data-ttu-id="82a60-103">邮件存储中的收件箱和发件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="82a60-103">Inbox and Outbox Folders in Message Stores</span></span>

  
  
<span data-ttu-id="82a60-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82a60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82a60-105">若要作为默认邮件存储，邮件存储提供程序必须实现收件箱和发件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="82a60-105">To be the default message store, a message store provider must implement Inbox and Outbox folders.</span></span> <span data-ttu-id="82a60-106">它们通常存储在邮件存储的 IPM 子树中。</span><span class="sxs-lookup"><span data-stu-id="82a60-106">They are typically stored in the IPM subtree of a message store.</span></span> <span data-ttu-id="82a60-107">这些文件夹很特殊，因为它们被指定为邮件传递到和发送自的文件夹，但不需要任何特殊功能。</span><span class="sxs-lookup"><span data-stu-id="82a60-107">These folders are special in that they are designated as the folders that messages are delivered to and sent from, but no special functionality is required of them.</span></span> <span data-ttu-id="82a60-108">发送和接收邮件的方式为在客户端应用程序、MAPI 后台处理程序和邮件存储提供程序之间定义调用序列。</span><span class="sxs-lookup"><span data-stu-id="82a60-108">Sending and receiving messages happens by way of defined call sequences between client applications, the MAPI spooler, and the message store provider.</span></span> <span data-ttu-id="82a60-109">"收件箱"和"发件箱"文件夹只是用于在这些调用序列期间保留邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="82a60-109">The Inbox and Outbox folders are simply folders that are used to hold messages during those call sequences.</span></span> <span data-ttu-id="82a60-110">重要的是，这些文件夹不是特殊的，或者它们被命名为"收件箱"和"发件箱";重要的是，邮件存储提供程序会使用它们作为对发送和接收邮件的支持的一部分。</span><span class="sxs-lookup"><span data-stu-id="82a60-110">The important point is not that the folders are special, or even that they are named Inbox and Outbox; the important point is that the message store provider uses them as part of its support for sending and receiving messages.</span></span>
  
<span data-ttu-id="82a60-111">若要支持接收邮件，邮件存储提供程序必须实现 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 和 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="82a60-111">To support receiving messages, the message store provider must implement the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) and [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) methods.</span></span> <span data-ttu-id="82a60-112">有关详细信息，请参阅 [使用邮件存储提供程序接收邮件](receiving-messages-by-using-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="82a60-112">For more information, see [Receiving Messages by Using Message Store Providers](receiving-messages-by-using-message-store-providers.md).</span></span>
  
<span data-ttu-id="82a60-113">为了支持发送邮件，邮件存储提供程序必须支持 [IMsgStore：：GetOutgoingQueue](imsgstore-getoutgoingqueue.md) 方法，以及 MAPI 后台处理程序在邮件发送过程中使用的其他方法。</span><span class="sxs-lookup"><span data-stu-id="82a60-113">To support sending messages, the message store provider must support the [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md) method, in addition to the other methods used by the MAPI spooler during the message sending process.</span></span> <span data-ttu-id="82a60-114">邮件存储的传出队列无需对应于邮件存储的文件夹树中的任意位置的实际文件夹。</span><span class="sxs-lookup"><span data-stu-id="82a60-114">A message store's outgoing queue does not have to correspond to an actual folder anywhere in the message store's folder tree.</span></span> <span data-ttu-id="82a60-115">但是，邮件存储提供程序在发件箱文件夹中显示传出邮件队列的内容（如果有）是一种希望。</span><span class="sxs-lookup"><span data-stu-id="82a60-115">However, it is customary for a message store provider to show the contents of the outgoing message queue in the Outbox folder, if there is one.</span></span> <span data-ttu-id="82a60-116">这样做使客户端应用程序可以方便地指示用户已发送的邮件的状态，因为发件箱文件夹可以与邮件存储中的所有其他文件夹一起显示。</span><span class="sxs-lookup"><span data-stu-id="82a60-116">Doing so gives client applications a convenient way to indicate the status of messages that the user has sent, because an Outbox folder can be displayed along with all the other folders in a message store.</span></span> <span data-ttu-id="82a60-117">有关详细信息，请参阅 [使用邮件存储提供程序发送邮件](sending-messages-by-using-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="82a60-117">For more information, see [Sending Messages by Using Message Store Providers](sending-messages-by-using-message-store-providers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="82a60-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82a60-118">See also</span></span>



[<span data-ttu-id="82a60-119">实现邮件存储中的文件夹</span><span class="sxs-lookup"><span data-stu-id="82a60-119">Implementing Folders in Message Stores</span></span>](implementing-folders-in-message-stores.md)

