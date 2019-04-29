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
ms.openlocfilehash: e6bda55951d8df5c5da272750c631ec105b2ccf2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409109"
---
# <a name="one-off-addresses"></a><span data-ttu-id="731f1-103">一次性地址</span><span class="sxs-lookup"><span data-stu-id="731f1-103">One-off addresses</span></span>

<span data-ttu-id="731f1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="731f1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="731f1-105">一次性地址用于向一次性收件人 (在任何会话的通讯簿容器中没有相应条目的收件人) 发送邮件。</span><span class="sxs-lookup"><span data-stu-id="731f1-105">One-off addresses are used to send messages to one-off recipients, recipients that do not have a corresponding entry in any of the session's address book containers.</span></span> <span data-ttu-id="731f1-106">客户端可以在向通讯簿添加新条目或向传出邮件的收件人列表中添加新条目时创建一次性地址。</span><span class="sxs-lookup"><span data-stu-id="731f1-106">Clients can create one-off addresses when they add new entries to the address book or new recipients to the recipient list of an outgoing message.</span></span> <span data-ttu-id="731f1-107">可以将一次性地址添加到任何可修改的容器中。</span><span class="sxs-lookup"><span data-stu-id="731f1-107">One-off addresses can be added to any container that is modifiable.</span></span>
  
<span data-ttu-id="731f1-108">若要创建一次性地址, 客户端应使用包含编辑控件的特殊模板, 以输入构成一次性地址的所有信息。</span><span class="sxs-lookup"><span data-stu-id="731f1-108">To create a one-off address, clients use a special template containing edit controls for entering all of the information that makes up a one-off address.</span></span> <span data-ttu-id="731f1-109">一次性地址, 如其他类型的地址, 使用预定义的格式。</span><span class="sxs-lookup"><span data-stu-id="731f1-109">One-off addresses, like addresses of other types, use a predefined format.</span></span> <span data-ttu-id="731f1-110">一次性地址格式由 MAPI 定义, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="731f1-110">The one-off address format is defined by MAPI as follows:</span></span>
  
`Display name[Address type:Email address]`
  
<span data-ttu-id="731f1-111">此格式有六个组件和一些关于引号字符的规则。</span><span class="sxs-lookup"><span data-stu-id="731f1-111">There are six components to this format and some rules about quoting characters.</span></span> <span data-ttu-id="731f1-112">下表中介绍了这些组件。</span><span class="sxs-lookup"><span data-stu-id="731f1-112">The components are described in the following table.</span></span>
  
