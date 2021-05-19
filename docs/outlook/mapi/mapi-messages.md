---
title: MAPI 邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 417c113f-bd98-4515-85d1-09db7fc3a227
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f1d1895cc6f9e65929781cb0e966873d2bce197c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423375"
---
# <a name="mapi-messages"></a><span data-ttu-id="e8199-103">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="e8199-103">MAPI Messages</span></span>

  
  
<span data-ttu-id="e8199-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8199-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8199-105">邮件是通过 MAPI 后台处理程序和服务提供商通过邮件系统从一个客户端应用程序传输到另一个客户端应用程序的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="e8199-105">Messages are MAPI objects that are transmitted from one client application to another through the MAPI spooler and service providers by way of a messaging system.</span></span> <span data-ttu-id="e8199-106">MAPI 中的几乎每个组件都使用消息。</span><span class="sxs-lookup"><span data-stu-id="e8199-106">Nearly every component in MAPI works with messages.</span></span> <span data-ttu-id="e8199-107">除了复制邮件并将其从一个文件夹移动到另一个文件夹之外，客户端还允许用户创建、保存、发送和删除邮件。</span><span class="sxs-lookup"><span data-stu-id="e8199-107">Clients let users create, save, send, and delete messages in addition to copy and move them from one folder to another.</span></span> <span data-ttu-id="e8199-108">邮件存储提供程序负责邮件管理和将邮件传递至 MAPI 后台处理程序或传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="e8199-108">Message store providers are responsible for message management and for delivering messages to the MAPI spooler or a transport provider.</span></span> <span data-ttu-id="e8199-109">MAPI 后台处理程序将邮件移动到适当的传输提供程序，而传输提供程序处理邮件在邮件系统之间传递和接收的邮件，并设置收件人和邮件选项属性。</span><span class="sxs-lookup"><span data-stu-id="e8199-109">The MAPI spooler moves messages to an appropriate transport provider, whereas transport providers handle the delivery and receipt of messages to and from a messaging system and set recipient and message option properties.</span></span> <span data-ttu-id="e8199-110">通讯簿提供程序间接处理邮件，支持描述邮件收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="e8199-110">Address book providers work indirectly with messages, supporting properties that describe message recipients.</span></span>
  
<span data-ttu-id="e8199-111">邮件存储在整个邮件存储的文件夹中，通常是在 IPM 文件夹的 (文件夹中) 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8199-111">Messages are stored in folders throughout a message store, typically folders created in the interpersonal message (IPM) root folder.</span></span> <span data-ttu-id="e8199-112">邮件通常存储在与标准 IPM 收件箱、已发送项目、已删除邮件和发件箱文件夹相同的级别，或存储在层次结构中的较低级别。</span><span class="sxs-lookup"><span data-stu-id="e8199-112">Messages are usually stored at the same level as the standard IPM Inbox, Sent Items, Deleted Items, and Outbox folders, or at lower levels in the hierarchy.</span></span> <span data-ttu-id="e8199-113">但是，邮件也可以存储在 IPM 子树外部。</span><span class="sxs-lookup"><span data-stu-id="e8199-113">However, messages can also be stored outside the IPM subtree.</span></span>
  
<span data-ttu-id="e8199-114">在标准 IPM 子树中创建的邮件具有标准 (内容，即客户端应用程序应用程序用户可以看到) 。</span><span class="sxs-lookup"><span data-stu-id="e8199-114">Messages created in the standard IPM subtree have standard contents (that is, contents that are visible to the user of a client application).</span></span> <span data-ttu-id="e8199-115">备注和报告是包含标准内容的邮件示例。</span><span class="sxs-lookup"><span data-stu-id="e8199-115">Notes and reports are examples of messages that have standard contents.</span></span> <span data-ttu-id="e8199-116">还可使用关联的内容或典型客户端中不可见的内容创建消息。</span><span class="sxs-lookup"><span data-stu-id="e8199-116">Messages can also be created with associated contents, or contents that are not visible in the typical client.</span></span> <span data-ttu-id="e8199-117">文件夹支持两个不同的内容表来保存不同类型的邮件：标准邮件的标准内容表和关联邮件的关联内容表。</span><span class="sxs-lookup"><span data-stu-id="e8199-117">Folders support two different contents tables to hold the different types of messages: a standard contents table for standard messages, and an associated contents table for associated messages.</span></span> <span data-ttu-id="e8199-118">由于 MAPI 不为关联邮件的内容设置标准，因此它们可以包含任意信息。</span><span class="sxs-lookup"><span data-stu-id="e8199-118">Because MAPI does not set standards for the content of associated messages, they can contain arbitrary information.</span></span> 
  
