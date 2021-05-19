---
title: SMTP 地址
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 42015740-a94f-4628-bf32-b7fc2fdb9ff6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fb4402100891df8b27c8d26900a4acd05f4183e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419623"
---
# <a name="smtp-addresses"></a><span data-ttu-id="64308-103">SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="64308-103">SMTP Addresses</span></span>

  
  
<span data-ttu-id="64308-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64308-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64308-105">SMTP 电子邮件地址的格式在 RFC 822 中定义。</span><span class="sxs-lookup"><span data-stu-id="64308-105">The format of SMTP email addresses is defined in RFC 822.</span></span> <span data-ttu-id="64308-106">MAPI 组件应处理符合该标准的任何地址。</span><span class="sxs-lookup"><span data-stu-id="64308-106">MAPI components should handle any address that complies with that standard.</span></span> <span data-ttu-id="64308-107">但是，有一种特定形式的 RFC 822 地址可以最好地对 MAPI 地址进行编码：</span><span class="sxs-lookup"><span data-stu-id="64308-107">However, there is a particular form of RFC 822 address that best encodes MAPI addresses:</span></span>
  
 <span data-ttu-id="64308-108">_display-name_ **\<**_email-address_**\>**</span><span class="sxs-lookup"><span data-stu-id="64308-108">_display-name_ **\<** _email-address_ **\>**</span></span>
  
<span data-ttu-id="64308-109">尖括号作为文字包含在内。</span><span class="sxs-lookup"><span data-stu-id="64308-109">The angle brackets are included as literals.</span></span> <span data-ttu-id="64308-110">空白在显示名称中很常见;它们不需要引用。</span><span class="sxs-lookup"><span data-stu-id="64308-110">Blanks are common in display names; they need not be quoted.</span></span> <span data-ttu-id="64308-111">典型地址可能如下所示，该地址属于 RFC 1521 的共同作者之一：</span><span class="sxs-lookup"><span data-stu-id="64308-111">A typical address might look like this one, which belongs to one of the coauthors of RFC 1521:</span></span>
  
<span data-ttu-id="64308-112">Nathaniel 一 \< nsb@bellcore.com\></span><span class="sxs-lookup"><span data-stu-id="64308-112">Nathaniel Borenstein \<nsb@bellcore.com\></span></span>
  
<span data-ttu-id="64308-113">如果显示名称 SMTP 地址（如 或 @）中包含特殊含义的字符，则整个 显示名称 应括在 \< 双引号中。</span><span class="sxs-lookup"><span data-stu-id="64308-113">If the display name contains characters that have special meaning in SMTP addresses, such as \< or @, the entire display name should be enclosed in double quotes.</span></span> <span data-ttu-id="64308-114">在出站邮件上，如果电子邮件地址的总长度加上 显示名称超过 255 个字符，显示名称丢弃。</span><span class="sxs-lookup"><span data-stu-id="64308-114">On outbound mail, if the total length of the email address plus display name exceeds 255 characters, the display name should be dropped.</span></span>
  
<span data-ttu-id="64308-115">SMTP 地址的各个部分映射到 MAPI 属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="64308-115">The parts of an SMTP address map into MAPI properties as follows:</span></span>
  
|<span data-ttu-id="64308-116">**SMTP 地址组件**</span><span class="sxs-lookup"><span data-stu-id="64308-116">**SMTP address component**</span></span>|<span data-ttu-id="64308-117">**MAPI 属性**</span><span class="sxs-lookup"><span data-stu-id="64308-117">**MAPI property**</span></span>|
|:-----|:-----|
| <span data-ttu-id="64308-118">_所有收件人_ 的显示名称</span><span class="sxs-lookup"><span data-stu-id="64308-118">_display-name_ for all recipients</span></span>  <br/> |<span data-ttu-id="64308-119">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="64308-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="64308-120">_From 字段的 display-name_</span><span class="sxs-lookup"><span data-stu-id="64308-120">_display-name_ for From field</span></span>  <br/> |<span data-ttu-id="64308-121">**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="64308-121">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="64308-122">_发件人字段_ 的显示名称</span><span class="sxs-lookup"><span data-stu-id="64308-122">_display-name_ for Sender field</span></span>  <br/> |<span data-ttu-id="64308-123">**PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="64308-123">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="64308-124">_email-address_</span><span class="sxs-lookup"><span data-stu-id="64308-124">_email-address_</span></span> <br/> |<span data-ttu-id="64308-125">**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="64308-125">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="64308-126">隐式，始终为"SMTP"</span><span class="sxs-lookup"><span data-stu-id="64308-126">implicit, always "SMTP"</span></span>  <br/> |<span data-ttu-id="64308-127">**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="64308-127">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |
   
<span data-ttu-id="64308-128">如果入站邮件显示名称地址，应改为使用整个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="64308-128">If there is no display name for an address on inbound mail, the entire email address should be used instead.</span></span> <span data-ttu-id="64308-129">地址类型始终为 SMTP。</span><span class="sxs-lookup"><span data-stu-id="64308-129">The address type is always SMTP.</span></span>
  
<span data-ttu-id="64308-130">收件人属性取自 MAPI 邮件的收件人表;发件人属性取自邮件本身。</span><span class="sxs-lookup"><span data-stu-id="64308-130">Recipient properties are taken from the MAPI message's recipient table; sender properties are taken from the message itself.</span></span>
  

