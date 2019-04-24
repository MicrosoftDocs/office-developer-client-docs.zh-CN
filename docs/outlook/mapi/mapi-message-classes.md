---
title: MAPI 邮件类别
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 64ef2bbb-585c-4908-8ad4-a1c954057e9b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b2ab5d56c53216152a83ca207ff5ba1d53c9049d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345891"
---
# <a name="mapi-message-classes"></a><span data-ttu-id="f8338-103">MAPI 邮件类别</span><span class="sxs-lookup"><span data-stu-id="f8338-103">MAPI Message Classes</span></span>

  
  
<span data-ttu-id="f8338-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f8338-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f8338-105">每封邮件都有一个消息类属性**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)), 该属性标识邮件的类型、目的或内容。</span><span class="sxs-lookup"><span data-stu-id="f8338-105">Every message has a message class property, **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)), which identifies the type, purpose, or content of the message.</span></span> <span data-ttu-id="f8338-106">**PR_MESSAGE_CLASS**是所有新邮件的必需属性。</span><span class="sxs-lookup"><span data-stu-id="f8338-106">**PR_MESSAGE_CLASS** is a required property on all new messages.</span></span> <span data-ttu-id="f8338-107">邮件的类决定了用于向用户显示邮件的窗体和用于放置传入邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f8338-107">A message's class determines the form that is used to present the message to the user and the folder for placing incoming messages.</span></span> 
  
<span data-ttu-id="f8338-108">邮件类是区分大小写的字符字符串, 其中包含 ASCII 字符32到127并由句点分隔, 但不能以句点结尾。</span><span class="sxs-lookup"><span data-stu-id="f8338-108">Message classes are case-sensitive character strings that contain ASCII characters 32 through 127 and are delimited by periods, but they cannot end with a period.</span></span> <span data-ttu-id="f8338-109">每个字符串表示一个级别的子类, 并且对允许的级别数没有限制。</span><span class="sxs-lookup"><span data-stu-id="f8338-109">Each string represents a level of subclassing, and there is no limit to the number of levels allowed.</span></span> 
  
<span data-ttu-id="f8338-110">例如, 客户端应用程序发送和接收的大多数邮件都属于**IPM**邮件类, 这是一个描述所有人际邮件 (即应由人为用户阅读的邮件, 而不是以编程方式通过计算机)。</span><span class="sxs-lookup"><span data-stu-id="f8338-110">For example, most messages that client applications send and receive fall into the **IPM** message class, a broad category that describes all interpersonal messages (that is, messages that are meant to be read by a human user, rather than programmatically by a computer).</span></span> <span data-ttu-id="f8338-111">邮件存储提供程序通过创建**ipm**子类更准确地描述 ipm 邮件。</span><span class="sxs-lookup"><span data-stu-id="f8338-111">Message store providers more precisely describe an IPM message by creating an **IPM** subclass.</span></span> <span data-ttu-id="f8338-112">**ipm**子类继承了**ipm**邮件类的属性。</span><span class="sxs-lookup"><span data-stu-id="f8338-112">The **IPM** subclass inherits the properties of the **IPM** message class.</span></span> <span data-ttu-id="f8338-113">**ipm**类的子类通过将其他字符字符串串联到 ipm 标识符 (如 ipm) 来命名 **。注释**: 说明注释消息和**IPM。联系**以描述联系人消息。</span><span class="sxs-lookup"><span data-stu-id="f8338-113">Subclasses of the **IPM** class are named by concatenating other character strings onto the IPM identifier, such as **IPM.Note** to describe a note message and **IPM.Contact** to describe a contact message.</span></span> 
  
<span data-ttu-id="f8338-114">若要处理 IPM 邮件的显示和管理, 客户端可以使用 MAPI 提供的标准表单。</span><span class="sxs-lookup"><span data-stu-id="f8338-114">To handle the display and management of IPM messages, clients can use a standard form that MAPI provides.</span></span> <span data-ttu-id="f8338-115">若要处理新邮件类的显示和管理, 您作为客户端应用程序开发人员有两个选项:</span><span class="sxs-lookup"><span data-stu-id="f8338-115">To handle the display and management of new message classes, you as a client application developer have two options:</span></span>
  
