---
title: 一次性条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 741d21ae-f14a-4b7f-80aa-91d0f0ff3f34
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1335de3c1decf6c594f0148fbbf055061d7ce7e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776539"
---
# <a name="one-off-entry-identifiers"></a><span data-ttu-id="0eef8-103">一次性条目标识符</span><span class="sxs-lookup"><span data-stu-id="0eef8-103">One-off entry identifiers</span></span>
  
<span data-ttu-id="0eef8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0eef8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0eef8-105">一次性条目标识符创建**IAddrBook::CreateOneOff**方法中的 MAPI 和不具有访问 MAPI 子系统，如网关组件的组件。</span><span class="sxs-lookup"><span data-stu-id="0eef8-105">One-off entry identifiers are created by MAPI in the **IAddrBook::CreateOneOff** method and by components that do not have access to the MAPI subsystem, such as gateway components.</span></span> <span data-ttu-id="0eef8-106">有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-106">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md).</span></span> <span data-ttu-id="0eef8-107">下图显示了一次性条目标识符格式。</span><span class="sxs-lookup"><span data-stu-id="0eef8-107">The following illustration shows the format of a one-off entry identifier.</span></span>
  
<span data-ttu-id="0eef8-108">**一次性条目标识符格式**</span><span class="sxs-lookup"><span data-stu-id="0eef8-108">**One-off entry identifier format**</span></span>
  
<span data-ttu-id="0eef8-109">![一次性条目标识符格式](media/amapi_69.gif "一次性条目标识符格式")</span><span class="sxs-lookup"><span data-stu-id="0eef8-109">![One-off entry identifier format](media/amapi_69.gif "One-off entry identifier format")</span></span>
  
