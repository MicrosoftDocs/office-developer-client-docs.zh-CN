---
title: MAPI 接收文件夹
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2e1287a3-0f15-4d9a-b7ee-738fce9cd51f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a305b9c9ea2802ac63a22118b55274bcdff23617
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569006"
---
# <a name="mapi-receive-folders"></a><span data-ttu-id="61594-103">MAPI 接收文件夹</span><span class="sxs-lookup"><span data-stu-id="61594-103">MAPI Receive Folders</span></span>

  
  
<span data-ttu-id="61594-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61594-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61594-105">接收文件夹包含特定邮件类别的入站的邮件。</span><span class="sxs-lookup"><span data-stu-id="61594-105">A receive folder holds inbound messages of a particular message class.</span></span> <span data-ttu-id="61594-106">接收由客户端、 消息存储提供程序，或 MAPI，则可以建立关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-106">Receive folder associations can be established by clients, by the message store provider, or by MAPI.</span></span> <span data-ttu-id="61594-107">MAPI 有两个默认的接收文件夹： 消息存储库的根文件夹和人际邮件 (IPM) 子树的收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-107">MAPI has two default receive folders: the root folder of the message store, and the Inbox folder of the interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="61594-108">消息存储库的根文件夹是默认接收所有进程间通信 (IPC) 邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-108">The root folder of the message store is the default receive folder for all interprocess communication (IPC) messages.</span></span>
  
 <span data-ttu-id="61594-109">每个新的消息存储由 MAPI 创建收件箱文件夹，并作为默认接收的以下邮件类的文件夹：</span><span class="sxs-lookup"><span data-stu-id="61594-109">The Inbox folder is created by MAPI for every new message store and acts as the default receive folder for the following message classes:</span></span> 
  
- <span data-ttu-id="61594-110">IPM 邮件类。</span><span class="sxs-lookup"><span data-stu-id="61594-110">The IPM message class.</span></span>
    
- <span data-ttu-id="61594-111">报告邮件类。</span><span class="sxs-lookup"><span data-stu-id="61594-111">The report message class.</span></span>
    
- <span data-ttu-id="61594-112">为空，或者缺少的类。</span><span class="sxs-lookup"><span data-stu-id="61594-112">An empty, or missing, class.</span></span>
    
<span data-ttu-id="61594-113">所有报告的邮件，甚至发送响应 IPC 消息，都放在收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-113">All report messages, even those sent in response to an IPC message, are placed in the Inbox folder.</span></span> <span data-ttu-id="61594-114">处理其自己的报告的 IPC 客户端应用程序必须明确添加用于报表的特定类的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-114">IPC client applications that process their own reports must explicitly add a receive folder for the particular class of report.</span></span> <span data-ttu-id="61594-115">例如，如果希望接收邮件类 IPC 客户端。Paper.Order，它应调用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)方法建立与类 Report.IPC.Paper.Order 报告的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-115">For example, if a client expects to receive messages with the class IPC.Paper.Order, it should call the [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) method to establish a receive folder for reports with the class Report.IPC.Paper.Order.</span></span> 
  
<span data-ttu-id="61594-116">接收基于分层组织的邮件类关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-116">Receive folder associations are based on the hierarchical organization of message classes.</span></span> <span data-ttu-id="61594-117">客户端可以显式建立的接收文件夹和邮件类之间的关联或使用 MAPI 默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-117">Clients can explicitly establish an association between a receive folder and a message class or use the MAPI default receive folders.</span></span> <span data-ttu-id="61594-118">通常情况下，客户端指定接收邮件的基类的一个文件夹和所有及其子类别。</span><span class="sxs-lookup"><span data-stu-id="61594-118">Typically, clients designate one folder to receive messages for a base class and all of its subclasses.</span></span> <span data-ttu-id="61594-119">例如，典型的客户端会建立的邮件类**MyClass**与的关联。</span><span class="sxs-lookup"><span data-stu-id="61594-119">For example, a typical client would establish an association for messages with the class **MyClass**.</span></span> <span data-ttu-id="61594-120">然后如果客户端收到邮件类**MyClass.Home**或**MyClass.Home.Kitchen.Computer**，这些消息将转到基类**MyClass**的接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="61594-120">Then if the client received messages with classes **MyClass.Home** or **MyClass.Home.Kitchen.Computer**, these messages would go to the receive folder for the base class, **MyClass**.</span></span>
  
<span data-ttu-id="61594-121">有三个消息存储方法用于处理客户端接收文件夹：</span><span class="sxs-lookup"><span data-stu-id="61594-121">There are three message store methods that clients use to work with receive folders:</span></span>
  
- [<span data-ttu-id="61594-122">IMsgStore::GetReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="61594-122">IMsgStore::GetReceiveFolderTable</span></span>](imsgstore-getreceivefoldertable.md)
    
