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
# <a name="formatted-text-in-mapi"></a><span data-ttu-id="e9ca2-103">MAPI 中的格式化文本</span><span class="sxs-lookup"><span data-stu-id="e9ca2-103">Formatted Text in MAPI</span></span>

  
  
<span data-ttu-id="e9ca2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9ca2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e9ca2-105">可以使用纯文本或带格式的文本来存储和传输邮件的文本。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-105">The text of a message can be stored and transmitted using plain text or formatted text.</span></span> <span data-ttu-id="e9ca2-106">格式化文本通过更改其外观 (例如, 一个或多个字体、字体大小或文本颜色) 来增强邮件文本。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-106">Formatted text enhances the message text by altering its appearance with, for example, one or more fonts, font sizes, or text colors.</span></span> <span data-ttu-id="e9ca2-107">建议所有的客户端和所有邮件存储提供程序 (如果可能) 都支持格式化文本。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-107">It is recommended that all clients and whenever possible, all message store providers, support formatted text.</span></span> <span data-ttu-id="e9ca2-108">在邮件中支持格式化文本通过提高邮件可读性和简化邮件处理来增加价值。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-108">Supporting formatted text in messages adds value by improving message readability and making message handling easier and more efficient.</span></span>
  
<span data-ttu-id="e9ca2-109">可以通过多种方式实现格式化文本。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-109">Formatted text can be implemented in a variety of ways.</span></span> <span data-ttu-id="e9ca2-110">最常见的方法是使用格式文本格式 (rtf)。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-110">The most common way is with the Rich Text Format (RTF).</span></span> <span data-ttu-id="e9ca2-111">MAPI 定义了用于保存邮件文本信息的三个传输属性: **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 用于纯文本、 **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) for HTML 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)), 用于已压缩的 rtf 文本。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-111">MAPI defines three transmittable properties for holding message text information: **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) for plain text, **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) for HTML, and **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) for RTF text that has been compressed.</span></span> <span data-ttu-id="e9ca2-112">由于邮件文本的格式设置版本的大小可以是不带格式的版本, 因此 RTF 文本在与邮件一起传输并存储在**PR_RTF_COMPRESSED**属性中之前会进行压缩。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-112">Because the formatted version of a message text can be twice as large as the version without the formatting, the RTF text is compressed before it is transferred with the message and stored in the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="e9ca2-113">在屏幕上显示邮件的时间时, 将使用 MAPI 提供的实用工具函数对其进行解压缩。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-113">When it is time to display the message on the screen, it is uncompressed using a utility function provided by MAPI.</span></span> 
  
<span data-ttu-id="e9ca2-114">MAPI 定义了这两种邮件文本属性和在它们之间进行转换的机制, 以便 RTF 感知客户端可以与不支持格式化文本的客户端和邮件系统进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-114">MAPI defines these two message text properties and mechanisms for conversion between them so that RTF-aware clients can interoperate with clients and messaging systems that do not support formatted text.</span></span>
  
### 

[<span data-ttu-id="e9ca2-115">同步文本和格式设置</span><span class="sxs-lookup"><span data-stu-id="e9ca2-115">Synchronizing Text and Formatting</span></span>](synchronizing-text-and-formatting.md)
  
> <span data-ttu-id="e9ca2-116">介绍如何将 RTF 邮件文本与格式保持同步。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-116">Describes how to keep RTF message text synchronized with the formatting.</span></span>
    
[<span data-ttu-id="e9ca2-117">在待发邮件中支持格式化文本: 客户端责任</span><span class="sxs-lookup"><span data-stu-id="e9ca2-117">Supporting Formatted Text in Outgoing Messages: Client Responsibilities</span></span>](supporting-formatted-text-in-outgoing-messages-client-responsibilities.md)
  
> <span data-ttu-id="e9ca2-118">介绍在传出邮件中支持格式化文本的客户端应用程序责任。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-118">Describes client application responsibilities for supporting formatted text in outgoing messages.</span></span>
    
[<span data-ttu-id="e9ca2-119">在传入邮件中支持格式化文本: 客户端责任</span><span class="sxs-lookup"><span data-stu-id="e9ca2-119">Supporting Formatted Text in Incoming Messages: Client Responsibilities</span></span>](supporting-formatted-text-in-incoming-messages-client-responsibilities.md)
  
> <span data-ttu-id="e9ca2-120">介绍在传入邮件中支持格式化文本的客户端应用程序责任。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-120">Describes client application responsibilities for supporting formatted text in incoming messages.</span></span>
    
[<span data-ttu-id="e9ca2-121">支持格式化文本: 邮件存储责任</span><span class="sxs-lookup"><span data-stu-id="e9ca2-121">Supporting Formatted Text: Message Store Responsibilities</span></span>](supporting-formatted-text-message-store-responsibilities.md)
  
> <span data-ttu-id="e9ca2-122">介绍用于支持格式化文本的邮件存储职责。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-122">Describes message store responsibilities for supporting formatted text.</span></span>
    
[<span data-ttu-id="e9ca2-123">支持格式化文本: 呈现附件</span><span class="sxs-lookup"><span data-stu-id="e9ca2-123">Supporting Formatted Text: Rendering Attachments</span></span>](supporting-formatted-text-rendering-attachments.md)
  
> <span data-ttu-id="e9ca2-124">介绍如何选择呈现附件的位置。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-124">Describes how to choose where attachments are rendered.</span></span>
    
[<span data-ttu-id="e9ca2-125">支持格式化文本: 网关责任</span><span class="sxs-lookup"><span data-stu-id="e9ca2-125">Supporting Formatted Text: Gateway Responsibilities</span></span>](supporting-formatted-text-gateway-responsibilities.md)
  
> <span data-ttu-id="e9ca2-126">介绍传出和传入的格式化短信的网关职责。</span><span class="sxs-lookup"><span data-stu-id="e9ca2-126">Describes the gateway responsibilities for outgoing and incoming formatted text messages.</span></span>
    

