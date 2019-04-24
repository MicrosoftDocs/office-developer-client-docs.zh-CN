---
title: 跨邮件域发送
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 65594253-66cd-486a-aa5b-0bc719f761f0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddbaa4aeacf17f2c266ccc0ff963d005f9e403ec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339716"
---
# <a name="sending-across-messaging-domains"></a><span data-ttu-id="46963-103">跨邮件域发送</span><span class="sxs-lookup"><span data-stu-id="46963-103">Sending Across Messaging Domains</span></span>

  
  
<span data-ttu-id="46963-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46963-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46963-105">邮件域代表共享公用地址格式的一个或多个邮件系统。</span><span class="sxs-lookup"><span data-stu-id="46963-105">A messaging domain represents one or more messaging systems that share a common address format.</span></span> <span data-ttu-id="46963-106">跨多个邮件域的通信需要将以原始邮件域格式发送的邮件转换为目标邮件域的格式。</span><span class="sxs-lookup"><span data-stu-id="46963-106">Communication across multiple messaging domains involves translating a message sent in the format of the original messaging domain into the format of the destination messaging domain.</span></span> <span data-ttu-id="46963-107">因为并非所有地址格式都兼容, 所以需要一个网关将源格式的寻址信息转换为目标格式。</span><span class="sxs-lookup"><span data-stu-id="46963-107">Because not all address formats are compatible, a gateway is needed to translate the addressing information from the source format into the destination format.</span></span> <span data-ttu-id="46963-108">为了确保邮件域之间的有效性, 客户端应用程序将重要的寻址信息存储在 MAPI 属性中。</span><span class="sxs-lookup"><span data-stu-id="46963-108">To ensure validity across messaging domains, client applications store important addressing information in MAPI properties.</span></span> <span data-ttu-id="46963-109">此外, 网关将执行转换, 检查已知需要转换的属性, 并将其更改为目标邮件域可以使用的格式。</span><span class="sxs-lookup"><span data-stu-id="46963-109">In addition, gateways perform the translation, examining the properties known to need translation and changing them to a format that the destination messaging domain can use.</span></span>
  
<span data-ttu-id="46963-110">以前, MAPI 允许仅将此寻址信息与包含邮件当前收件人列表的用户相关联。</span><span class="sxs-lookup"><span data-stu-id="46963-110">Previously, MAPI allowed this addressing information to be associated with only the users who comprise a message's current recipient list.</span></span> <span data-ttu-id="46963-111">描述收件人列表中每个成员的属性 underwent 网关所需的转换, 以确保邮件域的有效性。</span><span class="sxs-lookup"><span data-stu-id="46963-111">The properties describing each member of the recipient list underwent the required translation by the gateway to ensure validity across messaging domains.</span></span> <span data-ttu-id="46963-112">但是, 有些应用程序要求其邮件包括可能是过去收件人的用户的地址信息, 以后将是收件人, 或者永远不会是收件人。</span><span class="sxs-lookup"><span data-stu-id="46963-112">However, some applications require that their messages include addressing information about users that perhaps were recipients in the past, will be recipients in the future, or will never be recipients.</span></span> <span data-ttu-id="46963-113">例如, 将以指定顺序向一组用户发送邮件的路由应用程序会在邮件中嵌入有关这些用户的寻址信息。</span><span class="sxs-lookup"><span data-stu-id="46963-113">For example, routing applications, which send messages in a specified order to a group of users, embed addressing information about these users in the messages.</span></span> <span data-ttu-id="46963-114">嵌入的信息通常包括将来收件人的地址和地址类型, 以及其在路由顺序中的角色和位置、它们的名称以及每个收件人的一个或多个二进制标识符。</span><span class="sxs-lookup"><span data-stu-id="46963-114">The embedded information typically includes the address and address type of the future recipients, and perhaps also their roles and positions in the routing order, their names, and one or more binary identifiers per recipient.</span></span>
  
<span data-ttu-id="46963-115">若要启用邮件以包含有关这些 nonrecipient 用户的信息, MAPI 现在提供了一种策略, 用于确保在邮件域中也能正确翻译此 nonrecipient 信息。</span><span class="sxs-lookup"><span data-stu-id="46963-115">To enable messages to include information about these nonrecipient users, MAPI now includes a strategy for ensuring that this nonrecipient information is also translated correctly across messaging domains.</span></span> <span data-ttu-id="46963-116">此策略基于网关的不可映射属性的概念。</span><span class="sxs-lookup"><span data-stu-id="46963-116">This strategy is based on the concept of gateway-mappable properties.</span></span>
  