|<span data-ttu-id="731f1-113">**组件**</span><span class="sxs-lookup"><span data-stu-id="731f1-113">**Component**</span></span>|<span data-ttu-id="731f1-114">**用法**</span><span class="sxs-lookup"><span data-stu-id="731f1-114">**Usage**</span></span>|<span data-ttu-id="731f1-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="731f1-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="731f1-116">可分辨名称 (DN)</span><span class="sxs-lookup"><span data-stu-id="731f1-116">Display name</span></span>  <br/> |<span data-ttu-id="731f1-117">可选</span><span class="sxs-lookup"><span data-stu-id="731f1-117">Optional</span></span>  <br/> |<span data-ttu-id="731f1-118">如果不存在, 则**IAddrBook:: ResolveName**使用电子邮件地址的可见部分作为显示名称。</span><span class="sxs-lookup"><span data-stu-id="731f1-118">If not present, **IAddrBook::ResolveName** uses the visible part of the email address as the display name.</span></span> <span data-ttu-id="731f1-119">可能包含空格。</span><span class="sxs-lookup"><span data-stu-id="731f1-119">May include blanks.</span></span> <span data-ttu-id="731f1-120">有关详细信息, 请参阅[IAddrBook:: ResolveName](iaddrbook-resolvename.md)。</span><span class="sxs-lookup"><span data-stu-id="731f1-120">For more information, see [IAddrBook::ResolveName](iaddrbook-resolvename.md).</span></span>  <br/> |
|<span data-ttu-id="731f1-121">[</span><span class="sxs-lookup"><span data-stu-id="731f1-121"></span></span>  <br/> |<span data-ttu-id="731f1-122">必需</span><span class="sxs-lookup"><span data-stu-id="731f1-122">Required</span></span>  <br/> |<span data-ttu-id="731f1-123">描述了类型和地址信息的开头。</span><span class="sxs-lookup"><span data-stu-id="731f1-123">Delineates the start of the type and address information.</span></span>  <br/> |
|<span data-ttu-id="731f1-124">]</span><span class="sxs-lookup"><span data-stu-id="731f1-124"></span></span>  <br/> |<span data-ttu-id="731f1-125">必需</span><span class="sxs-lookup"><span data-stu-id="731f1-125">Required</span></span>  <br/> |<span data-ttu-id="731f1-126">描述了键入和地址信息的结尾。</span><span class="sxs-lookup"><span data-stu-id="731f1-126">Delineates the end of the type and address information.</span></span> <span data-ttu-id="731f1-127">如果除空格之外的任何内容都跟在此字符之后, 则不会将该条目视为自定义收件人。</span><span class="sxs-lookup"><span data-stu-id="731f1-127">If anything other than white space follows this character, the entry is not treated as a custom recipient.</span></span>  <br/> |
|<span data-ttu-id="731f1-128">地址类型</span><span class="sxs-lookup"><span data-stu-id="731f1-128">Address type</span></span>  <br/> |<span data-ttu-id="731f1-129">必需</span><span class="sxs-lookup"><span data-stu-id="731f1-129">Required</span></span>  <br/> |<span data-ttu-id="731f1-130">地址类型;映射到特定地址格式。</span><span class="sxs-lookup"><span data-stu-id="731f1-130">Type of address; maps to a specific address format.</span></span> <span data-ttu-id="731f1-131">有关详细信息, 请参阅[MAPI 地址类型](mapi-address-types.md)。</span><span class="sxs-lookup"><span data-stu-id="731f1-131">For more information, see [MAPI Address Types](mapi-address-types.md).</span></span>  <br/> |
|<span data-ttu-id="731f1-132">:</span><span class="sxs-lookup"><span data-stu-id="731f1-132"></span></span>  <br/> |<span data-ttu-id="731f1-133">必需</span><span class="sxs-lookup"><span data-stu-id="731f1-133">Required</span></span>  <br/> |<span data-ttu-id="731f1-134">将地址类型与电子邮件地址分隔开。</span><span class="sxs-lookup"><span data-stu-id="731f1-134">Separates the address type from the email address.</span></span>  <br/> |
|<span data-ttu-id="731f1-135">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="731f1-135">Email address</span></span>  <br/> |<span data-ttu-id="731f1-136">必需</span><span class="sxs-lookup"><span data-stu-id="731f1-136">Required</span></span>  <br/> |<span data-ttu-id="731f1-137">收件人的地址。</span><span class="sxs-lookup"><span data-stu-id="731f1-137">Address of the recipient.</span></span> <span data-ttu-id="731f1-138">可能包含空格。</span><span class="sxs-lookup"><span data-stu-id="731f1-138">May include blanks.</span></span>  <br/> |
   
