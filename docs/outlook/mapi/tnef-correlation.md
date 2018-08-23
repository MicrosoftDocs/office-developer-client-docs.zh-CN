---
title: TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93d1716d-a0be-45aa-85d2-6c9be65f5fd2
description: 上次修改时间： 2013 年 3 月 12 日
ms.openlocfilehash: 5b5af5cee7c58eb300e4020c763431fd96bdd295
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563757"
---
# <a name="tnef-correlation"></a><span data-ttu-id="33898-103">TNEF 相关性</span><span class="sxs-lookup"><span data-stu-id="33898-103">TNEF Correlation</span></span>

 
  
<span data-ttu-id="33898-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33898-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33898-105">某些消息系统执行任何连接到验证 TNEF 流确实实际上属于该邮件的入站消息的传输中性封装格式 (TNEF) 流相关检查。</span><span class="sxs-lookup"><span data-stu-id="33898-105">Some messaging systems perform a correlation check on any Transport-Neutral Encapsulation Format (TNEF) stream attached to an inbound message to verify that the TNEF stream does in fact belong to that message.</span></span> <span data-ttu-id="33898-106">此步骤需要使用 TNEF 流中的某些属性中存储的值的一个副本的入站邮件头中某些字段的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="33898-106">This involves matching the value of some field in the header of the inbound message with a copy of that value stored in some property in the TNEF stream.</span></span> <span data-ttu-id="33898-107">值可能是唯一的每条消息，如消息 ID 号，通常用于此。</span><span class="sxs-lookup"><span data-stu-id="33898-107">Values that are presumably unique for each message, such as message ID numbers, are typically used for this.</span></span> <span data-ttu-id="33898-108">传输或网关创建 TNEF 流负责为从邮件标头中选择适当的值和放置到 TNEF 流编码传出消息的属性之前复制到一个合适的属性。</span><span class="sxs-lookup"><span data-stu-id="33898-108">The transport or gateway that created the TNEF stream is responsible for choosing an appropriate value from the message header and placing a copy into an appropriate property before encoding the outgoing message's properties into the TNEF stream.</span></span> <span data-ttu-id="33898-109">网关或收到消息的传输可以从 TNEF 流提取属性并验证其值匹配的入站邮件上的相应标头字段值。</span><span class="sxs-lookup"><span data-stu-id="33898-109">Gateways or transports that receive the message can then extract that property from the TNEF stream and verify that its value matches the value of the corresponding header field on the inbound message.</span></span>
  
<span data-ttu-id="33898-110">如果值不匹配，则应放弃的网关或传输的 TNEF 流和处理仅本机邮件信封。</span><span class="sxs-lookup"><span data-stu-id="33898-110">If the values do not match, the gateway or transport should discard the TNEF stream and process only the native message envelope.</span></span> <span data-ttu-id="33898-111">此类检查都谨慎，因为不基于 MAPI 的邮件客户端可能将附加包含从旧的邮件转发或甚至无关的消息; TNEF 流的文件如果未选中，这样的错误可能导致丢失的消息文本。</span><span class="sxs-lookup"><span data-stu-id="33898-111">Such checks are prudent because non-MAPI-based mail clients may attach a file that contains a TNEF stream from an old message to a forwarding or even an unrelated message; if not checked, such an error may cause the loss of message text.</span></span>
  
<span data-ttu-id="33898-112">所选的标头字段的值必须是唯一的邮件。</span><span class="sxs-lookup"><span data-stu-id="33898-112">The header field value chosen must be unique to the message.</span></span> <span data-ttu-id="33898-113">因为不同邮件系统使用不同的页眉字段，则没有固定标头字段的所有邮件系统，但消息系统通常分配给适用于此目的的邮件的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="33898-113">There is no fixed header field for all messaging systems because different messaging systems use different header fields, but typically the messaging system assigns a unique identifier to the message which is suitable for this purpose.</span></span> <span data-ttu-id="33898-114">例如，SMTP 系统通常使用 MessageID 标头，而 X.400 系统通常使用 IM_THIS_IPM 属性。</span><span class="sxs-lookup"><span data-stu-id="33898-114">For example, SMTP systems typically use the MessageID header, while X.400 systems typically use the IM_THIS_IPM attribute.</span></span>
  

