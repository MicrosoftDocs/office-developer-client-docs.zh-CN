---
title: 选择窗体的属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5680fed2-b2e7-4c4b-9ba8-2c497b9c433c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 456ef036b26fd8b9840d33f0f699474c3a6ce127
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774665"
---
# <a name="choosing-a-forms-property-set"></a><span data-ttu-id="57738-103">选择窗体的属性集</span><span class="sxs-lookup"><span data-stu-id="57738-103">Choosing a form's property set</span></span>

<span data-ttu-id="57738-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="57738-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="57738-105">实现表单服务器时，您需要具有对每个邮件类所需的信息的属性。</span><span class="sxs-lookup"><span data-stu-id="57738-105">When you implement your form server, you need to have a property for each piece of information that your message class needs.</span></span> <span data-ttu-id="57738-106">这些属性可以是预定义的 MAPI 属性，也可以在您定义的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="57738-106">These properties can be predefined MAPI properties, or they can be custom properties that you define.</span></span> <span data-ttu-id="57738-107">有关使用属性的详细信息，请参阅[MAPI 属性概述](mapi-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="57738-107">For more information about working with properties, see [MAPI Property Overview](mapi-property-overview.md).</span></span>
  
<span data-ttu-id="57738-108">您窗体的配置文件将包含客户端应用程序可以使用，公开您的窗体服务器的属性列表，但这不需要在整个窗体服务器使用的属性列表。</span><span class="sxs-lookup"><span data-stu-id="57738-108">Your form configuration file will contain a list of properties that your form server exposes for client applications to use, but this does not have to be the entire list of properties used by your form server.</span></span> <span data-ttu-id="57738-109">客户端应用程序通常使用公开的属性使用户能够排序文件夹中的邮件或自定义其接口以某种方式。</span><span class="sxs-lookup"><span data-stu-id="57738-109">Client applications typically use the exposed properties to enable users to sort messages in a folder or customize their interfaces in some way.</span></span>
  
<span data-ttu-id="57738-110">MAPI 都有一大的预定义满足大多数应用程序的属性。</span><span class="sxs-lookup"><span data-stu-id="57738-110">MAPI has a large set of predefined properties that suffice for most applications.</span></span> <span data-ttu-id="57738-111">但是，将自定义邮件类别时需要 MAPI 未定义的属性的时间。</span><span class="sxs-lookup"><span data-stu-id="57738-111">However, there will be times when a custom message class needs a property that MAPI does not define.</span></span> <span data-ttu-id="57738-112">您可以使用自定义属性扩展 MAPI 预定义的一组属性的窗体服务器需要支持的任何特殊信息。</span><span class="sxs-lookup"><span data-stu-id="57738-112">You can use custom properties to extend the MAPI predefined set of properties for whatever special information your form server needs to support.</span></span>
  
<span data-ttu-id="57738-113">您可以使用以下方法来定义自定义属性之一：</span><span class="sxs-lookup"><span data-stu-id="57738-113">You can use either of the following ways to define custom properties:</span></span>
  
- <span data-ttu-id="57738-114">为属性选择一个名称并使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法为其获取属性标记。</span><span class="sxs-lookup"><span data-stu-id="57738-114">Choose a name for the property and use the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method to obtain a property tag for it.</span></span> <span data-ttu-id="57738-115">通过其调用此方法的[IMAPIProp](imapipropiunknown.md)接口来自时创建邮件传递到窗体服务器[IMessage](imessageimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="57738-115">The [IMAPIProp](imapipropiunknown.md) interface through which you call this method comes from the [IMessage](imessageimapiprop.md) pointer that is passed to the form server when the message is created.</span></span> <span data-ttu-id="57738-116">请注意，在属性名称必须范围个字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="57738-116">Note that the property name must be a wide-character string.</span></span> 
    
- <span data-ttu-id="57738-117">定义您自己的自定义属性标记。</span><span class="sxs-lookup"><span data-stu-id="57738-117">Define a custom property tag yourself.</span></span> <span data-ttu-id="57738-118">自定义属性标记必须在范围内通过 0x7BFF 0x6800。</span><span class="sxs-lookup"><span data-stu-id="57738-118">Custom property tags must be in the range 0x6800 through 0x7BFF.</span></span> <span data-ttu-id="57738-119">此范围中的属性是邮件类特定。</span><span class="sxs-lookup"><span data-stu-id="57738-119">Properties in this range are message-class specific.</span></span>
    
<span data-ttu-id="57738-120">有关定义自定义属性的详细信息，请参阅[定义新的 MAPI 属性](defining-new-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="57738-120">For more information about defining custom properties, see [Defining New MAPI Properties](defining-new-mapi-properties.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="57738-121">通常具有消息文本的窗体服务器使用**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性以将其存储。</span><span class="sxs-lookup"><span data-stu-id="57738-121">Form servers that have a message text often use the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property to store it.</span></span> <span data-ttu-id="57738-122">如果窗体服务器使用**PR_RTF_COMPRESSED**，它还应**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性包含纯文本邮件正文，版客户端不支持格式文本读取生成消息的情况下消息文本设置格式 (RTF)。</span><span class="sxs-lookup"><span data-stu-id="57738-122">If your form server uses **PR_RTF_COMPRESSED**, it should also ensure that the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property contains a text-only version of the message text, in case the resulting message is read by a client that does not support Rich Text Format (RTF) message text.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="57738-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57738-123">See also</span></span>

- [<span data-ttu-id="57738-124">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="57738-124">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

