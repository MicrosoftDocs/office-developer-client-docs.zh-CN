---
title: 一次性条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 741d21ae-f14a-4b7f-80aa-91d0f0ff3f34
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: abe52cb45e13e6713d28fffe379e245e2483bffa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411041"
---
# <a name="one-off-entry-identifiers"></a><span data-ttu-id="e766e-103">一次性条目标识符</span><span class="sxs-lookup"><span data-stu-id="e766e-103">One-off entry identifiers</span></span>
  
<span data-ttu-id="e766e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e766e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e766e-105">一次输入标识符由 MAPI 在 **IAddrBook：：CreateOneOff** 方法中创建，由无法访问 MAPI 子系统的组件（如网关组件）创建。</span><span class="sxs-lookup"><span data-stu-id="e766e-105">One-off entry identifiers are created by MAPI in the **IAddrBook::CreateOneOff** method and by components that do not have access to the MAPI subsystem, such as gateway components.</span></span> <span data-ttu-id="e766e-106">有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="e766e-106">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md).</span></span> <span data-ttu-id="e766e-107">下图显示了一次输入标识符的格式。</span><span class="sxs-lookup"><span data-stu-id="e766e-107">The following illustration shows the format of a one-off entry identifier.</span></span>
  
<span data-ttu-id="e766e-108">**一次性条目标识符格式**</span><span class="sxs-lookup"><span data-stu-id="e766e-108">**One-off entry identifier format**</span></span>
  
<span data-ttu-id="e766e-109">![一次使用条目标识符格式](media/amapi_69.gif "一次使用条目标识符格式")</span><span class="sxs-lookup"><span data-stu-id="e766e-109">![One-off entry identifier format](media/amapi_69.gif "One-off entry identifier format")</span></span>
  
<span data-ttu-id="e766e-110">第一个字段是一个特殊的 [MAPIUID](mapiuid.md) 结构，用于将条目标识符标识为表示自定义收件人。</span><span class="sxs-lookup"><span data-stu-id="e766e-110">The first field is a special [MAPIUID](mapiuid.md) structure that identifies the entry identifier as representing a custom recipient.</span></span> <span data-ttu-id="e766e-111">此 **MAPIUID** 结构必须设置为常量 MAPI_ONE_OFF_UID。</span><span class="sxs-lookup"><span data-stu-id="e766e-111">This **MAPIUID** structure must be set to the constant MAPI_ONE_OFF_UID.</span></span> <span data-ttu-id="e766e-112">MAPI_ONE_OFF_UID在头文件 MAPIDEFS.H 中定义。</span><span class="sxs-lookup"><span data-stu-id="e766e-112">MAPI_ONE_OFF_UID is defined in the header file MAPIDEFS.H.</span></span> 
  
<span data-ttu-id="e766e-113">版本和标志字段是按 Intel 字节顺序表示的 16 位单词。</span><span class="sxs-lookup"><span data-stu-id="e766e-113">The version and flags fields are 16-bit words in Intel byte order.</span></span> <span data-ttu-id="e766e-114">版本字段必须设置为零。</span><span class="sxs-lookup"><span data-stu-id="e766e-114">The version field must be set to zero.</span></span> <span data-ttu-id="e766e-115">可以将 flags 字段设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="e766e-115">The flags field can be set to the following values:</span></span>
  
<span data-ttu-id="e766e-116">MAPI_ONE_OFF_NO_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="e766e-116">MAPI_ONE_OFF_NO_RICH_INFO</span></span>
  
<span data-ttu-id="e766e-117">MAPI_ONE_OFF_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e766e-117">MAPI_ONE_OFF_UNICODE</span></span>
  
<span data-ttu-id="e766e-118">如果MAPI_ONE_OFF_NO_RICH_INFO TNEF 策略中不应接收传输中性封装格式的邮件内容， (设置) 。</span><span class="sxs-lookup"><span data-stu-id="e766e-118">The MAPI_ONE_OFF_NO_RICH_INFO flag is set if a recipient should not receive message content in the Transport Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="e766e-119">此标志在将 MAPI_SEND_NO_RICH_INFO [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md) 方法时设置。</span><span class="sxs-lookup"><span data-stu-id="e766e-119">This flag is set when MAPI_SEND_NO_RICH_INFO is passed to [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) method.</span></span> 
  