1. <span data-ttu-id="f8338-116">您可以使用标准客户端可以使用的由 MAPI 定义的表单界面集来创建新的表单。</span><span class="sxs-lookup"><span data-stu-id="f8338-116">You can create a new form by using the set of MAPI-defined form interfaces that a standard client can use.</span></span>
    
2. <span data-ttu-id="f8338-117">您可以通过实现完整的独立应用程序来编写自己的客户端。</span><span class="sxs-lookup"><span data-stu-id="f8338-117">You can write your own client by implementing a complete, standalone application.</span></span> 
    
<span data-ttu-id="f8338-118">虽然客户端应将每个传出邮件的**PR_MESSAGE_CLASS**属性设置为**IPM**或**IPC**的子类, 但邮件存储区提供程序对设置它的最终责任是最大的。</span><span class="sxs-lookup"><span data-stu-id="f8338-118">Although clients should set the **PR_MESSAGE_CLASS** property for every outgoing message to a subclass of either **IPM** or **IPC**, the message store provider has the ultimate responsibility for setting it.</span></span> <span data-ttu-id="f8338-119">因此, 如果客户端发送邮件时未设置其邮件类别, 则邮件存储提供程序会将其设置为适当类型的客户端的相应默认值。</span><span class="sxs-lookup"><span data-stu-id="f8338-119">Therefore, if a client sends a message without setting its message class, the message store provider sets it to the appropriate default value for the appropriate type of client.</span></span> <span data-ttu-id="f8338-120">人际邮件客户端的默认邮件类为**IPM**;进程间通信客户端的默认邮件类为**IPC**。</span><span class="sxs-lookup"><span data-stu-id="f8338-120">The default message class for interpersonal messaging clients is **IPM**; the default message class for interprocess communication clients is **IPC**.</span></span> 
  
<span data-ttu-id="f8338-121">邮件类别的长度限制为255个字符。</span><span class="sxs-lookup"><span data-stu-id="f8338-121">Message classes have a length restriction of 255 characters.</span></span> <span data-ttu-id="f8338-122">但是, 邮件类别不应超过127个字符以支持在报告中使用的邮件类。</span><span class="sxs-lookup"><span data-stu-id="f8338-122">However, message classes should not exceed 127 characters to support the message classes used in reports.</span></span> <span data-ttu-id="f8338-123">报告邮件类基于原始邮件的类, 其中包含两个添加项: 前缀和后缀。</span><span class="sxs-lookup"><span data-stu-id="f8338-123">Report message classes are based on the class of the original message, with two additions: a prefix and a suffix.</span></span> <span data-ttu-id="f8338-124">前缀报告指示邮件是一个报告, 后缀指示报告类型: DR (传递报告)、NDR (nondelivery report)、IPNRN (read report) 或 IPNNRN (未读 report)。</span><span class="sxs-lookup"><span data-stu-id="f8338-124">The prefix REPORT indicates that the message is a report, and the suffix indicates the type of report: DR (delivery report), NDR (nondelivery report), IPNRN (read report), or IPNNRN (nonread report).</span></span> <span data-ttu-id="f8338-125">请注意, 这些长度限制是在字符中提供的;在使用双字节字符集的平台上, 实际字节计数可能会更高。</span><span class="sxs-lookup"><span data-stu-id="f8338-125">Note that these length restrictions are given in characters; on platforms that use a double-byte character set, the actual byte count might be higher.</span></span> 
  
<span data-ttu-id="f8338-126">当客户端尝试分配超过其邮件类别允许的限制的字符串时, 邮件存储提供程序应从其[IMAPIProp:: SetProps](imapiprop-setprops.md)方法实现中返回 MAPI_E_INVALID_PARAMETER。</span><span class="sxs-lookup"><span data-stu-id="f8338-126">Message store providers should return MAPI_E_INVALID_PARAMETER from their [IMAPIProp::SetProps](imapiprop-setprops.md) method implementations when a client attempts to assign a string that exceeds the allowable limit for their message class.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f8338-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8338-127">See also</span></span>



[<span data-ttu-id="f8338-128">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="f8338-128">MAPI Messages</span></span>](mapi-messages.md)