<span data-ttu-id="0eef8-110">第一个域是标识为表示自定义的收件人的项标识符的特殊[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="0eef8-110">The first field is a special [MAPIUID](mapiuid.md) structure that identifies the entry identifier as representing a custom recipient.</span></span> <span data-ttu-id="0eef8-111">此**MAPIUID**结构必须设置为常量 MAPI_ONE_OFF_UID。</span><span class="sxs-lookup"><span data-stu-id="0eef8-111">This **MAPIUID** structure must be set to the constant MAPI_ONE_OFF_UID.</span></span> <span data-ttu-id="0eef8-112">MAPI_ONE_OFF_UID MAPIDEFS 的头文件中定义。H。</span><span class="sxs-lookup"><span data-stu-id="0eef8-112">MAPI_ONE_OFF_UID is defined in the header file MAPIDEFS.H.</span></span> 
  
<span data-ttu-id="0eef8-113">版本和标志字段是 16 位 Intel 字节顺序中的单词。</span><span class="sxs-lookup"><span data-stu-id="0eef8-113">The version and flags fields are 16-bit words in Intel byte order.</span></span> <span data-ttu-id="0eef8-114">版本字段必须设置为零。</span><span class="sxs-lookup"><span data-stu-id="0eef8-114">The version field must be set to zero.</span></span> <span data-ttu-id="0eef8-115">标志字段可以设置为下列值：</span><span class="sxs-lookup"><span data-stu-id="0eef8-115">The flags field can be set to the following values:</span></span>
  
<span data-ttu-id="0eef8-116">MAPI_ONE_OFF_NO_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="0eef8-116">MAPI_ONE_OFF_NO_RICH_INFO</span></span>
  
<span data-ttu-id="0eef8-117">MAPI_ONE_OFF_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0eef8-117">MAPI_ONE_OFF_UNICODE</span></span>
  
<span data-ttu-id="0eef8-118">如果收件人不应接收消息内容传输中性封装格式 (TNEF) 中，设置了 MAPI_ONE_OFF_NO_RICH_INFO 标志。</span><span class="sxs-lookup"><span data-stu-id="0eef8-118">The MAPI_ONE_OFF_NO_RICH_INFO flag is set if a recipient should not receive message content in the Transport Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="0eef8-119">时 MAPI_SEND_NO_RICH_INFO 传递给[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)方法设置此标志。</span><span class="sxs-lookup"><span data-stu-id="0eef8-119">This flag is set when MAPI_SEND_NO_RICH_INFO is passed to [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) method.</span></span> 
  
<span data-ttu-id="0eef8-120">Unicode 字符串的显示名称和电子邮件地址时设置 MAPI_ONE_OFF_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="0eef8-120">The MAPI_ONE_OFF_UNICODE flag is set if the display name and email address are Unicode strings.</span></span> <span data-ttu-id="0eef8-121">当 MAPI_UNICODE 传递给**IAddrBook::CreateOneOff**设置此标志。</span><span class="sxs-lookup"><span data-stu-id="0eef8-121">This flag is set when the MAPI_UNICODE is passed to **IAddrBook::CreateOneOff**.</span></span> <span data-ttu-id="0eef8-122">当 MAPI_UNICODE 标志不传递给**CreateOneOff**时，MAPI 假定的显示名称和电子邮件地址字符串在工作站的当前的 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="0eef8-122">When the MAPI_UNICODE flag is not passed to **CreateOneOff**, MAPI assumes that the display name and email address strings are in the workstation's current ANSI character set.</span></span> <span data-ttu-id="0eef8-123">ANSI 字符串通常不非常适用于使用不同的字符集，因为的项标识符未编码的代码页的平台之间发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="0eef8-123">ANSI strings generally do not work well in messages that are sent between platforms using different character sets because the code page is not encoded in the entry identifier.</span></span> <span data-ttu-id="0eef8-124">若要防止此潜在不兼容性，多个地址类型，仅限于仅共有跨多个字符集这些字符。</span><span class="sxs-lookup"><span data-stu-id="0eef8-124">To protect against this potential incompatibility, many address types are limited to only those characters that are common across multiple character sets.</span></span> <span data-ttu-id="0eef8-125">但是，若要确保字符设置和平台兼容性，客户端应该使用 Unicode 字符串在其邮件中。</span><span class="sxs-lookup"><span data-stu-id="0eef8-125">However, to ensure character set and platform compatibility, clients should use Unicode for the character strings in their messages.</span></span>
  
<span data-ttu-id="0eef8-126">显示名称为 null 结尾的收件人的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性以及与_lpszName_参数传递给**IAddrBook::CreateOneOff**相对应的字符串。</span><span class="sxs-lookup"><span data-stu-id="0eef8-126">The display name is a null-terminated string that corresponds to the recipient's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property and to the  _lpszName_ parameter passed to **IAddrBook::CreateOneOff**.</span></span> <span data-ttu-id="0eef8-127">字符集时 MAPI_ONE_OFF_UNICODE 标志是设置和 ANSI 清除时，将 Unicode。</span><span class="sxs-lookup"><span data-stu-id="0eef8-127">The character set is Unicode if the MAPI_ONE_OFF_UNICODE flag is set and ANSI if it is clear.</span></span> 
  
<span data-ttu-id="0eef8-128">地址类型是收件人的**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性以及与传递给**IAddrBook::CreateOneOff** _lpszAdrType_参数相对应以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="0eef8-128">The address type is a null-terminated string that corresponds to the recipient's **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property and to the  _lpszAdrType_ parameter passed to **IAddrBook::CreateOneOff**.</span></span> 
  
<span data-ttu-id="0eef8-129">该电子邮件地址是收件人的**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性以及与传递给**IAddrBook::CreateOneOff** _lpszAddress_参数相对应以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="0eef8-129">The email address is a null-terminated string that corresponds to the recipient's **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) property and to the  _lpszAddress_ parameter passed to **IAddrBook::CreateOneOff**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0eef8-130">一次性条目标识符结构; 中没有空白字节被完全如上所示打包和项标识符长度不应包含任何字节超出的电子邮件地址的终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="0eef8-130">There is no padding in one-off entry identifier structures; the bytes are packed exactly as indicated above and the entry identifier length should not include any bytes beyond the terminating null character of the email address.</span></span> 
  
<span data-ttu-id="0eef8-131">客户端和手动构建一次性条目标识符的通讯簿提供程序可能还需要生成**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="0eef8-131">Clients and address book providers that manually construct one-off entry identifiers might also need to generate values for the **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) properties.</span></span> <span data-ttu-id="0eef8-132">记录关键是相同的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0eef8-132">The record key is identical to the entry identifier.</span></span> <span data-ttu-id="0eef8-133">应通过将按以下顺序的以下字段形成搜索关键字：</span><span class="sxs-lookup"><span data-stu-id="0eef8-133">The search key should be formed by concatenating the following fields in the following order:</span></span>
  
1. <span data-ttu-id="0eef8-134">地址类型，转换为大写字符。</span><span class="sxs-lookup"><span data-stu-id="0eef8-134">The address type, converted to uppercase characters.</span></span>
    
2. <span data-ttu-id="0eef8-135">冒号 （:）。</span><span class="sxs-lookup"><span data-stu-id="0eef8-135">A colon (:).</span></span>
    
3. <span data-ttu-id="0eef8-136">电子邮件地址，转换为大写字符。</span><span class="sxs-lookup"><span data-stu-id="0eef8-136">The email address, converted to uppercase characters.</span></span>
    
4. <span data-ttu-id="0eef8-137">终止空字符。</span><span class="sxs-lookup"><span data-stu-id="0eef8-137">A terminating null character.</span></span>
    
<span data-ttu-id="0eef8-138">生成搜索关键字时，必须不完成任何字符集转换。</span><span class="sxs-lookup"><span data-stu-id="0eef8-138">No character set conversion must be done when generating the search key.</span></span>
  

