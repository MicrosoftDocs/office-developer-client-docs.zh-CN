---
title: 网关映射职责
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac67bb83-e4f3-4c82-995b-c11a2a195e90
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad5f4e896b748dc0d7495c428af093af57bc7cdd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775014"
---
# <a name="gateway-mapping-responsibilities"></a><span data-ttu-id="cc18a-103">网关映射职责</span><span class="sxs-lookup"><span data-stu-id="cc18a-103">Gateway mapping responsibilities</span></span>

<span data-ttu-id="cc18a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cc18a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cc18a-105">当 MAPI 感知的网关接收邮件，包含名为属性指定用来包含网关可映射属性的特殊属性集之一时，该网关应将的所有属性映射到目标邮件系统的协议。</span><span class="sxs-lookup"><span data-stu-id="cc18a-105">When a MAPI-aware gateway receives a message containing named properties in one of the special property sets designated to contain gateway-mappable properties, the gateway should map all of the properties to the protocol of the destination messaging system.</span></span> <span data-ttu-id="cc18a-106">尽管 MAPI 建议网关处理中的特殊属性集的所有命名的属性，应网关处理只有两： 电子邮件地址和地址类型。</span><span class="sxs-lookup"><span data-stu-id="cc18a-106">Although MAPI recommends that gateways handle all named properties in the special property sets, gateways are expected to handle only two: email address and address type.</span></span> <span data-ttu-id="cc18a-107">电子邮件地址和地址类型属性直接影响消息传输，因为它非常重要的网关支持这两个属性的映射。</span><span class="sxs-lookup"><span data-stu-id="cc18a-107">Because the email address and address type properties directly affect message transmission, it is critical that gateways support the mapping of these two properties.</span></span> <span data-ttu-id="cc18a-108">因为搜索键包含用户的地址类型和地址，他们还应如果可能翻译。</span><span class="sxs-lookup"><span data-stu-id="cc18a-108">Because search keys consist of a user's address type and address, they should also be translated if at all possible.</span></span>
  
<span data-ttu-id="cc18a-109">条目标识符不会经常处理。</span><span class="sxs-lookup"><span data-stu-id="cc18a-109">Entry identifiers are not expected to be handled frequently.</span></span> <span data-ttu-id="cc18a-110">若要启用映射到可由另一个消息系统使用的项标识符的一个邮件系统中的项标识符，该网关必须能够使用两个系统的格式。</span><span class="sxs-lookup"><span data-stu-id="cc18a-110">To enable mapping of an entry identifier that originates in one messaging system to an entry identifier that is usable by another messaging system, the gateway must be able to use the format of both systems.</span></span> <span data-ttu-id="cc18a-111">因为大多数网关不识别条目标识符格式，条目标识符的翻译很少见。</span><span class="sxs-lookup"><span data-stu-id="cc18a-111">Because most gateways are not aware of entry identifier formats, the translation of entry identifiers is rare.</span></span>
  
<span data-ttu-id="cc18a-112">不需要经常转换的另一个可映射属性的显示名称。</span><span class="sxs-lookup"><span data-stu-id="cc18a-112">Another mappable property that is not expected to be translated frequently is the display name.</span></span> <span data-ttu-id="cc18a-113">网关应存储的显示名称和传输，但不是一定翻译。</span><span class="sxs-lookup"><span data-stu-id="cc18a-113">Gateways should store display names and transmit them, but not necessarily translate them.</span></span> 
  

