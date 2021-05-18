---
title: MAPI 中的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d0ff834-253b-4e8c-a5be-6e4745a2a66c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f37d65e4beb328c2c92cf0c2ab28586af6bee45
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408087"
---
# <a name="formatted-text-in-mapi"></a><span data-ttu-id="5d65c-103">MAPI 中的格式化文本</span><span class="sxs-lookup"><span data-stu-id="5d65c-103">Formatted Text in MAPI</span></span>

  
  
<span data-ttu-id="5d65c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d65c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d65c-105">可以使用纯文本或格式化文本存储和传输邮件文本。</span><span class="sxs-lookup"><span data-stu-id="5d65c-105">The text of a message can be stored and transmitted using plain text or formatted text.</span></span> <span data-ttu-id="5d65c-106">格式化文本通过更改消息文本的外观（例如，使用一个或多个字体、字号或文本颜色）来增强消息文本。</span><span class="sxs-lookup"><span data-stu-id="5d65c-106">Formatted text enhances the message text by altering its appearance with, for example, one or more fonts, font sizes, or text colors.</span></span> <span data-ttu-id="5d65c-107">建议所有客户端以及所有邮件存储提供程序尽可能支持格式化文本。</span><span class="sxs-lookup"><span data-stu-id="5d65c-107">It is recommended that all clients and whenever possible, all message store providers, support formatted text.</span></span> <span data-ttu-id="5d65c-108">支持邮件中的格式化文本通过提高邮件可读性并简化邮件处理来增加价值。</span><span class="sxs-lookup"><span data-stu-id="5d65c-108">Supporting formatted text in messages adds value by improving message readability and making message handling easier and more efficient.</span></span>
  
<span data-ttu-id="5d65c-109">格式化文本可以通过多种方式实现。</span><span class="sxs-lookup"><span data-stu-id="5d65c-109">Formatted text can be implemented in a variety of ways.</span></span> <span data-ttu-id="5d65c-110">最常见的使用 RTF 格式格式 (RTF) 。</span><span class="sxs-lookup"><span data-stu-id="5d65c-110">The most common way is with the Rich Text Format (RTF).</span></span> <span data-ttu-id="5d65c-111">MAPI 定义用于存储邮件文本信息的三个可传输属性 **：PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 表示纯文本 **，PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 表示 HTML，PR_RTF_COMPRESSED ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 表示已压缩的 RTF 文本。 </span><span class="sxs-lookup"><span data-stu-id="5d65c-111">MAPI defines three transmittable properties for holding message text information: **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) for plain text, **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) for HTML, and **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) for RTF text that has been compressed.</span></span> <span data-ttu-id="5d65c-112">由于邮件文本的格式版本可以比不带格式的版本大两倍，因此在将 RTF 文本与邮件一起传输并存储在 PR_RTF_COMPRESSED 属性中之前 **，会** 先进行压缩。</span><span class="sxs-lookup"><span data-stu-id="5d65c-112">Because the formatted version of a message text can be twice as large as the version without the formatting, the RTF text is compressed before it is transferred with the message and stored in the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="5d65c-113">当应该在屏幕上显示消息时，使用 MAPI 提供的实用工具函数取消压缩消息。</span><span class="sxs-lookup"><span data-stu-id="5d65c-113">When it is time to display the message on the screen, it is uncompressed using a utility function provided by MAPI.</span></span> 
  
<span data-ttu-id="5d65c-114">MAPI 定义这两个邮件文本属性和机制，以便 RTF 感知客户端可以与不支持格式化文本的客户端和邮件系统进行互操作。</span><span class="sxs-lookup"><span data-stu-id="5d65c-114">MAPI defines these two message text properties and mechanisms for conversion between them so that RTF-aware clients can interoperate with clients and messaging systems that do not support formatted text.</span></span>
  
### 

[<span data-ttu-id="5d65c-115">同步文本和格式</span><span class="sxs-lookup"><span data-stu-id="5d65c-115">Synchronizing Text and Formatting</span></span>](synchronizing-text-and-formatting.md)
  
> <span data-ttu-id="5d65c-116">介绍如何保持 RTF 邮件文本与格式同步。</span><span class="sxs-lookup"><span data-stu-id="5d65c-116">Describes how to keep RTF message text synchronized with the formatting.</span></span>
    
[<span data-ttu-id="5d65c-117">支持传出邮件中的格式化文本：客户端责任</span><span class="sxs-lookup"><span data-stu-id="5d65c-117">Supporting Formatted Text in Outgoing Messages: Client Responsibilities</span></span>](supporting-formatted-text-in-outgoing-messages-client-responsibilities.md)
  
> <span data-ttu-id="5d65c-118">介绍客户端应用程序在支持传出邮件中的格式化文本方面的责任。</span><span class="sxs-lookup"><span data-stu-id="5d65c-118">Describes client application responsibilities for supporting formatted text in outgoing messages.</span></span>
    
[<span data-ttu-id="5d65c-119">支持传入邮件中的格式化文本：客户端责任</span><span class="sxs-lookup"><span data-stu-id="5d65c-119">Supporting Formatted Text in Incoming Messages: Client Responsibilities</span></span>](supporting-formatted-text-in-incoming-messages-client-responsibilities.md)
  
> <span data-ttu-id="5d65c-120">介绍客户端应用程序在支持传入邮件中的格式化文本方面的责任。</span><span class="sxs-lookup"><span data-stu-id="5d65c-120">Describes client application responsibilities for supporting formatted text in incoming messages.</span></span>
    
[<span data-ttu-id="5d65c-121">支持格式化文本：邮件存储责任</span><span class="sxs-lookup"><span data-stu-id="5d65c-121">Supporting Formatted Text: Message Store Responsibilities</span></span>](supporting-formatted-text-message-store-responsibilities.md)
  
> <span data-ttu-id="5d65c-122">描述邮件存储支持格式化文本的责任。</span><span class="sxs-lookup"><span data-stu-id="5d65c-122">Describes message store responsibilities for supporting formatted text.</span></span>
    
[<span data-ttu-id="5d65c-123">支持格式化文本：呈现附件</span><span class="sxs-lookup"><span data-stu-id="5d65c-123">Supporting Formatted Text: Rendering Attachments</span></span>](supporting-formatted-text-rendering-attachments.md)
  
> <span data-ttu-id="5d65c-124">介绍如何选择附件的呈现位置。</span><span class="sxs-lookup"><span data-stu-id="5d65c-124">Describes how to choose where attachments are rendered.</span></span>
    
[<span data-ttu-id="5d65c-125">支持格式化文本：网关责任</span><span class="sxs-lookup"><span data-stu-id="5d65c-125">Supporting Formatted Text: Gateway Responsibilities</span></span>](supporting-formatted-text-gateway-responsibilities.md)
  
> <span data-ttu-id="5d65c-126">描述网关对传出和传入格式化短信的责任。</span><span class="sxs-lookup"><span data-stu-id="5d65c-126">Describes the gateway responsibilities for outgoing and incoming formatted text messages.</span></span>
    

