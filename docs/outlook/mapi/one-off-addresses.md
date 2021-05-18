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
# <a name="one-off-addresses"></a><span data-ttu-id="f7d2a-103">一次性地址</span><span class="sxs-lookup"><span data-stu-id="f7d2a-103">One-off addresses</span></span>

<span data-ttu-id="f7d2a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7d2a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7d2a-105">一对一地址用于向一次收件人（该收件人在任何会话的通讯簿容器中没有对应条目的收件人）发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-105">One-off addresses are used to send messages to one-off recipients, recipients that do not have a corresponding entry in any of the session's address book containers.</span></span> <span data-ttu-id="f7d2a-106">客户端在将新条目添加到通讯簿或将新收件人添加到传出邮件的收件人列表时，可以创建一次地址。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-106">Clients can create one-off addresses when they add new entries to the address book or new recipients to the recipient list of an outgoing message.</span></span> <span data-ttu-id="f7d2a-107">一次使用地址可以添加到任何可修改的容器中。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-107">One-off addresses can be added to any container that is modifiable.</span></span>
  
<span data-ttu-id="f7d2a-108">若要创建一次地址，客户端使用包含编辑控件的特殊模板来输入所有信息，这些信息将形成一次地址。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-108">To create a one-off address, clients use a special template containing edit controls for entering all of the information that makes up a one-off address.</span></span> <span data-ttu-id="f7d2a-109">一次使用地址（如其他类型的地址）使用预定义格式。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-109">One-off addresses, like addresses of other types, use a predefined format.</span></span> <span data-ttu-id="f7d2a-110">一次地址格式由 MAPI 定义，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7d2a-110">The one-off address format is defined by MAPI as follows:</span></span>
  
`Display name[Address type:Email address]`
  
<span data-ttu-id="f7d2a-111">此格式包含六个要素和一些有关引用字符的规则。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-111">There are six components to this format and some rules about quoting characters.</span></span> <span data-ttu-id="f7d2a-112">下表介绍了这些组件。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-112">The components are described in the following table.</span></span>
  
|<span data-ttu-id="f7d2a-113">**组件**</span><span class="sxs-lookup"><span data-stu-id="f7d2a-113">**Component**</span></span>|<span data-ttu-id="f7d2a-114">**用法**</span><span class="sxs-lookup"><span data-stu-id="f7d2a-114">**Usage**</span></span>|<span data-ttu-id="f7d2a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f7d2a-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7d2a-116">显示名称</span><span class="sxs-lookup"><span data-stu-id="f7d2a-116">Display name</span></span>  <br/> |<span data-ttu-id="f7d2a-117">可选</span><span class="sxs-lookup"><span data-stu-id="f7d2a-117">Optional</span></span>  <br/> |<span data-ttu-id="f7d2a-118">如果不存在 **，IAddrBook：：ResolveName** 使用电子邮件地址的可见部分作为显示名称。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-118">If not present, **IAddrBook::ResolveName** uses the visible part of the email address as the display name.</span></span> <span data-ttu-id="f7d2a-119">可能包括空白。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-119">May include blanks.</span></span> <span data-ttu-id="f7d2a-120">有关详细信息，请参阅 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-120">For more information, see [IAddrBook::ResolveName](iaddrbook-resolvename.md).</span></span>  <br/> |
|<span data-ttu-id="f7d2a-121">[</span><span class="sxs-lookup"><span data-stu-id="f7d2a-121">[</span></span>  <br/> |<span data-ttu-id="f7d2a-122">必需</span><span class="sxs-lookup"><span data-stu-id="f7d2a-122">Required</span></span>  <br/> |<span data-ttu-id="f7d2a-123">描述类型和地址信息的开始。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-123">Delineates the start of the type and address information.</span></span>  <br/> |
|<span data-ttu-id="f7d2a-124">]</span><span class="sxs-lookup"><span data-stu-id="f7d2a-124">]</span></span>  <br/> |<span data-ttu-id="f7d2a-125">必需</span><span class="sxs-lookup"><span data-stu-id="f7d2a-125">Required</span></span>  <br/> |<span data-ttu-id="f7d2a-126">描述类型和地址信息的结尾。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-126">Delineates the end of the type and address information.</span></span> <span data-ttu-id="f7d2a-127">如果此字符后跟空格外的其他任何内容，则不将条目视为自定义收件人。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-127">If anything other than white space follows this character, the entry is not treated as a custom recipient.</span></span>  <br/> |
|<span data-ttu-id="f7d2a-128">地址类型</span><span class="sxs-lookup"><span data-stu-id="f7d2a-128">Address type</span></span>  <br/> |<span data-ttu-id="f7d2a-129">必需</span><span class="sxs-lookup"><span data-stu-id="f7d2a-129">Required</span></span>  <br/> |<span data-ttu-id="f7d2a-130">地址类型;映射到特定地址格式。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-130">Type of address; maps to a specific address format.</span></span> <span data-ttu-id="f7d2a-131">有关详细信息，请参阅 [MAPI 地址类型](mapi-address-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-131">For more information, see [MAPI Address Types](mapi-address-types.md).</span></span>  <br/> |
|<span data-ttu-id="f7d2a-132">:</span><span class="sxs-lookup"><span data-stu-id="f7d2a-132">:</span></span>  <br/> |<span data-ttu-id="f7d2a-133">必需</span><span class="sxs-lookup"><span data-stu-id="f7d2a-133">Required</span></span>  <br/> |<span data-ttu-id="f7d2a-134">将地址类型与电子邮件地址分开。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-134">Separates the address type from the email address.</span></span>  <br/> |
|<span data-ttu-id="f7d2a-135">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f7d2a-135">Email address</span></span>  <br/> |<span data-ttu-id="f7d2a-136">必需</span><span class="sxs-lookup"><span data-stu-id="f7d2a-136">Required</span></span>  <br/> |<span data-ttu-id="f7d2a-137">收件人的地址。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-137">Address of the recipient.</span></span> <span data-ttu-id="f7d2a-138">可能包括空白。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-138">May include blanks.</span></span>  <br/> |
   
