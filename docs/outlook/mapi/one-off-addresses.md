---
title: 一次性地址
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9224c694-b26f-42c7-9404-ee2dd832cfbb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 598ced18d659fcbe52ded07cc3bb80dc396eddbf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776560"
---
# <a name="one-off-addresses"></a><span data-ttu-id="f33fa-103">一次性地址</span><span class="sxs-lookup"><span data-stu-id="f33fa-103">One-off addresses</span></span>

<span data-ttu-id="f33fa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f33fa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f33fa-105">一次性地址用于向一次性收件人，没有任何会话的通讯簿容器中的相应条目的收件人发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f33fa-105">One-off addresses are used to send messages to one-off recipients, recipients that do not have a corresponding entry in any of the session's address book containers.</span></span> <span data-ttu-id="f33fa-106">新条目添加到通讯簿或新收件人的传出邮件的收件人列表中时，客户端可以创建一次性地址。</span><span class="sxs-lookup"><span data-stu-id="f33fa-106">Clients can create one-off addresses when they add new entries to the address book or new recipients to the recipient list of an outgoing message.</span></span> <span data-ttu-id="f33fa-107">可以是一次性地址添加到任何容器的可修改。</span><span class="sxs-lookup"><span data-stu-id="f33fa-107">One-off addresses can be added to any container that is modifiable.</span></span>
  
<span data-ttu-id="f33fa-108">若要创建一个一次性地址，客户端，请使用特殊模板包含编辑控件以输入所有构成一次性地址的信息。</span><span class="sxs-lookup"><span data-stu-id="f33fa-108">To create a one-off address, clients use a special template containing edit controls for entering all of the information that makes up a one-off address.</span></span> <span data-ttu-id="f33fa-109">一次性地址，如地址的其他类型，使用预定义的格式。</span><span class="sxs-lookup"><span data-stu-id="f33fa-109">One-off addresses, like addresses of other types, use a predefined format.</span></span> <span data-ttu-id="f33fa-110">一次性地址的格式，如下所示由 MAPI 进行定义：</span><span class="sxs-lookup"><span data-stu-id="f33fa-110">The one-off address format is defined by MAPI as follows:</span></span>
  
`Display name[Address type:Email address]`
  
<span data-ttu-id="f33fa-111">没有为此格式的六个组件和有关报价字符某些规则。</span><span class="sxs-lookup"><span data-stu-id="f33fa-111">There are six components to this format and some rules about quoting characters.</span></span> <span data-ttu-id="f33fa-112">下表中介绍的组件。</span><span class="sxs-lookup"><span data-stu-id="f33fa-112">The components are described in the following table.</span></span>
  
