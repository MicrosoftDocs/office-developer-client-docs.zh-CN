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
ms.openlocfilehash: 1146fa0441d0b55a7610368324489bd3a6bb24e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776269"
---
# <a name="mapi-messages"></a><span data-ttu-id="1087b-103">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="1087b-103">MAPI Messages</span></span>

  
  
<span data-ttu-id="1087b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1087b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1087b-105">邮件是传输到另一个通过 MAPI 后台处理程序和服务提供商通过邮件系统的一台客户端应用程序的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="1087b-105">Messages are MAPI objects that are transmitted from one client application to another through the MAPI spooler and service providers by way of a messaging system.</span></span> <span data-ttu-id="1087b-106">MAPI 中的几乎在每个组件处理的邮件。</span><span class="sxs-lookup"><span data-stu-id="1087b-106">Nearly every component in MAPI works with messages.</span></span> <span data-ttu-id="1087b-107">客户端让用户创建、 保存、 发送和删除此外，复制并将其从一个文件夹移动到另一个邮件。</span><span class="sxs-lookup"><span data-stu-id="1087b-107">Clients let users create, save, send, and delete messages in addition to copy and move them from one folder to another.</span></span> <span data-ttu-id="1087b-108">消息存储提供程序负责为邮件管理和邮件传递到 MAPI 后台处理程序或传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="1087b-108">Message store providers are responsible for message management and for delivering messages to the MAPI spooler or a transport provider.</span></span> <span data-ttu-id="1087b-109">MAPI 后台处理程序会将邮件移动到适当的传输提供程序，而传输提供程序处理的传送和接收邮件与邮件系统，然后设置收件人和消息选项属性。</span><span class="sxs-lookup"><span data-stu-id="1087b-109">The MAPI spooler moves messages to an appropriate transport provider, whereas transport providers handle the delivery and receipt of messages to and from a messaging system and set recipient and message option properties.</span></span> <span data-ttu-id="1087b-110">通讯簿提供程序处理间接邮件，支持描述邮件收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="1087b-110">Address book providers work indirectly with messages, supporting properties that describe message recipients.</span></span>
  
<span data-ttu-id="1087b-111">消息存储在整个邮件存储区中，通常人际邮件 (IPM) 根文件夹中创建的文件夹的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1087b-111">Messages are stored in folders throughout a message store, typically folders created in the interpersonal message (IPM) root folder.</span></span> <span data-ttu-id="1087b-112">邮件通常存储在相同的级别标准 IPM 收件箱、 已发送邮件、 已删除邮件和发件箱文件夹或层次结构中的较低级别。</span><span class="sxs-lookup"><span data-stu-id="1087b-112">Messages are usually stored at the same level as the standard IPM Inbox, Sent Items, Deleted Items, and Outbox folders, or at lower levels in the hierarchy.</span></span> <span data-ttu-id="1087b-113">但是，也可以 IPM 子树外部存储消息。</span><span class="sxs-lookup"><span data-stu-id="1087b-113">However, messages can also be stored outside the IPM subtree.</span></span>
  
<span data-ttu-id="1087b-114">在标准 IPM 子树中创建的邮件都具有标准内容 （即，对客户端应用程序的用户可见的内容）。</span><span class="sxs-lookup"><span data-stu-id="1087b-114">Messages created in the standard IPM subtree have standard contents (that is, contents that are visible to the user of a client application).</span></span> <span data-ttu-id="1087b-115">注释和报告是具有标准内容的邮件的示例。</span><span class="sxs-lookup"><span data-stu-id="1087b-115">Notes and reports are examples of messages that have standard contents.</span></span> <span data-ttu-id="1087b-116">消息也可以创建与关联的内容或在典型的客户端中不可见的内容。</span><span class="sxs-lookup"><span data-stu-id="1087b-116">Messages can also be created with associated contents, or contents that are not visible in the typical client.</span></span> <span data-ttu-id="1087b-117">文件夹支持两个不同内容表来保存不同类型的邮件： 一种标准内容的标准邮件和关联邮件关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="1087b-117">Folders support two different contents tables to hold the different types of messages: a standard contents table for standard messages, and an associated contents table for associated messages.</span></span> <span data-ttu-id="1087b-118">MAPI 不设置关联的消息的内容的标准，因为它们可包含任意信息。</span><span class="sxs-lookup"><span data-stu-id="1087b-118">Because MAPI does not set standards for the content of associated messages, they can contain arbitrary information.</span></span> 
  