- [<span data-ttu-id="61594-123">IMsgStore::GetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="61594-123">IMsgStore::GetReceiveFolder</span></span>](imsgstore-getreceivefolder.md)
    
- [<span data-ttu-id="61594-124">IMsgStore::SetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="61594-124">IMsgStore::SetReceiveFolder</span></span>](imsgstore-setreceivefolder.md)
    
<span data-ttu-id="61594-125">接收文件夹表是所有消息存储建立的接收文件夹信息的列表。</span><span class="sxs-lookup"><span data-stu-id="61594-125">The receive folder table is a listing of information about all of the receive folders established for a message store.</span></span> <span data-ttu-id="61594-126">其所需的列集包括邮件类、 记录键和项标识符。</span><span class="sxs-lookup"><span data-stu-id="61594-126">Its required column set includes the message class, record key, and entry identifier.</span></span>
  
<span data-ttu-id="61594-127">若要检索特定的邮件类的接收文件夹，客户端，请传递给[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)方法的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="61594-127">To retrieve a receive folder for a particular message class, clients pass the message class string to the [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) method.</span></span> <span data-ttu-id="61594-128">消息存储提供程序返回的相应文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="61594-128">The message store provider returns an entry identifier for the corresponding folder.</span></span> <span data-ttu-id="61594-129">若要实现**GetReceiveFolder**，消息存储提供程序应使用的算法的选择其关联的邮件类别匹配指定的邮件类的最长可能前缀的文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-129">To implement **GetReceiveFolder**, a message store provider should use an algorithm that selects the folder whose associated message class matches the longest possible prefix of the specified message class.</span></span> <span data-ttu-id="61594-130">例如，假定消息存储已接收文件夹和邮件类在以下之间关联其接收文件夹表：</span><span class="sxs-lookup"><span data-stu-id="61594-130">For example, assume the message store has the following associations between receive folders and message classes in its receive folder table:</span></span>
  
- <span data-ttu-id="61594-131">**IPM**消息放在收件箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="61594-131">**IPM** messages are placed in the Inbox folder.</span></span> 
    
- <span data-ttu-id="61594-132">**IPM。Note.Sample**消息放在示例文件夹中。</span><span class="sxs-lookup"><span data-stu-id="61594-132">**IPM.Note.Sample** messages are placed in the Samples folder.</span></span> 
    
<span data-ttu-id="61594-133">下表显示了如何使用各种类的邮件将被路由至相应的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-133">The following table shows how messages with various classes would be routed to the appropriate receive folder.</span></span>
  
|<span data-ttu-id="61594-134">**入站的邮件类**</span><span class="sxs-lookup"><span data-stu-id="61594-134">**Inbound message class**</span></span>|<span data-ttu-id="61594-135">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="61594-135">**Receive folder**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61594-136">**IPM。Note.Sample.Simple**</span><span class="sxs-lookup"><span data-stu-id="61594-136">**IPM.Note.Sample.Simple**</span></span> <br/> |<span data-ttu-id="61594-137">示例文件夹</span><span class="sxs-lookup"><span data-stu-id="61594-137">Samples folder</span></span>  <br/> |
|<span data-ttu-id="61594-138">**IPM。注释**</span><span class="sxs-lookup"><span data-stu-id="61594-138">**IPM.Note**</span></span> <br/> |<span data-ttu-id="61594-139">收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="61594-139">Inbox folder</span></span>  <br/> |
|<span data-ttu-id="61594-140">**IPM。考勤卡**</span><span class="sxs-lookup"><span data-stu-id="61594-140">**IPM.Timecard**</span></span> <br/> |<span data-ttu-id="61594-141">收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="61594-141">Inbox folder</span></span>  <br/> |
|<span data-ttu-id="61594-142">**IPM。Note.Sample.Simple.Totally**</span><span class="sxs-lookup"><span data-stu-id="61594-142">**IPM.Note.Sample.Simple.Totally**</span></span> <br/> |<span data-ttu-id="61594-143">示例文件夹</span><span class="sxs-lookup"><span data-stu-id="61594-143">Samples folder</span></span>  <br/> |
   
<span data-ttu-id="61594-144">客户端调用**SetReceiveFolder**方法以使特定邮件类别之间的显式关联和接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-144">Clients call the **SetReceiveFolder** method to make an explicit association between a particular message class and receive folder.</span></span> <span data-ttu-id="61594-145">邮件传递到空的邮件类，MAPI 将消息置于定义空类的前缀的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-145">When a message is delivered to an empty message class, MAPI places the message in the receive folder that is defined for a prefix of the empty class.</span></span> <span data-ttu-id="61594-146">例如，如果您的客户端已建立的邮件的接收文件夹类**IPM**和邮件类**IPM。Note.Test**是送达，此消息将被置于**IPM**邮件类的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-146">For example, if your client has a receive folder established for messages with class **IPM** and a message with class **IPM.Note.Test** is delivered, this message will be placed in the receive folder for the **IPM** message class.</span></span> 
  
