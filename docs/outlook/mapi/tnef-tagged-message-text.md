---
title: TNEF 标记的邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c65339e-240c-412d-9b71-69c746468bfb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2b4d4cd790870a024cac6f2ed9952d18a970235a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339590"
---
# <a name="tnef-tagged-message-text"></a><span data-ttu-id="96c95-103">TNEF 标记的邮件文本</span><span class="sxs-lookup"><span data-stu-id="96c95-103">TNEF-Tagged Message Text</span></span>

  
  
<span data-ttu-id="96c95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96c95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96c95-105">TNEF 使用标记的邮件文本来解析父邮件中的附件位置。</span><span class="sxs-lookup"><span data-stu-id="96c95-105">Tagged message text is used by TNEF to resolve attachment positions in the parent message.</span></span> <span data-ttu-id="96c95-106">这是通过在邮件文本中的附件位置添加占位符来实现的。</span><span class="sxs-lookup"><span data-stu-id="96c95-106">This is done by adding a place holder in the message text at the position of the attachment.</span></span> <span data-ttu-id="96c95-107">此 "放置位置" 或 "附件" 标记描述附件的方式是, TNEF 知道如何解析附件及其位置。</span><span class="sxs-lookup"><span data-stu-id="96c95-107">This place holder, or attachment tag, describes the attachment in such a way that TNEF knows how to resolve the attachment and its position.</span></span> <span data-ttu-id="96c95-108">这些标记的格式如下所示:</span><span class="sxs-lookup"><span data-stu-id="96c95-108">The tags are formatted as follows:</span></span>
  
 `[[ <Object Title> : <KeyNum> in <Stream Name> ]] [[ <File Name> : <KeyNum> in <Transport Name> ]]`
  
 <span data-ttu-id="96c95-109">\*\* \<对象标题\> \*\* \*\*和\<文件名是包含从附件本身\> \*\*获取的值的变量。</span><span class="sxs-lookup"><span data-stu-id="96c95-109">**\<Object Title\>** and **\<File Name\>** are variables containing values that are taken from the attachment itself.</span></span> <span data-ttu-id="96c95-110">在这些值不可用的情况下, 标题将根据附件类型默认使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="96c95-110">In cases where these values are not available, the title is defaulted by TNEF based on the attachment type.</span></span> 
  
<span data-ttu-id="96c95-111">KeyNum 变量包含通过 TNEF 分配给附件的附件密钥的文本表示形式。 \*\* \<\> \*\*</span><span class="sxs-lookup"><span data-stu-id="96c95-111">The **\<KeyNum\>** variable contains the textual representation of the attachment key assigned to the attachment by TNEF.</span></span> <span data-ttu-id="96c95-112">键的基值将传递到[OpenTnefStreamEx](opentnefstreamex.md)调用中。</span><span class="sxs-lookup"><span data-stu-id="96c95-112">The base value of the key is passed into the [OpenTnefStreamEx](opentnefstreamex.md) call.</span></span> <span data-ttu-id="96c95-113">基值不得为零, 并且对于每个**OpenTnefStreamEx**调用都不应相同。</span><span class="sxs-lookup"><span data-stu-id="96c95-113">The base value must not be zero and should not be the same for every call to **OpenTnefStreamEx**.</span></span> <span data-ttu-id="96c95-114">只要您保证它们从不为零, 就可以根据系统时间从运行时库提供的任何随机编号生成器使用伪随机数字。</span><span class="sxs-lookup"><span data-stu-id="96c95-114">It should suffice to use pseudo random numbers based on the system time from whatever random number generator your run-time library provides, as long as you guarantee that they are never zero.</span></span>
  
<span data-ttu-id="96c95-115">[](opentnefstreamex.md) **\>传输名称变量包含传递到 OpenTnefStreamEx 调用中的流名称或 PR_ATTACH_TRANSPORT_NAME (PidTagAttachTransportName) 属性的\<** 值。[](pidtagattachtransportname-canonical-property.md) \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="96c95-115">The **\<Transport Name\>** variable contains either the stream name passed into the [OpenTnefStreamEx](opentnefstreamex.md) call or the value of the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96c95-116">message 文本标记中的**PR_ATTACH_TRANSPORT_NAME**属性和\*\* \<transport NAME\> \*\*变量与您要实现的传输提供程序的名称无任何不同之处。</span><span class="sxs-lookup"><span data-stu-id="96c95-116">The **PR_ATTACH_TRANSPORT_NAME** property and the **\<Transport Name\>** variable in a message text tag have nothing to do with the name of the transport provider you are implementing.</span></span> <span data-ttu-id="96c95-117">这些项表示传输提供程序和邮件系统的附件的名称。</span><span class="sxs-lookup"><span data-stu-id="96c95-117">These items represent the name of an attachment for the transport provider and messaging system.</span></span> 
  
<span data-ttu-id="96c95-118">当传输提供程序通过调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法来请求标记的邮件文本时, 将标记邮件文本。</span><span class="sxs-lookup"><span data-stu-id="96c95-118">The message text is tagged when a transport provider asks for a tagged message text by calling the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method.</span></span> <span data-ttu-id="96c95-119">从标记文本流读取时, TNEF 将**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性中提供的索引处的邮件文本中的单个字符替换为相应的标记。</span><span class="sxs-lookup"><span data-stu-id="96c95-119">When reading from the tagged text stream, TNEF replaces the single character that was in the message text at the index provided in the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property with the appropriate tag.</span></span> <span data-ttu-id="96c95-120">在向标记文本流中写入时, TNEF 会检查标记的传入数据, 查找关联的附件, 并将标记替换为单个空格字符。</span><span class="sxs-lookup"><span data-stu-id="96c95-120">When writing to the tagged text stream, TNEF checks the incoming data for tags, finds the associated attachment, and replaces the tag with a single space character.</span></span>
  
<span data-ttu-id="96c95-121">请注意, 通过使用带标记的邮件文本, 传输提供程序可以保留附件的位置, 而不考虑邮件系统对邮件文本所做的大多数更改。</span><span class="sxs-lookup"><span data-stu-id="96c95-121">Note that by using tagged message text, a transport provider can preserve the positioning of attachments regardless of most changes made to the message text by messaging systems.</span></span>
  

