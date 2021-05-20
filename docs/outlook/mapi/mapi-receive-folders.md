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
ms.openlocfilehash: b22b8641d55037d3755fc9ae32b97455223bbd12
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431937"
---
# <a name="mapi-receive-folders"></a><span data-ttu-id="c832c-103">MAPI 接收文件夹</span><span class="sxs-lookup"><span data-stu-id="c832c-103">MAPI Receive Folders</span></span>

  
  
<span data-ttu-id="c832c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c832c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c832c-105">接收文件夹保留特定邮件类的入站邮件。</span><span class="sxs-lookup"><span data-stu-id="c832c-105">A receive folder holds inbound messages of a particular message class.</span></span> <span data-ttu-id="c832c-106">接收文件夹关联可以通过客户端、邮件存储提供程序或 MAPI 建立。</span><span class="sxs-lookup"><span data-stu-id="c832c-106">Receive folder associations can be established by clients, by the message store provider, or by MAPI.</span></span> <span data-ttu-id="c832c-107">MAPI 有两个默认接收文件夹：邮件存储的根文件夹和 IPM 子树 (邮件) 收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-107">MAPI has two default receive folders: the root folder of the message store, and the Inbox folder of the interpersonal message (IPM) subtree.</span></span> <span data-ttu-id="c832c-108">邮件存储的根文件夹是 IPC 传输的所有进程间通信的默认 () 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-108">The root folder of the message store is the default receive folder for all interprocess communication (IPC) messages.</span></span>
  
 <span data-ttu-id="c832c-109">"收件箱"文件夹由 MAPI 针对每个新邮件存储创建，并充当以下邮件类的默认接收文件夹：</span><span class="sxs-lookup"><span data-stu-id="c832c-109">The Inbox folder is created by MAPI for every new message store and acts as the default receive folder for the following message classes:</span></span> 
  
- <span data-ttu-id="c832c-110">IPM 邮件类。</span><span class="sxs-lookup"><span data-stu-id="c832c-110">The IPM message class.</span></span>
    
- <span data-ttu-id="c832c-111">报告邮件类。</span><span class="sxs-lookup"><span data-stu-id="c832c-111">The report message class.</span></span>
    
- <span data-ttu-id="c832c-112">一个空或缺失的类。</span><span class="sxs-lookup"><span data-stu-id="c832c-112">An empty, or missing, class.</span></span>
    
<span data-ttu-id="c832c-113">所有报告邮件（甚至是为响应 IPC 邮件而发送的报告邮件）都放置在"收件箱"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c832c-113">All report messages, even those sent in response to an IPC message, are placed in the Inbox folder.</span></span> <span data-ttu-id="c832c-114">处理自己的报告的 IPC 客户端应用程序必须明确添加特定报告类的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-114">IPC client applications that process their own reports must explicitly add a receive folder for the particular class of report.</span></span> <span data-ttu-id="c832c-115">例如，如果客户端希望接收具有类 IPC 的邮件。Paper.Order，它应调用 [IMsgStore：：SetReceiveFolder](imsgstore-setreceivefolder.md) 方法来为具有类 Report.IPC.Paper.Order 的报告建立接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-115">For example, if a client expects to receive messages with the class IPC.Paper.Order, it should call the [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) method to establish a receive folder for reports with the class Report.IPC.Paper.Order.</span></span> 
  
<span data-ttu-id="c832c-116">接收文件夹关联基于邮件类的分层组织。</span><span class="sxs-lookup"><span data-stu-id="c832c-116">Receive folder associations are based on the hierarchical organization of message classes.</span></span> <span data-ttu-id="c832c-117">客户端可以在接收文件夹和邮件类之间显式建立关联，或使用 MAPI 默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-117">Clients can explicitly establish an association between a receive folder and a message class or use the MAPI default receive folders.</span></span> <span data-ttu-id="c832c-118">通常，客户端指定一个文件夹来接收基类及其所有子类的邮件。</span><span class="sxs-lookup"><span data-stu-id="c832c-118">Typically, clients designate one folder to receive messages for a base class and all of its subclasses.</span></span> <span data-ttu-id="c832c-119">例如，典型的客户端会为具有 MyClass 类的邮件 **建立关联**。</span><span class="sxs-lookup"><span data-stu-id="c832c-119">For example, a typical client would establish an association for messages with the class **MyClass**.</span></span> <span data-ttu-id="c832c-120">然后，如果客户端收到具有 MyClass.Home 或 **MyClass.Home.Kitchen.Computer** 类的邮件，这些邮件将转到基类 **MyClass** 的接收文件夹。 </span><span class="sxs-lookup"><span data-stu-id="c832c-120">Then if the client received messages with classes **MyClass.Home** or **MyClass.Home.Kitchen.Computer**, these messages would go to the receive folder for the base class, **MyClass**.</span></span>
  
<span data-ttu-id="c832c-121">客户端使用三种邮件存储方法处理接收文件夹：</span><span class="sxs-lookup"><span data-stu-id="c832c-121">There are three message store methods that clients use to work with receive folders:</span></span>
  
