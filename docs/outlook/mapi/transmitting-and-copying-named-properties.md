---
title: 传输和复制命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 37075cfc-461d-4983-9045-d9f1da6739be
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6534e7344a62717e406c112249d26407b0852d93
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437775"
---
# <a name="transmitting-and-copying-named-properties"></a><span data-ttu-id="61cd3-103">传输和复制命名属性</span><span class="sxs-lookup"><span data-stu-id="61cd3-103">Transmitting and Copying Named Properties</span></span>

  
  
<span data-ttu-id="61cd3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61cd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61cd3-105">每当发送、移动或复制命名属性时，名称将保持不变，但必须更改标识符，以遵守目标对象的映射。</span><span class="sxs-lookup"><span data-stu-id="61cd3-105">Whenever a named property is sent, moved, or copied, the name remains constant but the identifier must change to adhere to the mapping of the destination object.</span></span> <span data-ttu-id="61cd3-106">此规则的唯一例外是源和目标具有相同的映射签名，因此不需要重新映射。</span><span class="sxs-lookup"><span data-stu-id="61cd3-106">The only exception to this rule is when the source and destination have the same mapping signature, making remapping unnecessary.</span></span>
  
<span data-ttu-id="61cd3-107">传输提供程序负责将传输的命名属性的名称重新映射为在目标处工作的适当标识符。</span><span class="sxs-lookup"><span data-stu-id="61cd3-107">It is the responsibility of the transport provider to remap the names of transmitted named properties to appropriate identifiers that work at the destination.</span></span> <span data-ttu-id="61cd3-108">发送传输提供程序无法知道目标的正确映射是什么;它必须传输名称并依赖接收传输提供程序将它们映射到工作的标识符。</span><span class="sxs-lookup"><span data-stu-id="61cd3-108">The sending transport provider cannot know what the correct mapping is at the destination; it must transmit the names and rely on the receiving transport provider to map them to identifiers that work.</span></span> <span data-ttu-id="61cd3-109">TNEF 的 MAPI 实现处理传输提供程序的命名属性的重新映射。</span><span class="sxs-lookup"><span data-stu-id="61cd3-109">The MAPI implementation of TNEF handles the remapping of named properties for transport providers.</span></span> <span data-ttu-id="61cd3-110">传输提供程序可以手动处理重新映射或使用 TNEF 实现。</span><span class="sxs-lookup"><span data-stu-id="61cd3-110">Transport providers can either handle the remapping manually or use the TNEF implementation.</span></span> 
  
<span data-ttu-id="61cd3-111">在邮件存储之间复制命名属性时，必须发生类似的命名属性重新映射。</span><span class="sxs-lookup"><span data-stu-id="61cd3-111">A similar remapping of named properties must occur when these properties are copied between message stores.</span></span> <span data-ttu-id="61cd3-112">但是，由于邮件存储提供程序可以检索到目标标识符映射的名称，因此它们可以马上重新映射属性，而不需要依赖目标邮件存储。</span><span class="sxs-lookup"><span data-stu-id="61cd3-112">However, because message store providers can retrieve the name to identifier mapping of the destination, they can remap the properties right away and not have to rely on the destination message store.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="61cd3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61cd3-113">See also</span></span>



[<span data-ttu-id="61cd3-114">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="61cd3-114">MAPI Named Properties</span></span>](mapi-named-properties.md)

