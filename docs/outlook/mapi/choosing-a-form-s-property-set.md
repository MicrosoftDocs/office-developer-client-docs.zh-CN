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
# <a name="choosing-a-forms-property-set"></a><span data-ttu-id="55c29-103">选择表单的属性集</span><span class="sxs-lookup"><span data-stu-id="55c29-103">Choosing a form's property set</span></span>

<span data-ttu-id="55c29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55c29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55c29-105">当您实现表单服务器时，您需要为邮件类需要的每个信息段设置一个 属性。</span><span class="sxs-lookup"><span data-stu-id="55c29-105">When you implement your form server, you need to have a property for each piece of information that your message class needs.</span></span> <span data-ttu-id="55c29-106">这些属性可以是预定义的 MAPI 属性，也可以是定义的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="55c29-106">These properties can be predefined MAPI properties, or they can be custom properties that you define.</span></span> <span data-ttu-id="55c29-107">有关使用属性的信息，请参阅 [MAPI 属性概述](mapi-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="55c29-107">For more information about working with properties, see [MAPI Property Overview](mapi-property-overview.md).</span></span>
  
<span data-ttu-id="55c29-108">表单配置文件将包含表单服务器公开的属性列表，供客户端应用程序使用，但这不是表单服务器使用的属性的整个列表。</span><span class="sxs-lookup"><span data-stu-id="55c29-108">Your form configuration file will contain a list of properties that your form server exposes for client applications to use, but this does not have to be the entire list of properties used by your form server.</span></span> <span data-ttu-id="55c29-109">客户端应用程序通常使用公开的属性来允许用户对文件夹中的邮件进行排序或以某种方式自定义其界面。</span><span class="sxs-lookup"><span data-stu-id="55c29-109">Client applications typically use the exposed properties to enable users to sort messages in a folder or customize their interfaces in some way.</span></span>
  
<span data-ttu-id="55c29-110">MAPI 具有一大组预定义属性，这对于大多数应用程序都足够。</span><span class="sxs-lookup"><span data-stu-id="55c29-110">MAPI has a large set of predefined properties that suffice for most applications.</span></span> <span data-ttu-id="55c29-111">但是，有时自定义邮件类需要 MAPI 未定义的属性。</span><span class="sxs-lookup"><span data-stu-id="55c29-111">However, there will be times when a custom message class needs a property that MAPI does not define.</span></span> <span data-ttu-id="55c29-112">您可以使用自定义属性来扩展窗体服务器需要支持的任何特殊信息的 MAPI 预定义属性集。</span><span class="sxs-lookup"><span data-stu-id="55c29-112">You can use custom properties to extend the MAPI predefined set of properties for whatever special information your form server needs to support.</span></span>
  
<span data-ttu-id="55c29-113">可以使用以下任一方法来定义自定义属性：</span><span class="sxs-lookup"><span data-stu-id="55c29-113">You can use either of the following ways to define custom properties:</span></span>
  
- <span data-ttu-id="55c29-114">选择属性的名称，并使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法获取该属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="55c29-114">Choose a name for the property and use the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method to obtain a property tag for it.</span></span> <span data-ttu-id="55c29-115">通过 [调用此方法的 IMAPIProp](imapipropiunknown.md) 接口来自创建消息时传递给表单服务器的 [IMessage](imessageimapiprop.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="55c29-115">The [IMAPIProp](imapipropiunknown.md) interface through which you call this method comes from the [IMessage](imessageimapiprop.md) pointer that is passed to the form server when the message is created.</span></span> <span data-ttu-id="55c29-116">请注意，属性名称必须是宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="55c29-116">Note that the property name must be a wide-character string.</span></span> 
    
- <span data-ttu-id="55c29-117">自己定义自定义属性标记。</span><span class="sxs-lookup"><span data-stu-id="55c29-117">Define a custom property tag yourself.</span></span> <span data-ttu-id="55c29-118">自定义属性标记的范围必须0x6800到0x7BFF。</span><span class="sxs-lookup"><span data-stu-id="55c29-118">Custom property tags must be in the range 0x6800 through 0x7BFF.</span></span> <span data-ttu-id="55c29-119">此范围中的属性特定于邮件类。</span><span class="sxs-lookup"><span data-stu-id="55c29-119">Properties in this range are message-class specific.</span></span>
    
<span data-ttu-id="55c29-120">有关定义自定义属性的信息，请参阅 [定义新的 MAPI 属性](defining-new-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="55c29-120">For more information about defining custom properties, see [Defining New MAPI Properties](defining-new-mapi-properties.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="55c29-121">具有邮件文本的表单服务器通常使用 PR_RTF_COMPRESSED  ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性来存储它。</span><span class="sxs-lookup"><span data-stu-id="55c29-121">Form servers that have a message text often use the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property to store it.</span></span> <span data-ttu-id="55c29-122">如果您的表单服务器使用 **PR_RTF_COMPRESSED**，它还应确保 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性包含仅文本版本的邮件文本，以防生成的邮件由不支持 RTF (RTF) 格式邮件文本的客户端读取。</span><span class="sxs-lookup"><span data-stu-id="55c29-122">If your form server uses **PR_RTF_COMPRESSED**, it should also ensure that the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property contains a text-only version of the message text, in case the resulting message is read by a client that does not support Rich Text Format (RTF) message text.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="55c29-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55c29-123">See also</span></span>

- [<span data-ttu-id="55c29-124">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="55c29-124">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

