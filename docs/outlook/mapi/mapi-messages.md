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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345855"
---
# <a name="mapi-messages"></a><span data-ttu-id="f2d77-103">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="f2d77-103">MAPI Messages</span></span>

  
  
<span data-ttu-id="f2d77-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2d77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2d77-105">邮件是 mapi 对象, 这些对象通过 mapi 后台处理程序和服务提供程序通过邮件系统从一个客户端应用程序传输到另一个客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="f2d77-105">Messages are MAPI objects that are transmitted from one client application to another through the MAPI spooler and service providers by way of a messaging system.</span></span> <span data-ttu-id="f2d77-106">MAPI 中的每个组件几乎都可处理邮件。</span><span class="sxs-lookup"><span data-stu-id="f2d77-106">Nearly every component in MAPI works with messages.</span></span> <span data-ttu-id="f2d77-107">除了复制邮件并将其从一个文件夹移动到另一个文件夹之外, 客户端还允许用户创建、保存、发送和删除邮件。</span><span class="sxs-lookup"><span data-stu-id="f2d77-107">Clients let users create, save, send, and delete messages in addition to copy and move them from one folder to another.</span></span> <span data-ttu-id="f2d77-108">邮件存储提供程序负责邮件管理以及将邮件传递到 MAPI 后台处理程序或传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="f2d77-108">Message store providers are responsible for message management and for delivering messages to the MAPI spooler or a transport provider.</span></span> <span data-ttu-id="f2d77-109">MAPI 后台处理程序将邮件移动到相应的传输提供程序, 而传输提供程序处理邮件发送到邮件系统和从邮件系统接收邮件以及设置收件人和邮件选项属性。</span><span class="sxs-lookup"><span data-stu-id="f2d77-109">The MAPI spooler moves messages to an appropriate transport provider, whereas transport providers handle the delivery and receipt of messages to and from a messaging system and set recipient and message option properties.</span></span> <span data-ttu-id="f2d77-110">通讯簿提供程序可间接处理邮件, 支持描述邮件收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="f2d77-110">Address book providers work indirectly with messages, supporting properties that describe message recipients.</span></span>
  
<span data-ttu-id="f2d77-111">邮件存储在整个邮件存储区中的文件夹中, 通常是在人际邮件 (IPM) 根文件夹中创建的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f2d77-111">Messages are stored in folders throughout a message store, typically folders created in the interpersonal message (IPM) root folder.</span></span> <span data-ttu-id="f2d77-112">邮件通常存储在与标准 IPM 收件箱、已发送邮件、已删除邮件和发件箱文件夹或层次结构的较低级别上的级别相同的级别。</span><span class="sxs-lookup"><span data-stu-id="f2d77-112">Messages are usually stored at the same level as the standard IPM Inbox, Sent Items, Deleted Items, and Outbox folders, or at lower levels in the hierarchy.</span></span> <span data-ttu-id="f2d77-113">但是, 邮件也可以存储在 IPM 子树外部。</span><span class="sxs-lookup"><span data-stu-id="f2d77-113">However, messages can also be stored outside the IPM subtree.</span></span>
  
<span data-ttu-id="f2d77-114">在标准 IPM 子树中创建的邮件具有标准内容 (即, 对客户端应用程序用户可见的内容)。</span><span class="sxs-lookup"><span data-stu-id="f2d77-114">Messages created in the standard IPM subtree have standard contents (that is, contents that are visible to the user of a client application).</span></span> <span data-ttu-id="f2d77-115">注释和报告是具有标准内容的邮件示例。</span><span class="sxs-lookup"><span data-stu-id="f2d77-115">Notes and reports are examples of messages that have standard contents.</span></span> <span data-ttu-id="f2d77-116">也可以使用关联的内容或在典型客户端中不可见的内容来创建邮件。</span><span class="sxs-lookup"><span data-stu-id="f2d77-116">Messages can also be created with associated contents, or contents that are not visible in the typical client.</span></span> <span data-ttu-id="f2d77-117">文件夹支持两个不同的内容表, 以保存不同类型的邮件: 标准邮件的标准内容表, 以及关联邮件的关联目录表。</span><span class="sxs-lookup"><span data-stu-id="f2d77-117">Folders support two different contents tables to hold the different types of messages: a standard contents table for standard messages, and an associated contents table for associated messages.</span></span> <span data-ttu-id="f2d77-118">由于 MAPI 不会为关联邮件的内容设置标准, 因此它们可以包含任意信息。</span><span class="sxs-lookup"><span data-stu-id="f2d77-118">Because MAPI does not set standards for the content of associated messages, they can contain arbitrary information.</span></span> 
  
