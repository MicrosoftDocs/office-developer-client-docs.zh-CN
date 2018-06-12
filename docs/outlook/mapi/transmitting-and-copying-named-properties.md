---
title: 传输和复制命名的属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 37075cfc-461d-4983-9045-d9f1da6739be
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a5d2244270463fcc2fe0a9786112590e741a8a66
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778994"
---
# <a name="transmitting-and-copying-named-properties"></a><span data-ttu-id="222e2-103">传输和复制命名的属性</span><span class="sxs-lookup"><span data-stu-id="222e2-103">Transmitting and Copying Named Properties</span></span>

  
  
<span data-ttu-id="222e2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="222e2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="222e2-105">发送的命名的属性时，移动或复制，名称保持不变，但必须更改标识符遵守的目标对象映射。</span><span class="sxs-lookup"><span data-stu-id="222e2-105">Whenever a named property is sent, moved, or copied, the name remains constant but the identifier must change to adhere to the mapping of the destination object.</span></span> <span data-ttu-id="222e2-106">对此规则唯一的例外是源和目标具有相同的映射签名时, 进行重新映射不必要。</span><span class="sxs-lookup"><span data-stu-id="222e2-106">The only exception to this rule is when the source and destination have the same mapping signature, making remapping unnecessary.</span></span>
  
<span data-ttu-id="222e2-107">是要重新映射到相应的标识符在目标工作的传输命名属性的名称的传输提供程序的责任。</span><span class="sxs-lookup"><span data-stu-id="222e2-107">It is the responsibility of the transport provider to remap the names of transmitted named properties to appropriate identifiers that work at the destination.</span></span> <span data-ttu-id="222e2-108">发送传输提供程序无法知道什么正确映射是在目标;它必须传输名称，并依赖于接收的传输提供程序，以将其映射到工作的标识符。</span><span class="sxs-lookup"><span data-stu-id="222e2-108">The sending transport provider cannot know what the correct mapping is at the destination; it must transmit the names and rely on the receiving transport provider to map them to identifiers that work.</span></span> <span data-ttu-id="222e2-109">TNEF 的 MAPI 实现处理传输提供程序将命名属性。</span><span class="sxs-lookup"><span data-stu-id="222e2-109">The MAPI implementation of TNEF handles the remapping of named properties for transport providers.</span></span> <span data-ttu-id="222e2-110">传输提供程序可以处理重新映射手动或使用 TNEF 实现。</span><span class="sxs-lookup"><span data-stu-id="222e2-110">Transport providers can either handle the remapping manually or use the TNEF implementation.</span></span> 
  
<span data-ttu-id="222e2-111">消息存储之间复制这些属性时，必须发生命名属性类似重新映射。</span><span class="sxs-lookup"><span data-stu-id="222e2-111">A similar remapping of named properties must occur when these properties are copied between message stores.</span></span> <span data-ttu-id="222e2-112">但是，因为消息存储提供程序可以检索到的目标的标识符映射的名称，他们可以立即重新映射属性，并不需要依赖目标消息存储区。</span><span class="sxs-lookup"><span data-stu-id="222e2-112">However, because message store providers can retrieve the name to identifier mapping of the destination, they can remap the properties right away and not have to rely on the destination message store.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="222e2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="222e2-113">See also</span></span>



[<span data-ttu-id="222e2-114">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="222e2-114">MAPI Named Properties</span></span>](mapi-named-properties.md)