<span data-ttu-id="1087b-119">指定在邮件有其他数据 — 的文件，另一条消息或 OLE 对象形式 — 与之关联。</span><span class="sxs-lookup"><span data-stu-id="1087b-119">A message can have additional data — in the form of a file, another message, or an OLE object — associated with it.</span></span> <span data-ttu-id="1087b-120">此附加的数据，该数据库称为附件，显示为图标或，RTF 邮件，为图元文件消息文本中。</span><span class="sxs-lookup"><span data-stu-id="1087b-120">This additional data, which is called an attachment, appears either as an icon or, for an RTF message, as a metafile in the message text.</span></span> <span data-ttu-id="1087b-121">零、 一个或多个附件，可以有一条消息。</span><span class="sxs-lookup"><span data-stu-id="1087b-121">A message can have zero, one, or many attachments.</span></span> <span data-ttu-id="1087b-122">始终为邮件传输附件。</span><span class="sxs-lookup"><span data-stu-id="1087b-122">Attachments are always transmitted with the message.</span></span>
  
<span data-ttu-id="1087b-123">传输邮件有一个或多个收件人 （与特定的邮件系统关联的地址）。</span><span class="sxs-lookup"><span data-stu-id="1087b-123">A message that is transmitted has one or more recipients (addresses that are associated with a particular messaging system).</span></span> <span data-ttu-id="1087b-124">某些收件人的通讯簿提供程序中的当前配置文件; 所属的容器中的条目创建其他收件人仅将邮件传输。</span><span class="sxs-lookup"><span data-stu-id="1087b-124">Some recipients are entries in a container that belongs to an address book provider in the current profile; other recipients are created only to transmit the message.</span></span> <span data-ttu-id="1087b-125">由于必须通过关联它们是邮件访问收件人和附件，邮件的收件人和附件称为及其子对象。</span><span class="sxs-lookup"><span data-stu-id="1087b-125">Because recipients and attachments must be accessed through the message with which they are associated, a message's recipients and attachments are known as its subobjects.</span></span> 
  
<span data-ttu-id="1087b-126">消息存储提供程序支持通过中三个接口方法的邮件、 附件和收件人：</span><span class="sxs-lookup"><span data-stu-id="1087b-126">Message store providers support messages, attachments, and recipients through methods in three interfaces:</span></span> 
  
|<span data-ttu-id="1087b-127">**接口**</span><span class="sxs-lookup"><span data-stu-id="1087b-127">**Interface**</span></span>|<span data-ttu-id="1087b-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="1087b-128">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1087b-129">IMessage</span><span class="sxs-lookup"><span data-stu-id="1087b-129">IMessage</span></span>](imessageimapiprop.md) <br/> |<span data-ttu-id="1087b-130">管理附件和收件人发送邮件、 设置读取的状态。</span><span class="sxs-lookup"><span data-stu-id="1087b-130">Manages attachments and recipients, sends messages, sets read status.</span></span>  <br/> |
|[<span data-ttu-id="1087b-131">IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="1087b-131">IMAPIFolder</span></span>](imapifolderimapicontainer.md) <br/> |<span data-ttu-id="1087b-132">创建、 复制，并将移动消息和子文件夹和管理邮件状态。</span><span class="sxs-lookup"><span data-stu-id="1087b-132">Creates, copies, and moves messages and subfolders and manages message status.</span></span>  <br/> |
|[<span data-ttu-id="1087b-133">IAttach</span><span class="sxs-lookup"><span data-stu-id="1087b-133">IAttach</span></span>](iattachimapiprop.md) <br/> |<span data-ttu-id="1087b-134">管理附件属性。</span><span class="sxs-lookup"><span data-stu-id="1087b-134">Manages attachment properties.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1087b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1087b-135">See also</span></span>



[<span data-ttu-id="1087b-136">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="1087b-136">MAPI Application Development</span></span>](mapi-application-development.md)