<span data-ttu-id="f7d2a-139">MAPI 使用特定的引文字符集允许地址包含特殊字符，如逗号 (，) 、左方括号 ([) 和冒号 (：) 以及一些不可键入的字符，如回车符或换行符或其他任何十六进制等效字符。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-139">MAPI uses particular sets of quoting characters to allow addresses to contain special characters such as comma (,), left bracket ([), and colon (:) and some untypeable characters such as the carriage return or line feed or any other hexadecimal equivalent.</span></span> <span data-ttu-id="f7d2a-140">该引文字符是反杠 (\) 。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-140">The quoting character is the backslash (\).</span></span> <span data-ttu-id="f7d2a-141">因此，如果客户端或提供商必须在地址中插入反杠，则必须在地址前加一个 \\ ("") 。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-141">Therefore, if clients or providers must insert a backslash in an address, they must preceed it with the quoting character ("\\").</span></span>
  
<span data-ttu-id="f7d2a-142">客户端和服务提供商可以在任何非fixed的可键入字段中使用此引文技术。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-142">Clients and service providers can use this quoting technique in any of the nonfixed, typeable fields.</span></span> <span data-ttu-id="f7d2a-143">例如，以下条目转换为 Bill Lee 作为显示名称，将 MSPEER 转换为地址类型， \\ 将 billll\in 转换为电子邮件地址：</span><span class="sxs-lookup"><span data-stu-id="f7d2a-143">For example, the following entry translates to Bill Lee as the display name, MSPEER as the address type, and \\billll\in as the email address:</span></span>
  
`Bill Lee[MSPEER:\\\\billl\in]`

<span data-ttu-id="f7d2a-144">为了插入特殊不可键入的字符，客户端和服务提供商使用后跟 x 和两个十六进制数字的商数来表示它们的十六进制等效字符。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-144">To insert special nontypeable characters, clients and service providers use a quoting character followed by an x and two hexadecimal digits to represent their hexadecimal equivalent.</span></span> <span data-ttu-id="f7d2a-145">例如，如果地址具有一个等号为回车的不可键入字符， (\0d) 十六进制，则客户端会按如下方式输入：</span><span class="sxs-lookup"><span data-stu-id="f7d2a-145">For example, if an address has a nontypeable character that equates to a carriage return, (\0d) in hexadecimal, a client would enter them as:</span></span>
  
`Fax Recipient[fax:recipient\x0dbuilding\x0doffice\x0d555-1212\x0d]`

<span data-ttu-id="f7d2a-146">**IAddrBook：：ResolveName** 还自动分析大多数 SMTP 地址，查找具有以下格式的地址：</span><span class="sxs-lookup"><span data-stu-id="f7d2a-146">**IAddrBook::ResolveName** also automatically parses most SMTP addresses, looking for addresses with the following format:</span></span> 
  
`XXX@YYY.ZZZ`

<span data-ttu-id="f7d2a-147">虽然并非所有可能的 RFC822 格式都得到处理，但此自动分析足以满足大多数用户的需求。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-147">Although not all of the possible RFC822 formats are handled, this automatic parsing is adequate for most users.</span></span> <span data-ttu-id="f7d2a-148">**ResolveName** 包含此功能，使用户可以直接在邮件中输入 SMTP 地址，并且使该邮件转到 Internet 用户。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-148">**ResolveName** includes this functionality to enable users to enter SMTP addresses directly into a message and have that message go to the Internet user.</span></span> <span data-ttu-id="f7d2a-149">地址的 XXX、YYY 和 ZZZ 组件可以是一个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-149">The XXX, YYY, and ZZZ components of the address can be one or more characters.</span></span> <span data-ttu-id="f7d2a-150">AT 符号 (@) 不能包含在 XXX、YYY 或 ZZZ 地址组件中，并且 YYY 组件也不能包含期间。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-150">The at sign (@) cannot be included in either the XXX, YYY, or ZZZ address components and the YYY component also cannot include the period.</span></span> <span data-ttu-id="f7d2a-151">由于以下字符是 SMTP 地址中的特殊字符，MAPI 会自动显示名称包含这些字符的字符串转换为一次地址：</span><span class="sxs-lookup"><span data-stu-id="f7d2a-151">Because the following characters are special characters in SMTP addresses, MAPI automatically converts a display name containing these characters into a one-off address:</span></span> 
  
- \>\>
    
- @
    
- \<\>
    
- <span data-ttu-id="f7d2a-152">.</span><span class="sxs-lookup"><span data-stu-id="f7d2a-152">.</span></span>
    
<span data-ttu-id="f7d2a-153">每个一次地址都分配有一个对应的一次输入标识符。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-153">Every one-off address is assigned a corresponding one-off entry identifier.</span></span> <span data-ttu-id="f7d2a-154">为了进行此分配，客户端调用 **IAddrBook：：CreateOneOff，** 传输提供程序 **调用 IMAPISupport：：CreateOneOff**。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-154">To make this assignment, clients call **IAddrBook::CreateOneOff** and transport providers call **IMAPISupport::CreateOneOff**.</span></span> <span data-ttu-id="f7d2a-155">有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md) 和 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-155">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) and [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span> <span data-ttu-id="f7d2a-156">处理传入邮件时，传输提供程序会为网关地址和传输的关联通讯簿提供程序无法处理的地址创建一次条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-156">When processing incoming messages, transport providers create one-off entry identifiers for gateway addresses and for addresses that cannot be handled by the transport's associated address book providers.</span></span> <span data-ttu-id="f7d2a-157">传输提供程序检查邮件中每个地址的类型，以确定该地址是否可以通过与传输关联的通讯簿提供程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-157">Transport providers check the type of each address in a message to determine if it can be handled by an address book provider associated with the transport.</span></span> <span data-ttu-id="f7d2a-158">如果无法，传输提供程序将调用 **IMAPISupport：：CreateOneOff** 以将地址与一次输入标识符关联。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-158">If it cannot, transport providers call **IMAPISupport::CreateOneOff** to associate the address with a one-off entry identifier.</span></span> 
  