<span data-ttu-id="e766e-120">如果MAPI_ONE_OFF_UNICODE和电子邮件地址是 Unicode 字符串显示名称，则设置此参数标记。</span><span class="sxs-lookup"><span data-stu-id="e766e-120">The MAPI_ONE_OFF_UNICODE flag is set if the display name and email address are Unicode strings.</span></span> <span data-ttu-id="e766e-121">此标志在将MAPI_UNICODE **IAddrBook：：CreateOneOff** 时设置。</span><span class="sxs-lookup"><span data-stu-id="e766e-121">This flag is set when the MAPI_UNICODE is passed to **IAddrBook::CreateOneOff**.</span></span> <span data-ttu-id="e766e-122">当 MAPI_UNICODE 标志未传递到 **CreateOneOff** 时，MAPI 假定 显示名称 和电子邮件地址字符串位于工作站的当前 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="e766e-122">When the MAPI_UNICODE flag is not passed to **CreateOneOff**, MAPI assumes that the display name and email address strings are in the workstation's current ANSI character set.</span></span> <span data-ttu-id="e766e-123">ANSI 字符串通常对使用不同字符集的平台之间发送的消息不起作用，因为代码页未在条目标识符中编码。</span><span class="sxs-lookup"><span data-stu-id="e766e-123">ANSI strings generally do not work well in messages that are sent between platforms using different character sets because the code page is not encoded in the entry identifier.</span></span> <span data-ttu-id="e766e-124">若要防止这种潜在的不兼容，许多地址类型仅限于在多个字符集之间通用的那些字符。</span><span class="sxs-lookup"><span data-stu-id="e766e-124">To protect against this potential incompatibility, many address types are limited to only those characters that are common across multiple character sets.</span></span> <span data-ttu-id="e766e-125">但是，为了确保字符集和平台兼容性，客户端应针对消息中的字符串使用 Unicode。</span><span class="sxs-lookup"><span data-stu-id="e766e-125">However, to ensure character set and platform compatibility, clients should use Unicode for the character strings in their messages.</span></span>
  
<span data-ttu-id="e766e-126">the 显示名称 is a null-terminated string that corresponds to the recipient's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property and to the  _lpszName_ parameter passed to **IAddrBook：：CreateOneOff**.</span><span class="sxs-lookup"><span data-stu-id="e766e-126">The display name is a null-terminated string that corresponds to the recipient's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property and to the  _lpszName_ parameter passed to **IAddrBook::CreateOneOff**.</span></span> <span data-ttu-id="e766e-127">如果设置了字符集标志，则字符集MAPI_ONE_OFF_UNICODE Unicode;如果字符集是清除标记，则字符集为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="e766e-127">The character set is Unicode if the MAPI_ONE_OFF_UNICODE flag is set and ANSI if it is clear.</span></span> 
  
<span data-ttu-id="e766e-128">地址类型是一个以 null 结尾的字符串，对应于收件人的 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性和传递到 **IAddrBook：：CreateOneOff** 的 _lpszAdrType_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e766e-128">The address type is a null-terminated string that corresponds to the recipient's **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property and to the  _lpszAdrType_ parameter passed to **IAddrBook::CreateOneOff**.</span></span> 
  
<span data-ttu-id="e766e-129">电子邮件地址是一个以 null 结尾的字符串，对应于收件人的 **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性和传递到 **IAddrBook：：CreateOneOff**_的 lpszAddress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="e766e-129">The email address is a null-terminated string that corresponds to the recipient's **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) property and to the  _lpszAddress_ parameter passed to **IAddrBook::CreateOneOff**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e766e-130">一次项标识符结构中没有填充;字节的打包方式与上述完全相同，条目标识符长度不应包含电子邮件地址的终止 null 字符之外的任何字节。</span><span class="sxs-lookup"><span data-stu-id="e766e-130">There is no padding in one-off entry identifier structures; the bytes are packed exactly as indicated above and the entry identifier length should not include any bytes beyond the terminating null character of the email address.</span></span> 
  
<span data-ttu-id="e766e-131">手动构造一次条目标识符的客户端和通讯簿提供程序可能还需要为 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性生成值。</span><span class="sxs-lookup"><span data-stu-id="e766e-131">Clients and address book providers that manually construct one-off entry identifiers might also need to generate values for the **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) properties.</span></span> <span data-ttu-id="e766e-132">记录键与条目标识符相同。</span><span class="sxs-lookup"><span data-stu-id="e766e-132">The record key is identical to the entry identifier.</span></span> <span data-ttu-id="e766e-133">搜索键应按以下顺序连接以下字段来形成：</span><span class="sxs-lookup"><span data-stu-id="e766e-133">The search key should be formed by concatenating the following fields in the following order:</span></span>
  
1. <span data-ttu-id="e766e-134">转换为大写字符的地址类型。</span><span class="sxs-lookup"><span data-stu-id="e766e-134">The address type, converted to uppercase characters.</span></span>
    
2. <span data-ttu-id="e766e-135">冒号 (：) 。</span><span class="sxs-lookup"><span data-stu-id="e766e-135">A colon (:).</span></span>
    
3. <span data-ttu-id="e766e-136">转换为大写字符的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e766e-136">The email address, converted to uppercase characters.</span></span>
    
4. <span data-ttu-id="e766e-137">终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="e766e-137">A terminating null character.</span></span>
    
<span data-ttu-id="e766e-138">生成搜索键时，无需执行字符集转换。</span><span class="sxs-lookup"><span data-stu-id="e766e-138">No character set conversion must be done when generating the search key.</span></span>
  