- [<span data-ttu-id="c832c-122">IMsgStore::GetReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="c832c-122">IMsgStore::GetReceiveFolderTable</span></span>](imsgstore-getreceivefoldertable.md)
    
- [<span data-ttu-id="c832c-123">IMsgStore::GetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="c832c-123">IMsgStore::GetReceiveFolder</span></span>](imsgstore-getreceivefolder.md)
    
- [<span data-ttu-id="c832c-124">IMsgStore::SetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="c832c-124">IMsgStore::SetReceiveFolder</span></span>](imsgstore-setreceivefolder.md)
    
<span data-ttu-id="c832c-125">接收文件夹表是有关为邮件存储建立的所有接收文件夹的信息列表。</span><span class="sxs-lookup"><span data-stu-id="c832c-125">The receive folder table is a listing of information about all of the receive folders established for a message store.</span></span> <span data-ttu-id="c832c-126">其所需的列集包括邮件类、记录键和条目标识符。</span><span class="sxs-lookup"><span data-stu-id="c832c-126">Its required column set includes the message class, record key, and entry identifier.</span></span>
  
<span data-ttu-id="c832c-127">若要检索特定邮件类的接收文件夹，客户端将邮件类字符串传递给 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c832c-127">To retrieve a receive folder for a particular message class, clients pass the message class string to the [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) method.</span></span> <span data-ttu-id="c832c-128">邮件存储提供程序返回相应文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="c832c-128">The message store provider returns an entry identifier for the corresponding folder.</span></span> <span data-ttu-id="c832c-129">若要实现 **GetReceiveFolder，** 邮件存储提供程序应该使用一种算法，选择其关联邮件类与指定邮件类的最长前缀匹配的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-129">To implement **GetReceiveFolder**, a message store provider should use an algorithm that selects the folder whose associated message class matches the longest possible prefix of the specified message class.</span></span> <span data-ttu-id="c832c-130">例如，假定邮件存储在其接收文件夹表中的接收文件夹和邮件类之间具有以下关联：</span><span class="sxs-lookup"><span data-stu-id="c832c-130">For example, assume the message store has the following associations between receive folders and message classes in its receive folder table:</span></span>
  
- <span data-ttu-id="c832c-131">**IPM** 邮件放置在"收件箱"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c832c-131">**IPM** messages are placed in the Inbox folder.</span></span> 
    
- <span data-ttu-id="c832c-132">**IPM。Note.Sample** messages are placed in the Samples folder.</span><span class="sxs-lookup"><span data-stu-id="c832c-132">**IPM.Note.Sample** messages are placed in the Samples folder.</span></span> 
    
<span data-ttu-id="c832c-133">下表显示了如何将具有各种类的邮件路由到相应的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-133">The following table shows how messages with various classes would be routed to the appropriate receive folder.</span></span>
  
|<span data-ttu-id="c832c-134">**入站邮件类**</span><span class="sxs-lookup"><span data-stu-id="c832c-134">**Inbound message class**</span></span>|<span data-ttu-id="c832c-135">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="c832c-135">**Receive folder**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c832c-136">**IPM。Note.Sample.Simple**</span><span class="sxs-lookup"><span data-stu-id="c832c-136">**IPM.Note.Sample.Simple**</span></span> <br/> |<span data-ttu-id="c832c-137">Samples 文件夹</span><span class="sxs-lookup"><span data-stu-id="c832c-137">Samples folder</span></span>  <br/> |
|<span data-ttu-id="c832c-138">**IPM。注意**</span><span class="sxs-lookup"><span data-stu-id="c832c-138">**IPM.Note**</span></span> <br/> |<span data-ttu-id="c832c-139">收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="c832c-139">Inbox folder</span></span>  <br/> |
|<span data-ttu-id="c832c-140">**IPM。Timecard**</span><span class="sxs-lookup"><span data-stu-id="c832c-140">**IPM.Timecard**</span></span> <br/> |<span data-ttu-id="c832c-141">收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="c832c-141">Inbox folder</span></span>  <br/> |
|<span data-ttu-id="c832c-142">**IPM。Note.Sample.Simple.Totally**</span><span class="sxs-lookup"><span data-stu-id="c832c-142">**IPM.Note.Sample.Simple.Totally**</span></span> <br/> |<span data-ttu-id="c832c-143">Samples 文件夹</span><span class="sxs-lookup"><span data-stu-id="c832c-143">Samples folder</span></span>  <br/> |
   
<span data-ttu-id="c832c-144">客户端调用 **SetReceiveFolder** 方法，以建立特定邮件类和接收文件夹之间的显式关联。</span><span class="sxs-lookup"><span data-stu-id="c832c-144">Clients call the **SetReceiveFolder** method to make an explicit association between a particular message class and receive folder.</span></span> <span data-ttu-id="c832c-145">当邮件传递到空邮件类时，MAPI 将邮件添加到为空类的前缀定义的接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c832c-145">When a message is delivered to an empty message class, MAPI places the message in the receive folder that is defined for a prefix of the empty class.</span></span> <span data-ttu-id="c832c-146">例如，如果客户端为具有类 IPM 的邮件和具有类 **IPM** 的邮件建立了接收 **文件夹。注意.测试** 已传递，此邮件将放在 **IPM** 邮件类的接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c832c-146">For example, if your client has a receive folder established for messages with class **IPM** and a message with class **IPM.Note.Test** is delivered, this message will be placed in the receive folder for the **IPM** message class.</span></span> 
  