<span data-ttu-id="f2d77-119">一封邮件可以包含与之关联的其他数据, 如文件的格式、另一封邮件或 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="f2d77-119">A message can have additional data — in the form of a file, another message, or an OLE object — associated with it.</span></span> <span data-ttu-id="f2d77-120">此附加数据称为附件, 作为图标或 RTF 邮件显示为邮件文本中的图元文件。</span><span class="sxs-lookup"><span data-stu-id="f2d77-120">This additional data, which is called an attachment, appears either as an icon or, for an RTF message, as a metafile in the message text.</span></span> <span data-ttu-id="f2d77-121">一封邮件可以包含零个、一个或多个附件。</span><span class="sxs-lookup"><span data-stu-id="f2d77-121">A message can have zero, one, or many attachments.</span></span> <span data-ttu-id="f2d77-122">附件总是随邮件一起传输。</span><span class="sxs-lookup"><span data-stu-id="f2d77-122">Attachments are always transmitted with the message.</span></span>
  
<span data-ttu-id="f2d77-123">传输的邮件包含一个或多个收件人 (与特定邮件系统相关联的地址)。</span><span class="sxs-lookup"><span data-stu-id="f2d77-123">A message that is transmitted has one or more recipients (addresses that are associated with a particular messaging system).</span></span> <span data-ttu-id="f2d77-124">某些收件人是属于当前配置文件中的通讯簿提供程序的容器中的条目。其他收件人只是为了传输邮件而创建的。</span><span class="sxs-lookup"><span data-stu-id="f2d77-124">Some recipients are entries in a container that belongs to an address book provider in the current profile; other recipients are created only to transmit the message.</span></span> <span data-ttu-id="f2d77-125">因为收件人和附件必须通过与其关联的邮件来访问, 所以邮件的收件人和附件称为其子控件。</span><span class="sxs-lookup"><span data-stu-id="f2d77-125">Because recipients and attachments must be accessed through the message with which they are associated, a message's recipients and attachments are known as its subobjects.</span></span> 
  
<span data-ttu-id="f2d77-126">邮件存储提供程序通过三个接口中的方法支持邮件、附件和收件人:</span><span class="sxs-lookup"><span data-stu-id="f2d77-126">Message store providers support messages, attachments, and recipients through methods in three interfaces:</span></span> 
  
|<span data-ttu-id="f2d77-127">**接口**</span><span class="sxs-lookup"><span data-stu-id="f2d77-127">**Interface**</span></span>|<span data-ttu-id="f2d77-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="f2d77-128">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f2d77-129">IMessage</span><span class="sxs-lookup"><span data-stu-id="f2d77-129">IMessage</span></span>](imessageimapiprop.md) <br/> |<span data-ttu-id="f2d77-130">管理附件和收件人, 发送邮件, 设置阅读状态。</span><span class="sxs-lookup"><span data-stu-id="f2d77-130">Manages attachments and recipients, sends messages, sets read status.</span></span>  <br/> |
|[<span data-ttu-id="f2d77-131">IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="f2d77-131">IMAPIFolder</span></span>](imapifolderimapicontainer.md) <br/> |<span data-ttu-id="f2d77-132">创建、复制和移动邮件和子文件夹, 并管理邮件状态。</span><span class="sxs-lookup"><span data-stu-id="f2d77-132">Creates, copies, and moves messages and subfolders and manages message status.</span></span>  <br/> |
|[<span data-ttu-id="f2d77-133">IAttach</span><span class="sxs-lookup"><span data-stu-id="f2d77-133">IAttach</span></span>](iattachimapiprop.md) <br/> |<span data-ttu-id="f2d77-134">管理附件属性。</span><span class="sxs-lookup"><span data-stu-id="f2d77-134">Manages attachment properties.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f2d77-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2d77-135">See also</span></span>



[<span data-ttu-id="f2d77-136">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="f2d77-136">MAPI Application Development</span></span>](mapi-application-development.md)

