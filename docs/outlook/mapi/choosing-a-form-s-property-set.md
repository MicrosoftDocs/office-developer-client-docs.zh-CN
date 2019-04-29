---
title: 选择表单的属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5680fed2-b2e7-4c4b-9ba8-2c497b9c433c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d983b71c7c92c395740a8ae6f6d3666a8bc2c0c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407191"
---
# <a name="choosing-a-forms-property-set"></a><span data-ttu-id="5f898-103">选择表单的属性集</span><span class="sxs-lookup"><span data-stu-id="5f898-103">Choosing a form's property set</span></span>

<span data-ttu-id="5f898-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f898-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f898-105">在实现窗体服务器时, 需要为您的邮件类需要的每条信息提供一个属性。</span><span class="sxs-lookup"><span data-stu-id="5f898-105">When you implement your form server, you need to have a property for each piece of information that your message class needs.</span></span> <span data-ttu-id="5f898-106">这些属性可以是预定义的 MAPI 属性, 也可以是您定义的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="5f898-106">These properties can be predefined MAPI properties, or they can be custom properties that you define.</span></span> <span data-ttu-id="5f898-107">有关使用属性的详细信息, 请参阅[MAPI 属性概述](mapi-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5f898-107">For more information about working with properties, see [MAPI Property Overview](mapi-property-overview.md).</span></span>
  
<span data-ttu-id="5f898-108">表单配置文件将包含表单服务器为要使用的客户端应用程序公开的属性列表, 但这并不一定是表单服务器所使用的全部属性列表。</span><span class="sxs-lookup"><span data-stu-id="5f898-108">Your form configuration file will contain a list of properties that your form server exposes for client applications to use, but this does not have to be the entire list of properties used by your form server.</span></span> <span data-ttu-id="5f898-109">客户端应用程序通常使用公开的属性, 使用户能够对文件夹中的邮件进行排序或以某种方式自定义其界面。</span><span class="sxs-lookup"><span data-stu-id="5f898-109">Client applications typically use the exposed properties to enable users to sort messages in a folder or customize their interfaces in some way.</span></span>
  
<span data-ttu-id="5f898-110">MAPI 具有大量预定义的属性, 足以满足大多数应用程序的要求。</span><span class="sxs-lookup"><span data-stu-id="5f898-110">MAPI has a large set of predefined properties that suffice for most applications.</span></span> <span data-ttu-id="5f898-111">但是, 有时会发生自定义邮件类需要 MAPI 未定义的属性。</span><span class="sxs-lookup"><span data-stu-id="5f898-111">However, there will be times when a custom message class needs a property that MAPI does not define.</span></span> <span data-ttu-id="5f898-112">您可以使用自定义属性来扩展 MAPI 的预定义属性集, 以确定您的表单服务器需要支持的任何特殊信息。</span><span class="sxs-lookup"><span data-stu-id="5f898-112">You can use custom properties to extend the MAPI predefined set of properties for whatever special information your form server needs to support.</span></span>
  
<span data-ttu-id="5f898-113">您可以使用下列任一方法来定义自定义属性:</span><span class="sxs-lookup"><span data-stu-id="5f898-113">You can use either of the following ways to define custom properties:</span></span>
  
- <span data-ttu-id="5f898-114">选择属性的名称, 并使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法获取它的属性标记。</span><span class="sxs-lookup"><span data-stu-id="5f898-114">Choose a name for the property and use the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method to obtain a property tag for it.</span></span> <span data-ttu-id="5f898-115">调用此方法时使用的[IMAPIProp](imapipropiunknown.md)接口来自在创建邮件时传递给表单服务器的[IMessage](imessageimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="5f898-115">The [IMAPIProp](imapipropiunknown.md) interface through which you call this method comes from the [IMessage](imessageimapiprop.md) pointer that is passed to the form server when the message is created.</span></span> <span data-ttu-id="5f898-116">请注意, 属性名称必须是宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="5f898-116">Note that the property name must be a wide-character string.</span></span> 
    
- <span data-ttu-id="5f898-117">自己定义自定义属性标记。</span><span class="sxs-lookup"><span data-stu-id="5f898-117">Define a custom property tag yourself.</span></span> <span data-ttu-id="5f898-118">自定义属性标记必须在0x6800 到0x7BFF 的范围内。</span><span class="sxs-lookup"><span data-stu-id="5f898-118">Custom property tags must be in the range 0x6800 through 0x7BFF.</span></span> <span data-ttu-id="5f898-119">此范围中的属性是特定于邮件类别的。</span><span class="sxs-lookup"><span data-stu-id="5f898-119">Properties in this range are message-class specific.</span></span>
    
<span data-ttu-id="5f898-120">有关定义自定义属性的详细信息, 请参阅[定义新的 MAPI 属性](defining-new-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5f898-120">For more information about defining custom properties, see [Defining New MAPI Properties](defining-new-mapi-properties.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f898-121">包含邮件文本的表单服务器通常使用**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性来存储它。</span><span class="sxs-lookup"><span data-stu-id="5f898-121">Form servers that have a message text often use the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property to store it.</span></span> <span data-ttu-id="5f898-122">如果您的表单服务器使用**PR_RTF_COMPRESSED**, 则还应确保**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性包含邮件文本的纯文本版本, 以便不支持 rtf 的客户端读取生成的邮件格式 (RTF) 消息文本。</span><span class="sxs-lookup"><span data-stu-id="5f898-122">If your form server uses **PR_RTF_COMPRESSED**, it should also ensure that the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property contains a text-only version of the message text, in case the resulting message is read by a client that does not support Rich Text Format (RTF) message text.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5f898-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f898-123">See also</span></span>

- [<span data-ttu-id="5f898-124">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="5f898-124">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