<span data-ttu-id="61594-147">在调用**SetReceiveFolder**，客户端通常传递邮件类字符串和新的项标识符接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-147">In calling **SetReceiveFolder**, clients typically pass a message class string and the entry identifier of the new receive folder.</span></span> <span data-ttu-id="61594-148">但是，客户端可以传递中一个或两个这些参数为 NULL。</span><span class="sxs-lookup"><span data-stu-id="61594-148">However, clients can pass in NULL for one or both of these parameters.</span></span> <span data-ttu-id="61594-149">下表介绍的邮件类和条目标识符参数指定 NULL 结果的行为。</span><span class="sxs-lookup"><span data-stu-id="61594-149">The following table describes the behavior that results from specifying NULL for the message class and entry identifier parameters.</span></span> 
  
|<span data-ttu-id="61594-150">**_SetReceiveFolder_参数**</span><span class="sxs-lookup"><span data-stu-id="61594-150">**_SetReceiveFolder_ parameter**</span></span>|<span data-ttu-id="61594-151">**结果行为**</span><span class="sxs-lookup"><span data-stu-id="61594-151">**Resulting behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61594-152">设置为 NULL 的项标识符</span><span class="sxs-lookup"><span data-stu-id="61594-152">Entry identifier set to NULL</span></span>  <br/> |<span data-ttu-id="61594-153">消息存储库中删除指定之间的关联邮件类和其现有的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-153">The message store deletes the association between the specified message class and its existing receive folder.</span></span> <span data-ttu-id="61594-154">新接收未建立文件夹。</span><span class="sxs-lookup"><span data-stu-id="61594-154">A new receive folder is not established.</span></span>  <br/> <span data-ttu-id="61594-155">后续调用**GetReceiveFolder**与此邮件类将返回的邮件类; 前缀的接收文件夹对于新邮件存储区， **GetReceiveFolder**将返回收件箱 IPM 子树。</span><span class="sxs-lookup"><span data-stu-id="61594-155">Subsequent calls to **GetReceiveFolder** with this message class will return the receive folder for a prefix of the message class; for new message stores, **GetReceiveFolder** will return the Inbox in the IPM subtree.</span></span>  <br/> |
|<span data-ttu-id="61594-156">邮件类设置为 NULL</span><span class="sxs-lookup"><span data-stu-id="61594-156">Message class set to NULL</span></span>  <br/> |<span data-ttu-id="61594-157">消息存储到指定的文件夹更改为空邮件类关联。</span><span class="sxs-lookup"><span data-stu-id="61594-157">The message store changes the association for the empty message class to the indicated folder.</span></span> <span data-ttu-id="61594-158">其类是否则无法识别的传入消息将转到此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="61594-158">Incoming messages whose class is otherwise unrecognized will go to this folder.</span></span>  <br/> |
|<span data-ttu-id="61594-159">设置为 NULL 的项标识符和邮件类</span><span class="sxs-lookup"><span data-stu-id="61594-159">Entry identifier and message class set to NULL</span></span>  <br/> |<span data-ttu-id="61594-160">消息存储删除的空邮件类的类/文件夹关联。</span><span class="sxs-lookup"><span data-stu-id="61594-160">The message store deletes the class/folder association for the empty message class.</span></span> <span data-ttu-id="61594-161">因为它通常会导致消息存储库，看不到客户端的文件夹的根文件夹中放置的入站邮件，不应为 NULL，设置这两个参数。</span><span class="sxs-lookup"><span data-stu-id="61594-161">You should not set both parameters to NULL, because it typically results in inbound messages being placed in the root folder of the message store, a folder that is invisible to the client.</span></span>  <br/> |
   
<span data-ttu-id="61594-162">尽管邮件类绝不应为空，但可能会发生空邮件类。</span><span class="sxs-lookup"><span data-stu-id="61594-162">Although a message's class should never be empty, an empty message class can occur.</span></span> <span data-ttu-id="61594-163">消息存储库的责任分配的邮件类**IPM**到新的出站邮件包含一个空的类;是分配**IPM 的传输提供程序的责任。注意**作为有任何空类的入站邮件的类。</span><span class="sxs-lookup"><span data-stu-id="61594-163">It is the message store's responsibility to assign the message class to **IPM** for new outbound messages that have an empty class; it is the transport provider's responsibility to assign **IPM.Note** as the class for inbound messages that have any empty class.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="61594-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61594-164">See also</span></span>



[<span data-ttu-id="61594-165">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="61594-165">MAPI Folders</span></span>](mapi-folders.md)

