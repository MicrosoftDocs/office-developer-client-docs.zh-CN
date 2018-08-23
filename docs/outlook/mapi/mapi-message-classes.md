---
title: MAPI 邮件类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 64ef2bbb-585c-4908-8ad4-a1c954057e9b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eecbbb3b806ecaee6c7ceba5c92bd4b713ad1075
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575138"
---
# <a name="mapi-message-classes"></a><span data-ttu-id="95101-103">MAPI 邮件类</span><span class="sxs-lookup"><span data-stu-id="95101-103">MAPI Message Classes</span></span>

  
  
<span data-ttu-id="95101-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95101-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95101-105">每个邮件具有邮件类属性， **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))，它标识类型、 目的或消息的内容。</span><span class="sxs-lookup"><span data-stu-id="95101-105">Every message has a message class property, **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)), which identifies the type, purpose, or content of the message.</span></span> <span data-ttu-id="95101-106">**PR_MESSAGE_CLASS**是必需的属性对所有新邮件。</span><span class="sxs-lookup"><span data-stu-id="95101-106">**PR_MESSAGE_CLASS** is a required property on all new messages.</span></span> <span data-ttu-id="95101-107">邮件类决定用于向用户和发出传入消息的文件夹的邮件的形式。</span><span class="sxs-lookup"><span data-stu-id="95101-107">A message's class determines the form that is used to present the message to the user and the folder for placing incoming messages.</span></span> 
  
<span data-ttu-id="95101-108">邮件类是区分大小写的字符串，包含 ASCII 字符到 127 32 和用句点，分隔，但他们不能以句点结尾。</span><span class="sxs-lookup"><span data-stu-id="95101-108">Message classes are case-sensitive character strings that contain ASCII characters 32 through 127 and are delimited by periods, but they cannot end with a period.</span></span> <span data-ttu-id="95101-109">每个字符串表示的子类，级别和允许的级别数为没有限制。</span><span class="sxs-lookup"><span data-stu-id="95101-109">Each string represents a level of subclassing, and there is no limit to the number of levels allowed.</span></span> 
  
