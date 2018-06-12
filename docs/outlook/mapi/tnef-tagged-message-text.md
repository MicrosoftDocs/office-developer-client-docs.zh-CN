---
title: TNEF 标记消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c65339e-240c-412d-9b71-69c746468bfb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bedfc0457b0de8287a4e7bc8bdf8fb57404e4fa8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778985"
---
# <a name="tnef-tagged-message-text"></a><span data-ttu-id="af447-103">TNEF 标记消息文本</span><span class="sxs-lookup"><span data-stu-id="af447-103">TNEF-Tagged Message Text</span></span>

  
  
<span data-ttu-id="af447-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="af447-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="af447-105">已标记的消息文本使用 TNEF 解析父邮件中的附件位置。</span><span class="sxs-lookup"><span data-stu-id="af447-105">Tagged message text is used by TNEF to resolve attachment positions in the parent message.</span></span> <span data-ttu-id="af447-106">这是通过附件的位置的消息文本中添加占位符。</span><span class="sxs-lookup"><span data-stu-id="af447-106">This is done by adding a place holder in the message text at the position of the attachment.</span></span> <span data-ttu-id="af447-107">此占位符或附件标记介绍一种 TNEF 知道如何解决附件和其位置的方法中的附件。</span><span class="sxs-lookup"><span data-stu-id="af447-107">This place holder, or attachment tag, describes the attachment in such a way that TNEF knows how to resolve the attachment and its position.</span></span> <span data-ttu-id="af447-108">标记的格式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="af447-108">The tags are formatted as follows:</span></span>
  
 `[[ <Object Title> : <KeyNum> in <Stream Name> ]] [[ <File Name> : <KeyNum> in <Transport Name> ]]`
  
 <span data-ttu-id="af447-109">**\<对象标题\>** 和**\<文件名\>** 是包含来自本身的附件的值的变量。</span><span class="sxs-lookup"><span data-stu-id="af447-109">**\<Object Title\>** and **\<File Name\>** are variables containing values that are taken from the attachment itself.</span></span> <span data-ttu-id="af447-110">在这些值不可用的情况下，通过 TNEF 附件类型基于默认标题。</span><span class="sxs-lookup"><span data-stu-id="af447-110">In cases where these values are not available, the title is defaulted by TNEF based on the attachment type.</span></span> 
  
<span data-ttu-id="af447-111">** \<KeyNum\>** 变量包含的文本表示形式 TNEF 由分配给附件的附件键。</span><span class="sxs-lookup"><span data-stu-id="af447-111">The **\<KeyNum\>** variable contains the textual representation of the attachment key assigned to the attachment by TNEF.</span></span> <span data-ttu-id="af447-112">基本项的值被传递到[OpenTnefStreamEx](opentnefstreamex.md)呼叫。</span><span class="sxs-lookup"><span data-stu-id="af447-112">The base value of the key is passed into the [OpenTnefStreamEx](opentnefstreamex.md) call.</span></span> <span data-ttu-id="af447-113">基本的值必须不为零，不应**OpenTnefStreamEx**每次调用相同。</span><span class="sxs-lookup"><span data-stu-id="af447-113">The base value must not be zero and should not be the same for every call to **OpenTnefStreamEx**.</span></span> <span data-ttu-id="af447-114">它应该就足够了，使用基于从运行时库提供，任何随机数字生成器系统时间，只要您能保证他们从不零伪随机数。</span><span class="sxs-lookup"><span data-stu-id="af447-114">It should suffice to use pseudo random numbers based on the system time from whatever random number generator your run-time library provides, as long as you guarantee that they are never zero.</span></span>
  
<span data-ttu-id="af447-115">**\<传输名称\>** 变量包含流名称传递到[OpenTnefStreamEx](opentnefstreamex.md)呼叫或**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="af447-115">The **\<Transport Name\>** variable contains either the stream name passed into the [OpenTnefStreamEx](opentnefstreamex.md) call or the value of the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af447-116">**PR_ATTACH_TRANSPORT_NAME**属性和**\<传输名称\>** 变量消息文本标记中的没有要进行处理要实现传输提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="af447-116">The **PR_ATTACH_TRANSPORT_NAME** property and the **\<Transport Name\>** variable in a message text tag have nothing to do with the name of the transport provider you are implementing.</span></span> <span data-ttu-id="af447-117">这些项表示传输提供程序和邮件系统的附件的名称。</span><span class="sxs-lookup"><span data-stu-id="af447-117">These items represent the name of an attachment for the transport provider and messaging system.</span></span> 
  
<span data-ttu-id="af447-118">传输提供程序通过调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法要求已标记的消息文本时标记消息文本。</span><span class="sxs-lookup"><span data-stu-id="af447-118">The message text is tagged when a transport provider asks for a tagged message text by calling the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method.</span></span> <span data-ttu-id="af447-119">从已标记的文本流读取时, TNEF 替换为已具有适当的标记提供**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性中的索引处的消息文本中的单个字符。</span><span class="sxs-lookup"><span data-stu-id="af447-119">When reading from the tagged text stream, TNEF replaces the single character that was in the message text at the index provided in the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property with the appropriate tag.</span></span> <span data-ttu-id="af447-120">写入标记的文本流时, TNEF 检查传入数据标记、 查找关联的附件，并标记替换为单个空格字符。</span><span class="sxs-lookup"><span data-stu-id="af447-120">When writing to the tagged text stream, TNEF checks the incoming data for tags, finds the associated attachment, and replaces the tag with a single space character.</span></span>
  
<span data-ttu-id="af447-121">请注意，通过使用已标记的消息文本，传输提供程序可以保留位置所做的消息文本的消息系统的大多数更改附件。</span><span class="sxs-lookup"><span data-stu-id="af447-121">Note that by using tagged message text, a transport provider can preserve the positioning of attachments regardless of most changes made to the message text by messaging systems.</span></span>
  

