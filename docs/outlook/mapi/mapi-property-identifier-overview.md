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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328182"
---
# <a name="mapi-property-identifier-overview"></a><span data-ttu-id="b2351-103">MAPI 属性标识符概述</span><span class="sxs-lookup"><span data-stu-id="b2351-103">MAPI Property Identifier Overview</span></span>

  
  
<span data-ttu-id="b2351-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b2351-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b2351-105">属性标识符是一个数字, 用于指示属性的用途和负责的所有者。</span><span class="sxs-lookup"><span data-stu-id="b2351-105">A property identifier is a number that is used to indicate what a property is used for and who is responsible for it.</span></span> <span data-ttu-id="b2351-106">将属性标识符除以 MAPI 到区域中;其中, 标识符位于范围内表示其使用和所有权。</span><span class="sxs-lookup"><span data-stu-id="b2351-106">Property identifiers are divided by MAPI into ranges; where an identifier falls in the range indicates its use and ownership.</span></span> 
  
<span data-ttu-id="b2351-107">属性标识符的范围从0x0001 到0xffff 运行。</span><span class="sxs-lookup"><span data-stu-id="b2351-107">The range of property identifiers runs from 0x0001 through 0xFFFF.</span></span> <span data-ttu-id="b2351-108">在所有情况下都会保留属性标识符0x0000 和 0xffff, 这意味着这些标识符必须保持未使用。</span><span class="sxs-lookup"><span data-stu-id="b2351-108">Property identifiers 0x0000 and 0xFFFF are reserved in all cases, meaning that these identifiers must remain unused.</span></span> <span data-ttu-id="b2351-109">MAPI 定义的属性的范围从0x0001 运行到0x3FFF。</span><span class="sxs-lookup"><span data-stu-id="b2351-109">The range for properties defined by MAPI runs from 0x0001 to 0x3FFF.</span></span> <span data-ttu-id="b2351-110">这些属性称为 MAPI 定义的属性。</span><span class="sxs-lookup"><span data-stu-id="b2351-110">These properties are referred to as MAPI-defined properties.</span></span> <span data-ttu-id="b2351-111">0x4000 到0x7FFF 的范围属于邮件和收件人属性, 客户端或服务提供程序可以在此范围内定义属性。</span><span class="sxs-lookup"><span data-stu-id="b2351-111">The range 0x4000 to 0x7FFF belongs to message and recipient properties, and either clients or service providers can define properties in this range.</span></span> <span data-ttu-id="b2351-112">0x0001 到0x7FFF 的范围中的属性称为 "标记属性"。</span><span class="sxs-lookup"><span data-stu-id="b2351-112">Properties in the range of 0x0001 to 0x7FFF are referred to as tagged properties.</span></span> <span data-ttu-id="b2351-113">大于0x8000 是指称为命名属性的范围, 或者是包含32位全局唯一标识符 (GUID) 的属性, 也可以是 Unicode 字符字符串或数值。</span><span class="sxs-lookup"><span data-stu-id="b2351-113">Beyond 0x8000 is the range for what is known as named properties, or properties that include a 32-bit globally unique identifier (GUID) and either a Unicode character string or numeric value.</span></span> <span data-ttu-id="b2351-114">客户端可以使用命名属性来自定义其属性集。</span><span class="sxs-lookup"><span data-stu-id="b2351-114">Clients can use named properties to customize their property set.</span></span>
  
<span data-ttu-id="b2351-115">服务提供程序可以在0x67F0 到0x67FF 的范围内定义安全配置文件属性。</span><span class="sxs-lookup"><span data-stu-id="b2351-115">Service providers can define secure profile properties in the range 0x67F0 through 0x67FF.</span></span> <span data-ttu-id="b2351-116">安全配置文件属性用于需要其他保护的信息, 如密码。</span><span class="sxs-lookup"><span data-stu-id="b2351-116">Secure profile properties are used for information that requires additional protection, such as passwords.</span></span> <span data-ttu-id="b2351-117">可以对这些属性进行隐藏和加密。</span><span class="sxs-lookup"><span data-stu-id="b2351-117">These properties can be hidden and encrypted.</span></span> <span data-ttu-id="b2351-118">[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法返回的默认属性列表中是否包含安全属性？: 方法取决于提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="b2351-118">Whether or not secure properties are included in the default list of properties returned by the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method depends on the provider's implementation.</span></span> <span data-ttu-id="b2351-119">通常情况下, 这些属性不包括在内。</span><span class="sxs-lookup"><span data-stu-id="b2351-119">Usually these properties are not included.</span></span> <span data-ttu-id="b2351-120">[IProfSect: IMAPIProp](iprofsectimapiprop.md)接口用于访问配置文件部分的属性, 包括安全属性。</span><span class="sxs-lookup"><span data-stu-id="b2351-120">The [IProfSect : IMAPIProp](iprofsectimapiprop.md) interface is used for accessing the properties of a profile section, including secure properties.</span></span> 
  
<span data-ttu-id="b2351-121">某些属性范围限制为传输属性或 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="b2351-121">Some of the property ranges are restricted to transmittable properties or nontransmittable properties.</span></span> <span data-ttu-id="b2351-122">传输属性与邮件一起传输;nontransmittable 属性不会与邮件一起传输。</span><span class="sxs-lookup"><span data-stu-id="b2351-122">Transmittable properties are transferred with a message; nontransmittable properties are not transferred with a message.</span></span> <span data-ttu-id="b2351-123">Nontransmittable 属性通常包含仅对在当前会话中运行的客户端和服务提供程序具有价值的信息。</span><span class="sxs-lookup"><span data-stu-id="b2351-123">Nontransmittable properties usually contain information that is of value only to clients and service providers operating with the current session.</span></span> <span data-ttu-id="b2351-124">这些属性不一定对其他邮件系统和另一组服务提供商有用。</span><span class="sxs-lookup"><span data-stu-id="b2351-124">These properties would not necessarily be useful to another messaging system and another set of service providers.</span></span> <span data-ttu-id="b2351-125">传输属性的概念主要适用于传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b2351-125">The concept of transmittable properties applies primarily to transport providers.</span></span> <span data-ttu-id="b2351-126">若要确定某个属性是否为传输, 请将其 property 标记传递给 Mapitags 头文件中定义的**FIsTransmittable**宏。</span><span class="sxs-lookup"><span data-stu-id="b2351-126">To determine whether a property is transmittable or not, pass its property tag to the **FIsTransmittable** macro, defined in the Mapitags.h header file.</span></span> 
  
<span data-ttu-id="b2351-127">有关标识符范围的完整说明, 请参阅[属性标识符范围](property-identifier-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="b2351-127">For a complete description of the identifier ranges, see [Property Identifier Ranges](property-identifier-ranges.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b2351-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2351-128">See also</span></span>



[<span data-ttu-id="b2351-129">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="b2351-129">MAPI Property Overview</span></span>](mapi-property-overview.md)

