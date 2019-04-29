---
title: 网关映射责任
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac67bb83-e4f3-4c82-995b-c11a2a195e90
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 214d24bb0b0af525d5e2588c556c37cf720364a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422752"
---
# <a name="gateway-mapping-responsibilities"></a><span data-ttu-id="aa0b8-103">网关映射责任</span><span class="sxs-lookup"><span data-stu-id="aa0b8-103">Gateway mapping responsibilities</span></span>

<span data-ttu-id="aa0b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa0b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa0b8-105">当 MAPI 感知网关收到一封包含命名属性的邮件时, 如果指定了包含网关可映射属性的某个特殊属性集, 该网关应将所有属性映射到目标邮件系统的协议。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-105">When a MAPI-aware gateway receives a message containing named properties in one of the special property sets designated to contain gateway-mappable properties, the gateway should map all of the properties to the protocol of the destination messaging system.</span></span> <span data-ttu-id="aa0b8-106">虽然 MAPI 建议在特殊属性集中处理所有命名属性, 但网关应仅处理两个: 电子邮件地址和地址类型。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-106">Although MAPI recommends that gateways handle all named properties in the special property sets, gateways are expected to handle only two: email address and address type.</span></span> <span data-ttu-id="aa0b8-107">由于电子邮件地址和地址类型属性直接影响邮件传输, 因此网关支持这两个属性的映射是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-107">Because the email address and address type properties directly affect message transmission, it is critical that gateways support the mapping of these two properties.</span></span> <span data-ttu-id="aa0b8-108">由于搜索关键字由用户的地址类型和地址组成, 因此还应转换它们 (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-108">Because search keys consist of a user's address type and address, they should also be translated if at all possible.</span></span>
  
<span data-ttu-id="aa0b8-109">条目标识符不应经常处理。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-109">Entry identifiers are not expected to be handled frequently.</span></span> <span data-ttu-id="aa0b8-110">若要使在一个邮件系统中出现的条目标识符映射到另一个邮件系统可用的条目标识符, 网关必须能够使用这两个系统的格式。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-110">To enable mapping of an entry identifier that originates in one messaging system to an entry identifier that is usable by another messaging system, the gateway must be able to use the format of both systems.</span></span> <span data-ttu-id="aa0b8-111">由于大多数网关都不知道条目标识符格式, 因此条目标识符的转换很少。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-111">Because most gateways are not aware of entry identifier formats, the translation of entry identifiers is rare.</span></span>
  
<span data-ttu-id="aa0b8-112">不希望频繁转换的另一个可映射属性是显示名称。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-112">Another mappable property that is not expected to be translated frequently is the display name.</span></span> <span data-ttu-id="aa0b8-113">网关应存储显示名称并传输它们, 但不一定要进行转换。</span><span class="sxs-lookup"><span data-stu-id="aa0b8-113">Gateways should store display names and transmit them, but not necessarily translate them.</span></span> 
  

