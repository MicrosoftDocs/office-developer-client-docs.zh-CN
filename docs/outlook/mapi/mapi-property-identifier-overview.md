---
title: MAPI 属性标识符概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 957aa00f-23d8-4f3b-bbc2-7d54f17b47b5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 725256a64cb7d55be494ba623247255dfe5936c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776290"
---
# <a name="mapi-property-identifier-overview"></a><span data-ttu-id="07674-103">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="07674-103">MAPI Property Identifier Overview</span></span>

  
  
<span data-ttu-id="07674-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="07674-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="07674-105">属性标识符是一个数字，用于指示属性用于和谁负责执行它。</span><span class="sxs-lookup"><span data-stu-id="07674-105">A property identifier is a number that is used to indicate what a property is used for and who is responsible for it.</span></span> <span data-ttu-id="07674-106">属性标识符可以分为若干通过 MAPI 范围;标识符属于范围中的其中指示其使用情况和所有权。</span><span class="sxs-lookup"><span data-stu-id="07674-106">Property identifiers are divided by MAPI into ranges; where an identifier falls in the range indicates its use and ownership.</span></span> 
  
<span data-ttu-id="07674-107">属性标识符的范围从 0x0001 经过 0xFFFF。</span><span class="sxs-lookup"><span data-stu-id="07674-107">The range of property identifiers runs from 0x0001 through 0xFFFF.</span></span> <span data-ttu-id="07674-108">在所有情况下，这意味着，这些标识符必须保持未使用保留 0x0000 和 0xFFFF 属性标识符。</span><span class="sxs-lookup"><span data-stu-id="07674-108">Property identifiers 0x0000 and 0xFFFF are reserved in all cases, meaning that these identifiers must remain unused.</span></span> <span data-ttu-id="07674-109">定义的 MAPI 属性的范围从 0x0001 运行，以 0x3FFF。</span><span class="sxs-lookup"><span data-stu-id="07674-109">The range for properties defined by MAPI runs from 0x0001 to 0x3FFF.</span></span> <span data-ttu-id="07674-110">这些属性被称为自定义 MAPI 的属性。</span><span class="sxs-lookup"><span data-stu-id="07674-110">These properties are referred to as MAPI-defined properties.</span></span> <span data-ttu-id="07674-111">范围 0x4000 到 0x7FFF 所属消息和收件人属性，并且客户端或服务提供商可以在此范围中定义属性。</span><span class="sxs-lookup"><span data-stu-id="07674-111">The range 0x4000 to 0x7FFF belongs to message and recipient properties, and either clients or service providers can define properties in this range.</span></span> <span data-ttu-id="07674-112">0x0001 到 0x7FFF 范围中的属性称为带标记的属性。</span><span class="sxs-lookup"><span data-stu-id="07674-112">Properties in the range of 0x0001 to 0x7FFF are referred to as tagged properties.</span></span> <span data-ttu-id="07674-113">超出 0x8000 是被称为命名的属性或包含 32 位的全局唯一标识符 (GUID) 和 Unicode 字符串或数值的属性的范围。</span><span class="sxs-lookup"><span data-stu-id="07674-113">Beyond 0x8000 is the range for what is known as named properties, or properties that include a 32-bit globally unique identifier (GUID) and either a Unicode character string or numeric value.</span></span> <span data-ttu-id="07674-114">客户端可以使用命名的属性自定义其属性集。</span><span class="sxs-lookup"><span data-stu-id="07674-114">Clients can use named properties to customize their property set.</span></span>
  
<span data-ttu-id="07674-115">服务提供商可以定义范围通过 0x67FF 0x67F0 中的安全配置文件属性。</span><span class="sxs-lookup"><span data-stu-id="07674-115">Service providers can define secure profile properties in the range 0x67F0 through 0x67FF.</span></span> <span data-ttu-id="07674-116">安全配置文件属性用于需要额外的保护，如密码的信息。</span><span class="sxs-lookup"><span data-stu-id="07674-116">Secure profile properties are used for information that requires additional protection, such as passwords.</span></span> <span data-ttu-id="07674-117">这些属性可以隐藏和加密。</span><span class="sxs-lookup"><span data-stu-id="07674-117">These properties can be hidden and encrypted.</span></span> <span data-ttu-id="07674-118">由[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的属性的默认列表中包含安全属性取决于提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="07674-118">Whether or not secure properties are included in the default list of properties returned by the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method depends on the provider's implementation.</span></span> <span data-ttu-id="07674-119">通常不包括这些属性。</span><span class="sxs-lookup"><span data-stu-id="07674-119">Usually these properties are not included.</span></span> <span data-ttu-id="07674-120">[IProfSect: IMAPIProp](iprofsectimapiprop.md)接口用于访问配置文件部分，包括安全属性的属性。</span><span class="sxs-lookup"><span data-stu-id="07674-120">The [IProfSect : IMAPIProp](iprofsectimapiprop.md) interface is used for accessing the properties of a profile section, including secure properties.</span></span> 
  
<span data-ttu-id="07674-121">某些属性区域被限制为可传送属性或 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="07674-121">Some of the property ranges are restricted to transmittable properties or nontransmittable properties.</span></span> <span data-ttu-id="07674-122">一条消息; 会传输可传送属性一条消息，不会传输 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="07674-122">Transmittable properties are transferred with a message; nontransmittable properties are not transferred with a message.</span></span> <span data-ttu-id="07674-123">Nontransmittable 属性通常包含的值仅为客户端和操作系统与当前会话的服务提供商的信息。</span><span class="sxs-lookup"><span data-stu-id="07674-123">Nontransmittable properties usually contain information that is of value only to clients and service providers operating with the current session.</span></span> <span data-ttu-id="07674-124">这些属性不一定是另一个邮件系统和服务提供商的另一组有用。</span><span class="sxs-lookup"><span data-stu-id="07674-124">These properties would not necessarily be useful to another messaging system and another set of service providers.</span></span> <span data-ttu-id="07674-125">可传送属性的概念主要于传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="07674-125">The concept of transmittable properties applies primarily to transport providers.</span></span> <span data-ttu-id="07674-126">若要确定是否可传送属性，请将其属性标记传递给**FIsTransmittable**宏，Mapitags.h 标头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="07674-126">To determine whether a property is transmittable or not, pass its property tag to the **FIsTransmittable** macro, defined in the Mapitags.h header file.</span></span> 
  
<span data-ttu-id="07674-127">标识符范围的完整说明，请参阅[属性标识符范围](property-identifier-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="07674-127">For a complete description of the identifier ranges, see [Property Identifier Ranges](property-identifier-ranges.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07674-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07674-128">See also</span></span>



[<span data-ttu-id="07674-129">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="07674-129">MAPI Property Overview</span></span>](mapi-property-overview.md)

