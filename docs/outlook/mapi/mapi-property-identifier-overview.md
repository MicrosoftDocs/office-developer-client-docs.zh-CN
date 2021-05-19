---
title: MAPI 属性标识符概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 957aa00f-23d8-4f3b-bbc2-7d54f17b47b5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 29626f49365a0f37f1e13d965c62bfd5ad0fb774
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414695"
---
# <a name="mapi-property-identifier-overview"></a><span data-ttu-id="b40b9-103">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="b40b9-103">MAPI Property Identifier Overview</span></span>

  
  
<span data-ttu-id="b40b9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b40b9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b40b9-105">属性标识符是一个数字，用于指示属性用于什么以及由谁负责。</span><span class="sxs-lookup"><span data-stu-id="b40b9-105">A property identifier is a number that is used to indicate what a property is used for and who is responsible for it.</span></span> <span data-ttu-id="b40b9-106">属性标识符按 MAPI 划分到范围中;其中标识符属于范围，指示其使用和所有权。</span><span class="sxs-lookup"><span data-stu-id="b40b9-106">Property identifiers are divided by MAPI into ranges; where an identifier falls in the range indicates its use and ownership.</span></span> 
  
<span data-ttu-id="b40b9-107">属性标识符的范围从 0x0001 到 0xFFFF。</span><span class="sxs-lookup"><span data-stu-id="b40b9-107">The range of property identifiers runs from 0x0001 through 0xFFFF.</span></span> <span data-ttu-id="b40b9-108">所有情况下0x0000和0xFFFF保留属性标识符，这意味着这些标识符必须保持未使用状态。</span><span class="sxs-lookup"><span data-stu-id="b40b9-108">Property identifiers 0x0000 and 0xFFFF are reserved in all cases, meaning that these identifiers must remain unused.</span></span> <span data-ttu-id="b40b9-109">MAPI 定义的属性范围从 0x0001 到 0x3FFF。</span><span class="sxs-lookup"><span data-stu-id="b40b9-109">The range for properties defined by MAPI runs from 0x0001 to 0x3FFF.</span></span> <span data-ttu-id="b40b9-110">这些属性称为 MAPI 定义的属性。</span><span class="sxs-lookup"><span data-stu-id="b40b9-110">These properties are referred to as MAPI-defined properties.</span></span> <span data-ttu-id="b40b9-111">要0x4000 0x7FFF属于邮件和收件人属性，客户端或服务提供商都可以定义此范围中的属性。</span><span class="sxs-lookup"><span data-stu-id="b40b9-111">The range 0x4000 to 0x7FFF belongs to message and recipient properties, and either clients or service providers can define properties in this range.</span></span> <span data-ttu-id="b40b9-112">要访问0x0001 0x7FFF属性称为标记属性。</span><span class="sxs-lookup"><span data-stu-id="b40b9-112">Properties in the range of 0x0001 to 0x7FFF are referred to as tagged properties.</span></span> <span data-ttu-id="b40b9-113">除了 0x8000 是所谓的命名属性的范围，或者是包括 32 位全局唯一标识符 (GUID) 以及 Unicode 字符串或数值的属性。</span><span class="sxs-lookup"><span data-stu-id="b40b9-113">Beyond 0x8000 is the range for what is known as named properties, or properties that include a 32-bit globally unique identifier (GUID) and either a Unicode character string or numeric value.</span></span> <span data-ttu-id="b40b9-114">客户端可以使用命名属性自定义其属性集。</span><span class="sxs-lookup"><span data-stu-id="b40b9-114">Clients can use named properties to customize their property set.</span></span>
  
<span data-ttu-id="b40b9-115">服务提供商可以在范围中定义安全配置文件属性，0x67F0到0x67FF。</span><span class="sxs-lookup"><span data-stu-id="b40b9-115">Service providers can define secure profile properties in the range 0x67F0 through 0x67FF.</span></span> <span data-ttu-id="b40b9-116">安全配置文件属性用于需要额外保护的信息，如密码。</span><span class="sxs-lookup"><span data-stu-id="b40b9-116">Secure profile properties are used for information that requires additional protection, such as passwords.</span></span> <span data-ttu-id="b40b9-117">这些属性可以隐藏和加密。</span><span class="sxs-lookup"><span data-stu-id="b40b9-117">These properties can be hidden and encrypted.</span></span> <span data-ttu-id="b40b9-118">[IMAPIProp：：GetPropList](imapiprop-getproplist.md)方法返回的属性的默认列表中是否包含安全属性取决于提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="b40b9-118">Whether or not secure properties are included in the default list of properties returned by the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method depends on the provider's implementation.</span></span> <span data-ttu-id="b40b9-119">通常不包括这些属性。</span><span class="sxs-lookup"><span data-stu-id="b40b9-119">Usually these properties are not included.</span></span> <span data-ttu-id="b40b9-120">[IProfSect ： IMAPIProp](iprofsectimapiprop.md)接口用于访问配置文件节的属性，包括安全属性。</span><span class="sxs-lookup"><span data-stu-id="b40b9-120">The [IProfSect : IMAPIProp](iprofsectimapiprop.md) interface is used for accessing the properties of a profile section, including secure properties.</span></span> 
  
<span data-ttu-id="b40b9-121">某些属性范围仅限于可传输属性或非可传输属性。</span><span class="sxs-lookup"><span data-stu-id="b40b9-121">Some of the property ranges are restricted to transmittable properties or nontransmittable properties.</span></span> <span data-ttu-id="b40b9-122">可传输属性随邮件一起传输;不可传输的属性不会随邮件一起传输。</span><span class="sxs-lookup"><span data-stu-id="b40b9-122">Transmittable properties are transferred with a message; nontransmittable properties are not transferred with a message.</span></span> <span data-ttu-id="b40b9-123">不可传输的属性通常包含仅对使用当前会话的客户端和服务提供商有价值的信息。</span><span class="sxs-lookup"><span data-stu-id="b40b9-123">Nontransmittable properties usually contain information that is of value only to clients and service providers operating with the current session.</span></span> <span data-ttu-id="b40b9-124">这些属性不一定对另一个邮件系统和另一组服务提供商有用。</span><span class="sxs-lookup"><span data-stu-id="b40b9-124">These properties would not necessarily be useful to another messaging system and another set of service providers.</span></span> <span data-ttu-id="b40b9-125">可传输属性的概念主要适用于传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b40b9-125">The concept of transmittable properties applies primarily to transport providers.</span></span> <span data-ttu-id="b40b9-126">若要确定属性是否可传输，请传递其属性标记到 **FIsTransmittable** 宏，该宏在 Mapitags.h 头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="b40b9-126">To determine whether a property is transmittable or not, pass its property tag to the **FIsTransmittable** macro, defined in the Mapitags.h header file.</span></span> 
  
<span data-ttu-id="b40b9-127">有关标识符范围的完整说明，请参阅 [属性标识符范围](property-identifier-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="b40b9-127">For a complete description of the identifier ranges, see [Property Identifier Ranges](property-identifier-ranges.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b40b9-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b40b9-128">See also</span></span>



[<span data-ttu-id="b40b9-129">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="b40b9-129">MAPI Property Overview</span></span>](mapi-property-overview.md)