<span data-ttu-id="95101-110">例如，最多邮件客户端应用程序发送和接收分为**IPM**邮件类时，广，它介绍了所有人际邮件 (也就是说，为了按人员的用户，而不是以编程方式通过读取的消息计算机）。</span><span class="sxs-lookup"><span data-stu-id="95101-110">For example, most messages that client applications send and receive fall into the **IPM** message class, a broad category that describes all interpersonal messages (that is, messages that are meant to be read by a human user, rather than programmatically by a computer).</span></span> <span data-ttu-id="95101-111">消息存储提供程序更精确地介绍了通过创建**IPM**子类的 IPM 消息。</span><span class="sxs-lookup"><span data-stu-id="95101-111">Message store providers more precisely describe an IPM message by creating an **IPM** subclass.</span></span> <span data-ttu-id="95101-112">**IPM**子类继承**IPM**邮件类的属性。</span><span class="sxs-lookup"><span data-stu-id="95101-112">The **IPM** subclass inherits the properties of the **IPM** message class.</span></span> <span data-ttu-id="95101-113">通过连接到 IPM 标识符，如**IPM 其他字符的字符串被命名**IPM**类的子类。注意**来描述说明消息和**IPM。联系人**描述联系人的邮件。</span><span class="sxs-lookup"><span data-stu-id="95101-113">Subclasses of the **IPM** class are named by concatenating other character strings onto the IPM identifier, such as **IPM.Note** to describe a note message and **IPM.Contact** to describe a contact message.</span></span> 
  
<span data-ttu-id="95101-114">若要处理的显示和管理 IPM 消息，客户端可以使用 MAPI 提供了对标准窗体。</span><span class="sxs-lookup"><span data-stu-id="95101-114">To handle the display and management of IPM messages, clients can use a standard form that MAPI provides.</span></span> <span data-ttu-id="95101-115">若要处理的显示和管理新的邮件类，您作为客户端应用程序开发人员具有两个选项：</span><span class="sxs-lookup"><span data-stu-id="95101-115">To handle the display and management of new message classes, you as a client application developer have two options:</span></span>
  
1. <span data-ttu-id="95101-116">通过使用标准的客户端可以使用的 MAPI 定义窗体接口的组，可以创建新表单。</span><span class="sxs-lookup"><span data-stu-id="95101-116">You can create a new form by using the set of MAPI-defined form interfaces that a standard client can use.</span></span>
    
2. <span data-ttu-id="95101-117">您可以编写自己的客户端通过实施一个完整、 独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="95101-117">You can write your own client by implementing a complete, standalone application.</span></span> 
    
<span data-ttu-id="95101-118">客户端应将每个传出 message **PR_MESSAGE_CLASS**属性设置为**IPM**或**IPC**的一个子类，尽管消息存储提供程序具有其设置的 ultimate 责任。</span><span class="sxs-lookup"><span data-stu-id="95101-118">Although clients should set the **PR_MESSAGE_CLASS** property for every outgoing message to a subclass of either **IPM** or **IPC**, the message store provider has the ultimate responsibility for setting it.</span></span> <span data-ttu-id="95101-119">因此，如果客户端发送一条消息，而不设置其邮件类别，消息存储提供程序将其设置为适当的客户端类型的适当的默认值。</span><span class="sxs-lookup"><span data-stu-id="95101-119">Therefore, if a client sends a message without setting its message class, the message store provider sets it to the appropriate default value for the appropriate type of client.</span></span> <span data-ttu-id="95101-120">人际邮件客户端的默认邮件类别是**IPM**;进程间的通信客户端的默认邮件类别是**IPC**。</span><span class="sxs-lookup"><span data-stu-id="95101-120">The default message class for interpersonal messaging clients is **IPM**; the default message class for interprocess communication clients is **IPC**.</span></span> 
  
<span data-ttu-id="95101-121">邮件类具有长度限制为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="95101-121">Message classes have a length restriction of 255 characters.</span></span> <span data-ttu-id="95101-122">但是，邮件类不应超过 127 个字符，以支持报告中所使用的邮件类。</span><span class="sxs-lookup"><span data-stu-id="95101-122">However, message classes should not exceed 127 characters to support the message classes used in reports.</span></span> <span data-ttu-id="95101-123">报告邮件类基于的原始邮件，两个内容类： 前缀和后缀。</span><span class="sxs-lookup"><span data-stu-id="95101-123">Report message classes are based on the class of the original message, with two additions: a prefix and a suffix.</span></span> <span data-ttu-id="95101-124">前缀报告指示邮件是报表，并且后缀指示的报告类型： 灾难恢复 （送达报告）、 NDR （原件报告）、 IPNRN （阅读报告） 或 IPNNRN （nonread 报告）。</span><span class="sxs-lookup"><span data-stu-id="95101-124">The prefix REPORT indicates that the message is a report, and the suffix indicates the type of report: DR (delivery report), NDR (nondelivery report), IPNRN (read report), or IPNNRN (nonread report).</span></span> <span data-ttu-id="95101-125">请注意，这些长度限制授予以字符;使用双字节字符集的平台上, 实际的字节数可能更高版本。</span><span class="sxs-lookup"><span data-stu-id="95101-125">Note that these length restrictions are given in characters; on platforms that use a double-byte character set, the actual byte count might be higher.</span></span> 
  
<span data-ttu-id="95101-126">客户端尝试分配的字符串超出其邮件类别的允许限制时，消息存储提供程序应从其[IMAPIProp::SetProps](imapiprop-setprops.md)方法实现返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="95101-126">Message store providers should return MAPI_E_INVALID_PARAMETER from their [IMAPIProp::SetProps](imapiprop-setprops.md) method implementations when a client attempts to assign a string that exceeds the allowable limit for their message class.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="95101-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95101-127">See also</span></span>



[<span data-ttu-id="95101-128">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="95101-128">MAPI Messages</span></span>](mapi-messages.md)

