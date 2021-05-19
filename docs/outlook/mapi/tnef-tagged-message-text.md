---
title: TNEF-Tagged消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c65339e-240c-412d-9b71-69c746468bfb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2b4d4cd790870a024cac6f2ed9952d18a970235a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419917"
---
# <a name="tnef-tagged-message-text"></a><span data-ttu-id="6dfdd-103">TNEF-Tagged消息文本</span><span class="sxs-lookup"><span data-stu-id="6dfdd-103">TNEF-Tagged Message Text</span></span>

  
  
<span data-ttu-id="6dfdd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6dfdd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6dfdd-105">TNEF 使用带标记的邮件文本解析父邮件中的附件位置。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-105">Tagged message text is used by TNEF to resolve attachment positions in the parent message.</span></span> <span data-ttu-id="6dfdd-106">为此，在附件位置的邮件文本中添加位置持有者。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-106">This is done by adding a place holder in the message text at the position of the attachment.</span></span> <span data-ttu-id="6dfdd-107">此位置持有者（或 attachment 标记）以 TNEF 知道如何解析附件及其位置的方式描述附件。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-107">This place holder, or attachment tag, describes the attachment in such a way that TNEF knows how to resolve the attachment and its position.</span></span> <span data-ttu-id="6dfdd-108">标记的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="6dfdd-108">The tags are formatted as follows:</span></span>
  
 `[[ <Object Title> : <KeyNum> in <Stream Name> ]] [[ <File Name> : <KeyNum> in <Transport Name> ]]`
  
 <span data-ttu-id="6dfdd-109">**\< 对象标题 \>\*\*\*\*\< 和文件名 \>** 是包含从附件本身获得的值的变量。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-109">**\<Object Title\>** and **\<File Name\>** are variables containing values that are taken from the attachment itself.</span></span> <span data-ttu-id="6dfdd-110">如果这些值不可用，则 TNEF 根据附件类型默认使用标题。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-110">In cases where these values are not available, the title is defaulted by TNEF based on the attachment type.</span></span> 
  
<span data-ttu-id="6dfdd-111">**\< KeyNum \>** 变量包含 TNEF 分配给附件的附件键的文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-111">The **\<KeyNum\>** variable contains the textual representation of the attachment key assigned to the attachment by TNEF.</span></span> <span data-ttu-id="6dfdd-112">键的基值将传递到 [OpenTnefStreamEx](opentnefstreamex.md) 调用中。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-112">The base value of the key is passed into the [OpenTnefStreamEx](opentnefstreamex.md) call.</span></span> <span data-ttu-id="6dfdd-113">基值不能为零，并且对于每次调用 **OpenTnefStreamEx** 时不应相同。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-113">The base value must not be zero and should not be the same for every call to **OpenTnefStreamEx**.</span></span> <span data-ttu-id="6dfdd-114">根据系统时间从运行时库提供的随机数字生成器使用伪随机数字就足够了，只要你保证它们从不为零。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-114">It should suffice to use pseudo random numbers based on the system time from whatever random number generator your run-time library provides, as long as you guarantee that they are never zero.</span></span>
  
<span data-ttu-id="6dfdd-115">Transport **\< Name \>** 变量包含传入 [OpenTnefStreamEx](opentnefstreamex.md)调用的流名称或 **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-115">The **\<Transport Name\>** variable contains either the stream name passed into the [OpenTnefStreamEx](opentnefstreamex.md) call or the value of the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6dfdd-116">the **PR_ATTACH_TRANSPORT_NAME** property and the **\< Transport Name \>** variable in a message text tag have nothing to do with the name of the transport provider you are implementing.</span><span class="sxs-lookup"><span data-stu-id="6dfdd-116">The **PR_ATTACH_TRANSPORT_NAME** property and the **\<Transport Name\>** variable in a message text tag have nothing to do with the name of the transport provider you are implementing.</span></span> <span data-ttu-id="6dfdd-117">这些项目表示传输提供程序和邮件系统的附件的名称。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-117">These items represent the name of an attachment for the transport provider and messaging system.</span></span> 
  
<span data-ttu-id="6dfdd-118">当传输提供程序通过调用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法请求标记的邮件文本时，邮件文本将被标记。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-118">The message text is tagged when a transport provider asks for a tagged message text by calling the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method.</span></span> <span data-ttu-id="6dfdd-119">从带标记的文本流中读取时，TNEF 将 PR_RENDERING_POSITION ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md) **)** 属性中提供索引的消息文本中的单个字符替换为相应的标记。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-119">When reading from the tagged text stream, TNEF replaces the single character that was in the message text at the index provided in the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property with the appropriate tag.</span></span> <span data-ttu-id="6dfdd-120">当写入带标记的文本流时，TNEF 会检查传入的标记数据，查找关联的附件，并用单个空格字符替换标记。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-120">When writing to the tagged text stream, TNEF checks the incoming data for tags, finds the associated attachment, and replaces the tag with a single space character.</span></span>
  
<span data-ttu-id="6dfdd-121">请注意，通过使用带标记的邮件文本，传输提供程序可以保留附件的定位，而不管邮件系统对邮件文本进行了何种更改。</span><span class="sxs-lookup"><span data-stu-id="6dfdd-121">Note that by using tagged message text, a transport provider can preserve the positioning of attachments regardless of most changes made to the message text by messaging systems.</span></span>
  

