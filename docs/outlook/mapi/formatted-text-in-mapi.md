---
title: MAPI 中的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d0ff834-253b-4e8c-a5be-6e4745a2a66c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6b82a755cbf2c8bd0f1d3676d4560e131dce3bd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774987"
---
# <a name="formatted-text-in-mapi"></a><span data-ttu-id="cd8ae-103">MAPI 中的格式化文本</span><span class="sxs-lookup"><span data-stu-id="cd8ae-103">Formatted Text in MAPI</span></span>

  
  
<span data-ttu-id="cd8ae-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cd8ae-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cd8ae-105">消息的文本可存储和传输使用纯文本或带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-105">The text of a message can be stored and transmitted using plain text or formatted text.</span></span> <span data-ttu-id="cd8ae-106">带格式的文本更改其与，例如，一个或多个字体、 字号或文本颜色的外观，从而增强了消息文本。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-106">Formatted text enhances the message text by altering its appearance with, for example, one or more fonts, font sizes, or text colors.</span></span> <span data-ttu-id="cd8ae-107">建议的所有客户端和所有消息存储提供程序，只要有可能，都支持带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-107">It is recommended that all clients and whenever possible, all message store providers, support formatted text.</span></span> <span data-ttu-id="cd8ae-108">支持带格式的文本消息中添加通过改进消息可读性和进行消息处理更容易、 更高效的值。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-108">Supporting formatted text in messages adds value by improving message readability and making message handling easier and more efficient.</span></span>
  
<span data-ttu-id="cd8ae-109">可以采用多种方式实现格式化的文本。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-109">Formatted text can be implemented in a variety of ways.</span></span> <span data-ttu-id="cd8ae-110">最常用的方法是使用富文本格式 (RTF)。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-110">The most common way is with the Rich Text Format (RTF).</span></span> <span data-ttu-id="cd8ae-111">MAPI 定义三个可传送属性用于保存消息文本信息： **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 纯文本， **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) HTML，和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 的 RTF 已压缩的文本。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-111">MAPI defines three transmittable properties for holding message text information: **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) for plain text, **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) for HTML, and **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) for RTF text that has been compressed.</span></span> <span data-ttu-id="cd8ae-112">消息文本的格式的版本可以两次版本，而不的格式，因为它是与邮件传输和存储在**PR_RTF_COMPRESSED**属性之前被压缩 RTF 的文本。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-112">Because the formatted version of a message text can be twice as large as the version without the formatting, the RTF text is compressed before it is transferred with the message and stored in the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="cd8ae-113">在屏幕上显示邮件时，时，未压缩使用 MAPI 提供的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-113">When it is time to display the message on the screen, it is uncompressed using a utility function provided by MAPI.</span></span> 
  
<span data-ttu-id="cd8ae-114">MAPI 定义这两个邮件文本属性和它们之间的转换的机制，以便 RTF 感知客户端可以与客户端和不支持的邮件系统互操作格式化文本。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-114">MAPI defines these two message text properties and mechanisms for conversion between them so that RTF-aware clients can interoperate with clients and messaging systems that do not support formatted text.</span></span>
  
### 

[<span data-ttu-id="cd8ae-115">同步文本和格式设置</span><span class="sxs-lookup"><span data-stu-id="cd8ae-115">Synchronizing Text and Formatting</span></span>](synchronizing-text-and-formatting.md)
  
> <span data-ttu-id="cd8ae-116">介绍如何保留 RTF 邮件文本的格式与同步。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-116">Describes how to keep RTF message text synchronized with the formatting.</span></span>
    
[<span data-ttu-id="cd8ae-117">支持待发邮件中的格式化文本：客户端责任</span><span class="sxs-lookup"><span data-stu-id="cd8ae-117">Supporting Formatted Text in Outgoing Messages: Client Responsibilities</span></span>](supporting-formatted-text-in-outgoing-messages-client-responsibilities.md)
  
> <span data-ttu-id="cd8ae-118">介绍在传出消息中支持带格式的文本的客户端应用程序责任。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-118">Describes client application responsibilities for supporting formatted text in outgoing messages.</span></span>
    
[<span data-ttu-id="cd8ae-119">支持传入邮件中的格式化文本：客户端责任</span><span class="sxs-lookup"><span data-stu-id="cd8ae-119">Supporting Formatted Text in Incoming Messages: Client Responsibilities</span></span>](supporting-formatted-text-in-incoming-messages-client-responsibilities.md)
  
> <span data-ttu-id="cd8ae-120">介绍客户端应用程序接收的邮件中支持带格式的文本的责任。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-120">Describes client application responsibilities for supporting formatted text in incoming messages.</span></span>
    
[<span data-ttu-id="cd8ae-121">支持格式化文本：邮件存储区责任</span><span class="sxs-lookup"><span data-stu-id="cd8ae-121">Supporting Formatted Text: Message Store Responsibilities</span></span>](supporting-formatted-text-message-store-responsibilities.md)
  
> <span data-ttu-id="cd8ae-122">介绍支持带格式的文本的消息存储责任。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-122">Describes message store responsibilities for supporting formatted text.</span></span>
    
[<span data-ttu-id="cd8ae-123">支持格式化文本：显示附件</span><span class="sxs-lookup"><span data-stu-id="cd8ae-123">Supporting Formatted Text: Rendering Attachments</span></span>](supporting-formatted-text-rendering-attachments.md)
  
> <span data-ttu-id="cd8ae-124">介绍如何选择其中呈现附件。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-124">Describes how to choose where attachments are rendered.</span></span>
    
[<span data-ttu-id="cd8ae-125">支持格式化文本：网关责任</span><span class="sxs-lookup"><span data-stu-id="cd8ae-125">Supporting Formatted Text: Gateway Responsibilities</span></span>](supporting-formatted-text-gateway-responsibilities.md)
  
> <span data-ttu-id="cd8ae-126">介绍传出和传入格式化的文本邮件的网关责任。</span><span class="sxs-lookup"><span data-stu-id="cd8ae-126">Describes the gateway responsibilities for outgoing and incoming formatted text messages.</span></span>
    

