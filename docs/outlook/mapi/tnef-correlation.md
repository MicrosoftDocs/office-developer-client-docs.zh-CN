---
title: TNEF 相关性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93d1716d-a0be-45aa-85d2-6c9be65f5fd2
description: 上次修改时间：2013 年 3 月 12 日
ms.openlocfilehash: 8d601bb2bbc65e21c5bc83179cc29e53ddd33876
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410369"
---
# <a name="tnef-correlation"></a><span data-ttu-id="4f35b-103">TNEF 相关性</span><span class="sxs-lookup"><span data-stu-id="4f35b-103">TNEF Correlation</span></span>

 
  
<span data-ttu-id="4f35b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f35b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4f35b-105">某些邮件系统对附加到入站邮件的任何 Transport-Neutral 封装格式 (TNEF) 流执行相关检查，以验证 TNEF 流实际上是否属于该邮件。</span><span class="sxs-lookup"><span data-stu-id="4f35b-105">Some messaging systems perform a correlation check on any Transport-Neutral Encapsulation Format (TNEF) stream attached to an inbound message to verify that the TNEF stream does in fact belong to that message.</span></span> <span data-ttu-id="4f35b-106">这包括将入站邮件头中某些字段的值与存储在 TNEF 流中的某些属性中的该值的副本进行匹配。</span><span class="sxs-lookup"><span data-stu-id="4f35b-106">This involves matching the value of some field in the header of the inbound message with a copy of that value stored in some property in the TNEF stream.</span></span> <span data-ttu-id="4f35b-107">通常，对于每封邮件唯一的值（如邮件 ID 号）通常用于此。</span><span class="sxs-lookup"><span data-stu-id="4f35b-107">Values that are presumably unique for each message, such as message ID numbers, are typically used for this.</span></span> <span data-ttu-id="4f35b-108">创建 TNEF 流的传输或网关负责从邮件头选择一个合适的值，在将传出邮件的属性编码到 TNEF 流之前，将副本放入相应的属性中。</span><span class="sxs-lookup"><span data-stu-id="4f35b-108">The transport or gateway that created the TNEF stream is responsible for choosing an appropriate value from the message header and placing a copy into an appropriate property before encoding the outgoing message's properties into the TNEF stream.</span></span> <span data-ttu-id="4f35b-109">然后，接收邮件的网关或传输可以从 TNEF 流中提取该属性并验证其值是否与入站邮件上相应头字段的值匹配。</span><span class="sxs-lookup"><span data-stu-id="4f35b-109">Gateways or transports that receive the message can then extract that property from the TNEF stream and verify that its value matches the value of the corresponding header field on the inbound message.</span></span>
  
<span data-ttu-id="4f35b-110">如果值不匹配，网关或传输应丢弃 TNEF 流并仅处理本机邮件信封。</span><span class="sxs-lookup"><span data-stu-id="4f35b-110">If the values do not match, the gateway or transport should discard the TNEF stream and process only the native message envelope.</span></span> <span data-ttu-id="4f35b-111">此类检查是谨慎的，因为非基于 MAPI 的邮件客户端可能会将包含 TNEF 流的文件从旧邮件附加到转发，甚至是不相关的邮件;如果未选中，则此类错误可能导致邮件文本丢失。</span><span class="sxs-lookup"><span data-stu-id="4f35b-111">Such checks are prudent because non-MAPI-based mail clients may attach a file that contains a TNEF stream from an old message to a forwarding or even an unrelated message; if not checked, such an error may cause the loss of message text.</span></span>
  
<span data-ttu-id="4f35b-112">选择的邮件头字段值必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4f35b-112">The header field value chosen must be unique to the message.</span></span> <span data-ttu-id="4f35b-113">所有邮件系统没有固定的邮件头字段，因为不同的邮件系统使用不同的头字段，但通常邮件系统为邮件分配一个适合此目的的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4f35b-113">There is no fixed header field for all messaging systems because different messaging systems use different header fields, but typically the messaging system assigns a unique identifier to the message which is suitable for this purpose.</span></span> <span data-ttu-id="4f35b-114">例如，SMTP 系统通常使用 MessageID 标头，而 X.400 系统通常使用 IM_THIS_IPM 属性。</span><span class="sxs-lookup"><span data-stu-id="4f35b-114">For example, SMTP systems typically use the MessageID header, while X.400 systems typically use the IM_THIS_IPM attribute.</span></span>
  

