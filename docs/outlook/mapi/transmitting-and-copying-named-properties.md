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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356642"
---
# <a name="transmitting-and-copying-named-properties"></a><span data-ttu-id="063b8-103">传输和复制命名属性</span><span class="sxs-lookup"><span data-stu-id="063b8-103">Transmitting and Copying Named Properties</span></span>

  
  
<span data-ttu-id="063b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="063b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="063b8-105">只要发送、移动或复制命名的属性, 名称将保持不变, 但标识符必须更改以符合目标对象的映射。</span><span class="sxs-lookup"><span data-stu-id="063b8-105">Whenever a named property is sent, moved, or copied, the name remains constant but the identifier must change to adhere to the mapping of the destination object.</span></span> <span data-ttu-id="063b8-106">此规则的唯一例外是当源和目标具有相同的映射签名时, 再进行不必要的映射。</span><span class="sxs-lookup"><span data-stu-id="063b8-106">The only exception to this rule is when the source and destination have the same mapping signature, making remapping unnecessary.</span></span>
  
<span data-ttu-id="063b8-107">传输提供程序负责将已传输的命名属性的名称重新映射到在目标上工作的相应标识符。</span><span class="sxs-lookup"><span data-stu-id="063b8-107">It is the responsibility of the transport provider to remap the names of transmitted named properties to appropriate identifiers that work at the destination.</span></span> <span data-ttu-id="063b8-108">发送传输提供程序无法知道目标是正确的映射。它必须传输名称, 并依靠接收的传输提供程序将它们映射到工作的标识符。</span><span class="sxs-lookup"><span data-stu-id="063b8-108">The sending transport provider cannot know what the correct mapping is at the destination; it must transmit the names and rely on the receiving transport provider to map them to identifiers that work.</span></span> <span data-ttu-id="063b8-109">TNEF 的 MAPI 实现处理传输提供程序的命名属性的重映射。</span><span class="sxs-lookup"><span data-stu-id="063b8-109">The MAPI implementation of TNEF handles the remapping of named properties for transport providers.</span></span> <span data-ttu-id="063b8-110">传输提供程序既可以手动处理重新映射, 也可以使用 TNEF 实现。</span><span class="sxs-lookup"><span data-stu-id="063b8-110">Transport providers can either handle the remapping manually or use the TNEF implementation.</span></span> 
  
<span data-ttu-id="063b8-111">当在邮件存储之间复制这些属性时, 必须进行类似的命名属性重新映射。</span><span class="sxs-lookup"><span data-stu-id="063b8-111">A similar remapping of named properties must occur when these properties are copied between message stores.</span></span> <span data-ttu-id="063b8-112">但是, 由于邮件存储提供程序可以检索名称以映射目标的标识符, 因此可以立即重新映射属性, 而不必依赖目标邮件存储。</span><span class="sxs-lookup"><span data-stu-id="063b8-112">However, because message store providers can retrieve the name to identifier mapping of the destination, they can remap the properties right away and not have to rely on the destination message store.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="063b8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="063b8-113">See also</span></span>



[<span data-ttu-id="063b8-114">MAPI 命名属性</span><span class="sxs-lookup"><span data-stu-id="063b8-114">MAPI Named Properties</span></span>](mapi-named-properties.md)