|<span data-ttu-id="f33fa-113">**组件**</span><span class="sxs-lookup"><span data-stu-id="f33fa-113">**Component**</span></span>|<span data-ttu-id="f33fa-114">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="f33fa-114">**Usage**</span></span>|<span data-ttu-id="f33fa-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f33fa-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f33fa-116">显示名称</span><span class="sxs-lookup"><span data-stu-id="f33fa-116">Display name</span></span>  <br/> |<span data-ttu-id="f33fa-117">可选</span><span class="sxs-lookup"><span data-stu-id="f33fa-117">Optional</span></span>  <br/> |<span data-ttu-id="f33fa-118">如果不存在，则**IAddrBook::ResolveName**使用的电子邮件地址的可见部分用作显示名称。</span><span class="sxs-lookup"><span data-stu-id="f33fa-118">If not present, **IAddrBook::ResolveName** uses the visible part of the email address as the display name.</span></span> <span data-ttu-id="f33fa-119">可能包括空格。</span><span class="sxs-lookup"><span data-stu-id="f33fa-119">May include blanks.</span></span> <span data-ttu-id="f33fa-120">有关详细信息，请参阅[IAddrBook::ResolveName](iaddrbook-resolvename.md)。</span><span class="sxs-lookup"><span data-stu-id="f33fa-120">For more information, see [IAddrBook::ResolveName](iaddrbook-resolvename.md).</span></span>  <br/> |
|<span data-ttu-id="f33fa-121">[</span><span class="sxs-lookup"><span data-stu-id="f33fa-121"></span></span>  <br/> |<span data-ttu-id="f33fa-122">必需</span><span class="sxs-lookup"><span data-stu-id="f33fa-122">Required</span></span>  <br/> |<span data-ttu-id="f33fa-123">描绘的类型和地址信息的开头。</span><span class="sxs-lookup"><span data-stu-id="f33fa-123">Delineates the start of the type and address information.</span></span>  <br/> |
|<span data-ttu-id="f33fa-124">]</span><span class="sxs-lookup"><span data-stu-id="f33fa-124"></span></span>  <br/> |<span data-ttu-id="f33fa-125">必需</span><span class="sxs-lookup"><span data-stu-id="f33fa-125">Required</span></span>  <br/> |<span data-ttu-id="f33fa-126">描绘的类型和地址信息的末尾。</span><span class="sxs-lookup"><span data-stu-id="f33fa-126">Delineates the end of the type and address information.</span></span> <span data-ttu-id="f33fa-127">如果此字符后面空格以外的任何内容，输入不被视为一个自定义收件人。</span><span class="sxs-lookup"><span data-stu-id="f33fa-127">If anything other than white space follows this character, the entry is not treated as a custom recipient.</span></span>  <br/> |
|<span data-ttu-id="f33fa-128">地址类型</span><span class="sxs-lookup"><span data-stu-id="f33fa-128">Address type</span></span>  <br/> |<span data-ttu-id="f33fa-129">必需</span><span class="sxs-lookup"><span data-stu-id="f33fa-129">Required</span></span>  <br/> |<span data-ttu-id="f33fa-130">地址; 类型映射到特定地址格式。</span><span class="sxs-lookup"><span data-stu-id="f33fa-130">Type of address; maps to a specific address format.</span></span> <span data-ttu-id="f33fa-131">有关详细信息，请参阅[MAPI 地址类型](mapi-address-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f33fa-131">For more information, see [MAPI Address Types](mapi-address-types.md).</span></span>  <br/> |
|<span data-ttu-id="f33fa-132">:</span><span class="sxs-lookup"><span data-stu-id="f33fa-132"></span></span>  <br/> |<span data-ttu-id="f33fa-133">必需</span><span class="sxs-lookup"><span data-stu-id="f33fa-133">Required</span></span>  <br/> |<span data-ttu-id="f33fa-134">开来的电子邮件地址的地址类型。</span><span class="sxs-lookup"><span data-stu-id="f33fa-134">Separates the address type from the email address.</span></span>  <br/> |
|<span data-ttu-id="f33fa-135">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f33fa-135">Email address</span></span>  <br/> |<span data-ttu-id="f33fa-136">必需</span><span class="sxs-lookup"><span data-stu-id="f33fa-136">Required</span></span>  <br/> |<span data-ttu-id="f33fa-137">收件人地址。</span><span class="sxs-lookup"><span data-stu-id="f33fa-137">Address of the recipient.</span></span> <span data-ttu-id="f33fa-138">可能包括空格。</span><span class="sxs-lookup"><span data-stu-id="f33fa-138">May include blanks.</span></span>  <br/> |
   
<span data-ttu-id="f33fa-139">MAPI 使用报价字符的特定集允许地址包含左方括号 ([])，如逗号 （，） 的特殊字符和冒号 （:） 和一些 untypeable 字符，例如回车返回或线条源或任何其他十六进制等效。</span><span class="sxs-lookup"><span data-stu-id="f33fa-139">MAPI uses particular sets of quoting characters to allow addresses to contain special characters such as comma (,), left bracket ([), and colon (:) and some untypeable characters such as the carriage return or line feed or any other hexadecimal equivalent.</span></span> <span data-ttu-id="f33fa-140">报价字符是反斜杠 (\)。</span><span class="sxs-lookup"><span data-stu-id="f33fa-140">The quoting character is the backslash (\).</span></span> <span data-ttu-id="f33fa-141">因此，如果客户端或提供程序必须在地址插入反斜杠，它们必须低于它的报价字符 ("\\")。</span><span class="sxs-lookup"><span data-stu-id="f33fa-141">Therefore, if clients or providers must insert a backslash in an address, they must preceed it with the quoting character ("\\").</span></span>
  
<span data-ttu-id="f33fa-142">客户端和服务提供商可以使用此报价技术中的任何 nonfixed，可键入字段。</span><span class="sxs-lookup"><span data-stu-id="f33fa-142">Clients and service providers can use this quoting technique in any of the nonfixed, typeable fields.</span></span> <span data-ttu-id="f33fa-143">例如，以下条目转换为用作显示名称，作为地址类型，MSPEER Bill 李和\\billll\in 作为电子邮件地址：</span><span class="sxs-lookup"><span data-stu-id="f33fa-143">For example, the following entry translates to Bill Lee as the display name, MSPEER as the address type, and \\billll\in as the email address:</span></span>
  
`Bill Lee[MSPEER:\\\\billl\in]`

<span data-ttu-id="f33fa-144">要插入特殊 nontypeable 字符，客户端和服务提供商使用报价字符后跟 x 和两个十六进制数字表示等效其十六进制值。</span><span class="sxs-lookup"><span data-stu-id="f33fa-144">To insert special nontypeable characters, clients and service providers use a quoting character followed by an x and two hexadecimal digits to represent their hexadecimal equivalent.</span></span> <span data-ttu-id="f33fa-145">例如，如果某个地址具有等同于回车符 nontypeable 字符返回，(\0d) 十六进制数，在客户端应输入为：</span><span class="sxs-lookup"><span data-stu-id="f33fa-145">For example, if an address has a nontypeable character that equates to a carriage return, (\0d) in hexadecimal, a client would enter them as:</span></span>
  
`Fax Recipient[fax:recipient\x0dbuilding\x0doffice\x0d555-1212\x0d]`

<span data-ttu-id="f33fa-146">**IAddrBook::ResolveName**还会自动分析大多数 SMTP 地址，查找具有以下格式的地址：</span><span class="sxs-lookup"><span data-stu-id="f33fa-146">**IAddrBook::ResolveName** also automatically parses most SMTP addresses, looking for addresses with the following format:</span></span> 
  
`XXX@YYY.ZZZ`

<span data-ttu-id="f33fa-147">尽管不是所有可能的附加了 RFC822 格式进行处理，此自动分析足以满足大多数用户。</span><span class="sxs-lookup"><span data-stu-id="f33fa-147">Although not all of the possible RFC822 formats are handled, this automatic parsing is adequate for most users.</span></span> <span data-ttu-id="f33fa-148">**ResolveName**包括此功能，以使用户可以直接在消息输入 SMTP 地址并转到 Internet 用户的消息。</span><span class="sxs-lookup"><span data-stu-id="f33fa-148">**ResolveName** includes this functionality to enable users to enter SMTP addresses directly into a message and have that message go to the Internet user.</span></span> <span data-ttu-id="f33fa-149">XXX、 YYY 和 ZZZ 组件的地址可以是一个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="f33fa-149">The XXX, YYY, and ZZZ components of the address can be one or more characters.</span></span> <span data-ttu-id="f33fa-150">At 符号 (@) 不能包含在地址 XXX、 YYY 或 ZZZ 组件和 YYY 组件也不能包含时间段。</span><span class="sxs-lookup"><span data-stu-id="f33fa-150">The at sign (@) cannot be included in either the XXX, YYY, or ZZZ address components and the YYY component also cannot include the period.</span></span> <span data-ttu-id="f33fa-151">由于以下字符是 SMTP 地址中的特殊字符，MAPI 自动转换为一次性地址包含这些字符的显示名称：</span><span class="sxs-lookup"><span data-stu-id="f33fa-151">Because the following characters are special characters in SMTP addresses, MAPI automatically converts a display name containing these characters into a one-off address:</span></span> 
  
- \>\>
    
- @
    
- \<\>
    
- <span data-ttu-id="f33fa-152">.</span><span class="sxs-lookup"><span data-stu-id="f33fa-152"></span></span>
    
<span data-ttu-id="f33fa-153">每个一次性地址分配相应的一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f33fa-153">Every one-off address is assigned a corresponding one-off entry identifier.</span></span> <span data-ttu-id="f33fa-154">若要使此工作分配，客户端调用**IAddrBook::CreateOneOff**和传输提供程序调用**IMAPISupport::CreateOneOff**。</span><span class="sxs-lookup"><span data-stu-id="f33fa-154">To make this assignment, clients call **IAddrBook::CreateOneOff** and transport providers call **IMAPISupport::CreateOneOff**.</span></span> <span data-ttu-id="f33fa-155">有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="f33fa-155">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) and [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span> <span data-ttu-id="f33fa-156">处理传入消息时, 传输提供程序创建一次性条目标识符网关地址和传输类型的关联的通讯簿提供程序无法处理的地址。</span><span class="sxs-lookup"><span data-stu-id="f33fa-156">When processing incoming messages, transport providers create one-off entry identifiers for gateway addresses and for addresses that cannot be handled by the transport's associated address book providers.</span></span> <span data-ttu-id="f33fa-157">传输提供程序检查邮件以确定它可以由传输类型相关联的通讯簿提供程序来处理中每个地址的类型。</span><span class="sxs-lookup"><span data-stu-id="f33fa-157">Transport providers check the type of each address in a message to determine if it can be handled by an address book provider associated with the transport.</span></span> <span data-ttu-id="f33fa-158">如果它无法传输提供程序调用**IMAPISupport::CreateOneOff**一次性条目标识符与关联的地址。</span><span class="sxs-lookup"><span data-stu-id="f33fa-158">If it cannot, transport providers call **IMAPISupport::CreateOneOff** to associate the address with a one-off entry identifier.</span></span> 
  
<span data-ttu-id="f33fa-159">一次性条目标识符按以下顺序包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="f33fa-159">One-off entry identifiers include the following information in the following order:</span></span>
  
1. <span data-ttu-id="f33fa-160">**MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="f33fa-160">**MAPIUID**</span></span>
    
2. <span data-ttu-id="f33fa-161">版本</span><span class="sxs-lookup"><span data-stu-id="f33fa-161">Version</span></span>
    
3. <span data-ttu-id="f33fa-162">Flags</span><span class="sxs-lookup"><span data-stu-id="f33fa-162">Flags</span></span>
    
4. <span data-ttu-id="f33fa-163">显示名称</span><span class="sxs-lookup"><span data-stu-id="f33fa-163">Display name</span></span>
    
5. <span data-ttu-id="f33fa-164">地址类型</span><span class="sxs-lookup"><span data-stu-id="f33fa-164">Address type</span></span>
    
6. <span data-ttu-id="f33fa-165">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f33fa-165">Email address</span></span>
    
<span data-ttu-id="f33fa-166">在调用**IAddrBook::CreateOneOff**和**IMAPISupport::CreateOneOff**，客户端和传输提供程序可以设置一个标志，指示由一次性地址的收件人可以处理带格式的文本或嵌入 OLE对象。</span><span class="sxs-lookup"><span data-stu-id="f33fa-166">In the calls to **IAddrBook::CreateOneOff** and **IMAPISupport::CreateOneOff**, clients and transport providers can set a flag that indicates whether or not the recipient represented by the one-off address can process formatted text or embedded OLE objects.</span></span> <span data-ttu-id="f33fa-167">指示收件人可以处理带格式的文本和 OLE 对象，客户端和传输提供程序集_ulFlags_参数中的 MAPI_SEND_NO_RICH_INFO 标志。</span><span class="sxs-lookup"><span data-stu-id="f33fa-167">To indicate that a recipient can handle formatted text and OLE objects, clients and transport providers set the MAPI_SEND_NO_RICH_INFO flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="f33fa-168">然后，MAPI 将一次性收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="f33fa-168">MAPI then sets the one-off recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property to FALSE.</span></span> <span data-ttu-id="f33fa-169">当未设置此标志时，MAPI 设为 TRUE **PR_SEND_RICH_INFO** ，除非一次性地址被解释为 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="f33fa-169">When this flag is not set, MAPI sets **PR_SEND_RICH_INFO** to TRUE unless the one-off address is interpreted as an SMTP address.</span></span> <span data-ttu-id="f33fa-170">在本例一个**PR_SEND_RICH_INFO**默认为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="f33fa-170">In this one case, **PR_SEND_RICH_INFO** defaults to FALSE.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f33fa-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f33fa-171">See also</span></span>

- [<span data-ttu-id="f33fa-172">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="f33fa-172">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)