<span data-ttu-id="f7d2a-159">一次输入标识符按以下顺序包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="f7d2a-159">One-off entry identifiers include the following information in the following order:</span></span>
  
1. <span data-ttu-id="f7d2a-160">**MAPIUID**</span><span class="sxs-lookup"><span data-stu-id="f7d2a-160">**MAPIUID**</span></span>
    
2. <span data-ttu-id="f7d2a-161">版本</span><span class="sxs-lookup"><span data-stu-id="f7d2a-161">Version</span></span>
    
3. <span data-ttu-id="f7d2a-162">Flags</span><span class="sxs-lookup"><span data-stu-id="f7d2a-162">Flags</span></span>
    
4. <span data-ttu-id="f7d2a-163">显示名称</span><span class="sxs-lookup"><span data-stu-id="f7d2a-163">Display name</span></span>
    
5. <span data-ttu-id="f7d2a-164">地址类型</span><span class="sxs-lookup"><span data-stu-id="f7d2a-164">Address type</span></span>
    
6. <span data-ttu-id="f7d2a-165">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f7d2a-165">Email address</span></span>
    
<span data-ttu-id="f7d2a-166">在调用 **IAddrBook：：CreateOneOff** 和 **IMAPISupport：：CreateOneOff** 时，客户端和传输提供程序可以设置一个标志，指示一次使用地址表示的收件人是否可以处理格式化的文本或嵌入的 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-166">In the calls to **IAddrBook::CreateOneOff** and **IMAPISupport::CreateOneOff**, clients and transport providers can set a flag that indicates whether or not the recipient represented by the one-off address can process formatted text or embedded OLE objects.</span></span> <span data-ttu-id="f7d2a-167">为了指示收件人可以处理格式化的文本和 OLE 对象，客户端和传输提供程序在  _ulFlags_ MAPI_SEND_NO_RICH_INFO设置 MAPI_SEND_NO_RICH_INFO 标记。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-167">To indicate that a recipient can handle formatted text and OLE objects, clients and transport providers set the MAPI_SEND_NO_RICH_INFO flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="f7d2a-168">然后，MAPI 将[PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md) PR_SEND_RICH_INFO (一次收件人) 属性为 FALSE。 </span><span class="sxs-lookup"><span data-stu-id="f7d2a-168">MAPI then sets the one-off recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property to FALSE.</span></span> <span data-ttu-id="f7d2a-169">未设置此标志时，MAPI PR_SEND_RICH_INFO设置为 TRUE，除非一次使用的地址被解释为 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-169">When this flag is not set, MAPI sets **PR_SEND_RICH_INFO** to TRUE unless the one-off address is interpreted as an SMTP address.</span></span> <span data-ttu-id="f7d2a-170">在这一 **种情况下，PR_SEND_RICH_INFO** 默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="f7d2a-170">In this one case, **PR_SEND_RICH_INFO** defaults to FALSE.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f7d2a-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d2a-171">See also</span></span>

- [<span data-ttu-id="f7d2a-172">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="f7d2a-172">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)