<span data-ttu-id="731f1-139">MAPI 使用特定的一组引用字符来允许地址包含特殊字符, 如逗号 (,)、左方括号 ([) 和冒号 (:)以及一些 untypeable 字符 (如回车符或换行符) 或任何其他十六进制等效项。</span><span class="sxs-lookup"><span data-stu-id="731f1-139">MAPI uses particular sets of quoting characters to allow addresses to contain special characters such as comma (,), left bracket ([), and colon (:) and some untypeable characters such as the carriage return or line feed or any other hexadecimal equivalent.</span></span> <span data-ttu-id="731f1-140">引号字符是反斜杠 (\)。</span><span class="sxs-lookup"><span data-stu-id="731f1-140">The quoting character is the backslash (\).</span></span> <span data-ttu-id="731f1-141">因此, 如果客户端或提供程序必须在地址中插入反斜杠, 则必须使用引号字符 ("\\") 将其 preceed。</span><span class="sxs-lookup"><span data-stu-id="731f1-141">Therefore, if clients or providers must insert a backslash in an address, they must preceed it with the quoting character ("\\").</span></span>
  
<span data-ttu-id="731f1-142">客户端和服务提供商可以在任何 nonfixed (种) 字段中使用此报价技术。</span><span class="sxs-lookup"><span data-stu-id="731f1-142">Clients and service providers can use this quoting technique in any of the nonfixed, typeable fields.</span></span> <span data-ttu-id="731f1-143">例如, 以下条目转换为 "记帐名称"、"MSPEER" 作为 "地址类型" 和\\"billll\in" 作为电子邮件地址:</span><span class="sxs-lookup"><span data-stu-id="731f1-143">For example, the following entry translates to Bill Lee as the display name, MSPEER as the address type, and \\billll\in as the email address:</span></span>
  
`Bill Lee[MSPEER:\\\\billl\in]`

<span data-ttu-id="731f1-144">若要插入特殊的 nontypeable 字符, 客户端和服务提供程序使用带引号的字符, 后跟 x 和2个十六进制数字来表示它们的十六进制等效项。</span><span class="sxs-lookup"><span data-stu-id="731f1-144">To insert special nontypeable characters, clients and service providers use a quoting character followed by an x and two hexadecimal digits to represent their hexadecimal equivalent.</span></span> <span data-ttu-id="731f1-145">例如, 如果地址的 nontypeable 字符等于回车 (\0d), 则客户端会输入以下字符:</span><span class="sxs-lookup"><span data-stu-id="731f1-145">For example, if an address has a nontypeable character that equates to a carriage return, (\0d) in hexadecimal, a client would enter them as:</span></span>
  
`Fax Recipient[fax:recipient\x0dbuilding\x0doffice\x0d555-1212\x0d]`

<span data-ttu-id="731f1-146">**IAddrBook:: ResolveName**还会自动分析大多数 SMTP 地址, 查找具有以下格式的地址:</span><span class="sxs-lookup"><span data-stu-id="731f1-146">**IAddrBook::ResolveName** also automatically parses most SMTP addresses, looking for addresses with the following format:</span></span> 
  
`XXX@YYY.ZZZ`

<span data-ttu-id="731f1-147">虽然并非所有可能的/rfc822 格式都得到处理, 但这种自动分析足以满足大多数用户的情况。</span><span class="sxs-lookup"><span data-stu-id="731f1-147">Although not all of the possible RFC822 formats are handled, this automatic parsing is adequate for most users.</span></span> <span data-ttu-id="731f1-148">**ResolveName**包括此功能, 使用户能够直接在邮件中输入 SMTP 地址, 并让该邮件转到 Internet 用户。</span><span class="sxs-lookup"><span data-stu-id="731f1-148">**ResolveName** includes this functionality to enable users to enter SMTP addresses directly into a message and have that message go to the Internet user.</span></span> <span data-ttu-id="731f1-149">XXX、YYY 和 ZZZ 组件的地址可以是一个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="731f1-149">The XXX, YYY, and ZZZ components of the address can be one or more characters.</span></span> <span data-ttu-id="731f1-150">at 符号 (@) 不能包含在 XXX、yyy 或 ZZZ 地址组件中, YYY 组件也不能包含句点。</span><span class="sxs-lookup"><span data-stu-id="731f1-150">The at sign (@) cannot be included in either the XXX, YYY, or ZZZ address components and the YYY component also cannot include the period.</span></span> <span data-ttu-id="731f1-151">由于以下字符是 SMTP 地址中的特殊字符, 因此 MAPI 会自动将包含这些字符的显示名称转换为一次性地址:</span><span class="sxs-lookup"><span data-stu-id="731f1-151">Because the following characters are special characters in SMTP addresses, MAPI automatically converts a display name containing these characters into a one-off address:</span></span> 
  
- \>\>
    
- @
    
- \<\>
    
- <span data-ttu-id="731f1-152">.</span><span class="sxs-lookup"><span data-stu-id="731f1-152"></span></span>
    
<span data-ttu-id="731f1-153">为每个一次性地址分配一个对应的一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="731f1-153">Every one-off address is assigned a corresponding one-off entry identifier.</span></span> <span data-ttu-id="731f1-154">若要进行此分配, 客户端可以调用**IAddrBook:: CreateOneOff**和 transport providers, 调用**IMAPISupport:: CreateOneOff**。</span><span class="sxs-lookup"><span data-stu-id="731f1-154">To make this assignment, clients call **IAddrBook::CreateOneOff** and transport providers call **IMAPISupport::CreateOneOff**.</span></span> <span data-ttu-id="731f1-155">有关详细信息, 请参阅[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="731f1-155">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) and [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span> <span data-ttu-id="731f1-156">在处理传入邮件时, 传输提供程序为网关地址和传输的关联通讯簿提供程序无法处理的地址创建一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="731f1-156">When processing incoming messages, transport providers create one-off entry identifiers for gateway addresses and for addresses that cannot be handled by the transport's associated address book providers.</span></span> <span data-ttu-id="731f1-157">传输提供程序检查邮件中每个地址的类型, 以确定是否可以通过与传输关联的通讯簿提供程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="731f1-157">Transport providers check the type of each address in a message to determine if it can be handled by an address book provider associated with the transport.</span></span> <span data-ttu-id="731f1-158">如果不能, 传输提供程序将调用**IMAPISupport:: CreateOneOff**以将地址与一次性条目标识符相关联。</span><span class="sxs-lookup"><span data-stu-id="731f1-158">If it cannot, transport providers call **IMAPISupport::CreateOneOff** to associate the address with a one-off entry identifier.</span></span> 
  
<span data-ttu-id="731f1-159">一次性条目标识符按以下顺序包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="731f1-159">One-off entry identifiers include the following information in the following order:</span></span>
  
1. <span data-ttu-id="731f1-160">**MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="731f1-160">**MAPIUID**</span></span>
    
2. <span data-ttu-id="731f1-161">版本</span><span class="sxs-lookup"><span data-stu-id="731f1-161">Version</span></span>
    
3. <span data-ttu-id="731f1-162">Flags</span><span class="sxs-lookup"><span data-stu-id="731f1-162">Flags</span></span>
    
4. <span data-ttu-id="731f1-163">可分辨名称 (DN)</span><span class="sxs-lookup"><span data-stu-id="731f1-163">Display name</span></span>
    
5. <span data-ttu-id="731f1-164">地址类型</span><span class="sxs-lookup"><span data-stu-id="731f1-164">Address type</span></span>
    
6. <span data-ttu-id="731f1-165">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="731f1-165">Email address</span></span>
    
<span data-ttu-id="731f1-166">在对**IAddrBook:: CreateOneOff**和**IMAPISupport:: CreateOneOff**、客户端和传输提供程序的调用中, 可以设置一个标志, 该标志指示由一次性地址表示的收件人是否可以处理格式化文本或嵌入的 OLE对象.</span><span class="sxs-lookup"><span data-stu-id="731f1-166">In the calls to **IAddrBook::CreateOneOff** and **IMAPISupport::CreateOneOff**, clients and transport providers can set a flag that indicates whether or not the recipient represented by the one-off address can process formatted text or embedded OLE objects.</span></span> <span data-ttu-id="731f1-167">若要指示收件人可以处理带格式的文本和 OLE 对象, 客户端和传输提供程序在_ulFlags_参数中设置 MAPI_SEND_NO_RICH_INFO 标志。</span><span class="sxs-lookup"><span data-stu-id="731f1-167">To indicate that a recipient can handle formatted text and OLE objects, clients and transport providers set the MAPI_SEND_NO_RICH_INFO flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="731f1-168">MAPI 然后将一次性收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="731f1-168">MAPI then sets the one-off recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property to FALSE.</span></span> <span data-ttu-id="731f1-169">如果未设置此标志, 则 MAPI 会将**PR_SEND_RICH_INFO**设置为 TRUE, 除非将一次性地址解释为 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="731f1-169">When this flag is not set, MAPI sets **PR_SEND_RICH_INFO** to TRUE unless the one-off address is interpreted as an SMTP address.</span></span> <span data-ttu-id="731f1-170">在这种情况下, **PR_SEND_RICH_INFO**默认为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="731f1-170">In this one case, **PR_SEND_RICH_INFO** defaults to FALSE.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="731f1-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="731f1-171">See also</span></span>

- [<span data-ttu-id="731f1-172">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="731f1-172">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)