<span data-ttu-id="e8199-119">邮件可以具有与之关联的其他数据（格式为文件、其他邮件或 OLE 对象）。</span><span class="sxs-lookup"><span data-stu-id="e8199-119">A message can have additional data — in the form of a file, another message, or an OLE object — associated with it.</span></span> <span data-ttu-id="e8199-120">此附加数据（称为附件）显示为图标，或者对于 RTF 邮件，显示为邮件文本中的图元文件。</span><span class="sxs-lookup"><span data-stu-id="e8199-120">This additional data, which is called an attachment, appears either as an icon or, for an RTF message, as a metafile in the message text.</span></span> <span data-ttu-id="e8199-121">邮件可以有零个、一个或多个附件。</span><span class="sxs-lookup"><span data-stu-id="e8199-121">A message can have zero, one, or many attachments.</span></span> <span data-ttu-id="e8199-122">附件始终随邮件一起传输。</span><span class="sxs-lookup"><span data-stu-id="e8199-122">Attachments are always transmitted with the message.</span></span>
  
<span data-ttu-id="e8199-123">传输的邮件具有一个或多个收件人 (与特定邮件系统邮箱关联的) 。</span><span class="sxs-lookup"><span data-stu-id="e8199-123">A message that is transmitted has one or more recipients (addresses that are associated with a particular messaging system).</span></span> <span data-ttu-id="e8199-124">某些收件人是属于当前配置文件中的通讯簿提供程序的容器中的条目;创建其他收件人仅仅是为了传输邮件。</span><span class="sxs-lookup"><span data-stu-id="e8199-124">Some recipients are entries in a container that belongs to an address book provider in the current profile; other recipients are created only to transmit the message.</span></span> <span data-ttu-id="e8199-125">由于必须通过与其关联的邮件访问收件人和附件，因此邮件的收件人和附件称为其子对象。</span><span class="sxs-lookup"><span data-stu-id="e8199-125">Because recipients and attachments must be accessed through the message with which they are associated, a message's recipients and attachments are known as its subobjects.</span></span> 
  
<span data-ttu-id="e8199-126">邮件存储提供程序通过以下三个接口中的方法支持邮件、附件和收件人：</span><span class="sxs-lookup"><span data-stu-id="e8199-126">Message store providers support messages, attachments, and recipients through methods in three interfaces:</span></span> 
  
|<span data-ttu-id="e8199-127">**接口**</span><span class="sxs-lookup"><span data-stu-id="e8199-127">**Interface**</span></span>|<span data-ttu-id="e8199-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="e8199-128">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e8199-129">IMessage</span><span class="sxs-lookup"><span data-stu-id="e8199-129">IMessage</span></span>](imessageimapiprop.md) <br/> |<span data-ttu-id="e8199-130">管理附件和收件人、发送邮件、设置读取状态。</span><span class="sxs-lookup"><span data-stu-id="e8199-130">Manages attachments and recipients, sends messages, sets read status.</span></span>  <br/> |
|[<span data-ttu-id="e8199-131">IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="e8199-131">IMAPIFolder</span></span>](imapifolderimapicontainer.md) <br/> |<span data-ttu-id="e8199-132">创建、复制和移动邮件和子文件夹，并管理邮件状态。</span><span class="sxs-lookup"><span data-stu-id="e8199-132">Creates, copies, and moves messages and subfolders and manages message status.</span></span>  <br/> |
|[<span data-ttu-id="e8199-133">IAttach</span><span class="sxs-lookup"><span data-stu-id="e8199-133">IAttach</span></span>](iattachimapiprop.md) <br/> |<span data-ttu-id="e8199-134">管理附件属性。</span><span class="sxs-lookup"><span data-stu-id="e8199-134">Manages attachment properties.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e8199-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8199-135">See also</span></span>



[<span data-ttu-id="e8199-136">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="e8199-136">MAPI Application Development</span></span>](mapi-application-development.md)