<span data-ttu-id="c832c-147">在调用 **SetReceiveFolder** 时，客户端通常会传递邮件类字符串和新接收文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="c832c-147">In calling **SetReceiveFolder**, clients typically pass a message class string and the entry identifier of the new receive folder.</span></span> <span data-ttu-id="c832c-148">但是，客户端可以针对其中一个或两个参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="c832c-148">However, clients can pass in NULL for one or both of these parameters.</span></span> <span data-ttu-id="c832c-149">下表描述了为邮件类和条目标识符参数指定 NULL 时导致的行为。</span><span class="sxs-lookup"><span data-stu-id="c832c-149">The following table describes the behavior that results from specifying NULL for the message class and entry identifier parameters.</span></span> 
  
|<span data-ttu-id="c832c-150">**_SetReceiveFolder_ 参数**</span><span class="sxs-lookup"><span data-stu-id="c832c-150">**_SetReceiveFolder_ parameter**</span></span>|<span data-ttu-id="c832c-151">**生成的行为**</span><span class="sxs-lookup"><span data-stu-id="c832c-151">**Resulting behavior**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c832c-152">条目标识符设置为 NULL</span><span class="sxs-lookup"><span data-stu-id="c832c-152">Entry identifier set to NULL</span></span>  <br/> |<span data-ttu-id="c832c-153">邮件存储删除指定邮件类及其现有接收文件夹之间的关联。</span><span class="sxs-lookup"><span data-stu-id="c832c-153">The message store deletes the association between the specified message class and its existing receive folder.</span></span> <span data-ttu-id="c832c-154">未建立新的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-154">A new receive folder is not established.</span></span>  <br/> <span data-ttu-id="c832c-155">对此邮件 **类的 GetReceiveFolder** 的后续调用将返回邮件类前缀的接收文件夹;对于新邮件存储 **，GetReceiveFolder** 将返回 IPM 子树中的收件箱。</span><span class="sxs-lookup"><span data-stu-id="c832c-155">Subsequent calls to **GetReceiveFolder** with this message class will return the receive folder for a prefix of the message class; for new message stores, **GetReceiveFolder** will return the Inbox in the IPM subtree.</span></span>  <br/> |
|<span data-ttu-id="c832c-156">邮件类设置为 NULL</span><span class="sxs-lookup"><span data-stu-id="c832c-156">Message class set to NULL</span></span>  <br/> |<span data-ttu-id="c832c-157">邮件存储将空邮件类的关联更改到指示的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-157">The message store changes the association for the empty message class to the indicated folder.</span></span> <span data-ttu-id="c832c-158">其类无法识别的传入邮件将转到此文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-158">Incoming messages whose class is otherwise unrecognized will go to this folder.</span></span>  <br/> |
|<span data-ttu-id="c832c-159">条目标识符和邮件类设置为 NULL</span><span class="sxs-lookup"><span data-stu-id="c832c-159">Entry identifier and message class set to NULL</span></span>  <br/> |<span data-ttu-id="c832c-160">邮件存储会删除空邮件类的类/文件夹关联。</span><span class="sxs-lookup"><span data-stu-id="c832c-160">The message store deletes the class/folder association for the empty message class.</span></span> <span data-ttu-id="c832c-161">不应将两个参数都设置为 NULL，因为它通常会导致入站邮件被置于邮件存储的根文件夹中，即对客户端不可见的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c832c-161">You should not set both parameters to NULL, because it typically results in inbound messages being placed in the root folder of the message store, a folder that is invisible to the client.</span></span>  <br/> |
   
<span data-ttu-id="c832c-162">尽管邮件的类永远不应为空，但会出现空邮件类。</span><span class="sxs-lookup"><span data-stu-id="c832c-162">Although a message's class should never be empty, an empty message class can occur.</span></span> <span data-ttu-id="c832c-163">邮件存储负责为具有空类的新出站邮件将邮件类分配给 **IPM;** 分配 IPM 是传输提供程序 **的责任。请注意** ，作为具有任何空类的入站邮件的类。</span><span class="sxs-lookup"><span data-stu-id="c832c-163">It is the message store's responsibility to assign the message class to **IPM** for new outbound messages that have an empty class; it is the transport provider's responsibility to assign **IPM.Note** as the class for inbound messages that have any empty class.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c832c-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c832c-164">See also</span></span>



[<span data-ttu-id="c832c-165">MAPI 文件夹</span><span class="sxs-lookup"><span data-stu-id="c832c-165">MAPI Folders</span></span>](mapi-folders.md)

