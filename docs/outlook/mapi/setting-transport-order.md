---
title: 设置传输顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4a140ec3-9520-4119-a975-0fb6c1049967
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: efa2d6ab9edbd50634093b5185ef9036689f1379
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433596"
---
# <a name="setting-transport-order"></a><span data-ttu-id="c45d1-103">设置传输顺序</span><span class="sxs-lookup"><span data-stu-id="c45d1-103">Setting Transport Order</span></span>

  
  
<span data-ttu-id="c45d1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c45d1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c45d1-105">MAPI 后台处理程序根据传输提供程序声明可以处理的地址类型和标识符分配传出邮件的责任。</span><span class="sxs-lookup"><span data-stu-id="c45d1-105">The MAPI spooler assigns responsibility for outgoing messages based on the address types and identifiers that transport providers declare they can handle.</span></span> <span data-ttu-id="c45d1-106">当 MAPI 在登录后直接调用 [其 IXPLogon：：AddressTypes](ixplogon-addresstypes.md)方法时，传输提供程序将发布受支持的地址类型和标识符的列表（存储在 **MAPIUID** 结构中）。</span><span class="sxs-lookup"><span data-stu-id="c45d1-106">Transport providers publish a list of supported address types and identifiers — stored in **MAPIUID** structures — when MAPI calls their [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method, directly after logon.</span></span> <span data-ttu-id="c45d1-107">收件人的地址类型存储在其[PidTagAddressType PR_ADDRTYPE (PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性中。 </span><span class="sxs-lookup"><span data-stu-id="c45d1-107">A recipient's address type is stored in its **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="c45d1-108">注册地址类型向 MAPI 指示传输提供程序可以发送给其 PR_ADDRTYPE **属性设置为** 注册地址类型的收件人。</span><span class="sxs-lookup"><span data-stu-id="c45d1-108">Registering for an address type indicates to MAPI that the transport provider can deliver to recipients with their **PR_ADDRTYPE** property set to the registered address type.</span></span> <span data-ttu-id="c45d1-109">同样，注册 **MAPIUID** 指示传输提供程序可以传递至使用注册 **的 MAPIUID** 的条目标识符表示的收件人。</span><span class="sxs-lookup"><span data-stu-id="c45d1-109">Similarly, registering for a **MAPIUID** indicates that the transport provider can deliver to recipients that are represented by entry identifiers with the registered **MAPIUID**.</span></span>
  
<span data-ttu-id="c45d1-110">大多数传输提供程序注册一个或多个地址类型;很少通过 **MAPIUID 注册**。</span><span class="sxs-lookup"><span data-stu-id="c45d1-110">Most transport providers register for one or more address types; few register by **MAPIUID**.</span></span> <span data-ttu-id="c45d1-111">与通讯簿提供程序紧密结合并了解其条目标识符格式的传输提供程序可以通过 **MAPIUID** 注册以处理邮件，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="c45d1-111">Transport providers that are tightly coupled with an address book provider and understand its entry identifier format can register to handle messages by **MAPIUID**, thereby improving performance.</span></span> <span data-ttu-id="c45d1-112">这些紧密耦合的传输提供程序可以从条目标识符中提取收件人的电子邮件地址和其他必要信息，而无需使用 **IMAPISupport：：OpenEntry** 调用打开它。</span><span class="sxs-lookup"><span data-stu-id="c45d1-112">These tightly coupled transport providers can extract the recipient's email address and other necessary information from the entry identifier without having to open it with an **IMAPISupport::OpenEntry** call.</span></span> 
  
<span data-ttu-id="c45d1-113">MAPI 维护传输提供程序的顺序，当多个传输提供程序已注册同一地址类型或 **MAPIUID 时，**</span><span class="sxs-lookup"><span data-stu-id="c45d1-113">MAPI maintains an order for transport providers, used when multiple transport providers have registered for the same address type or **MAPIUID**.</span></span> <span data-ttu-id="c45d1-114">可以通过调用 [IMsgServiceAdmin：：MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)并传递由 _lpUIDList_ 参数指向的所有活动传输提供程序的 **MAPIUID** 的有序列表来替代此顺序：</span><span class="sxs-lookup"><span data-stu-id="c45d1-114">You can override this order by calling [IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md) and passing an ordered list of the **MAPIUID** s of all of the active transport providers pointed to by the  _lpUIDList_ parameter.:</span></span> 
  
<span data-ttu-id="c45d1-115">若要检索一个活动传输提供程序可以处理的所有地址类型的列表，请调用 [IMAPISession：：EnumAdrTypes](imapisession-enumadrtypes.md)。</span><span class="sxs-lookup"><span data-stu-id="c45d1-115">To retrieve a list of all of the address types that can be handled by one of the active transport providers, call [IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md).</span></span> <span data-ttu-id="c45d1-116">**EnumAdrTypes** 返回一个字符串数组，该数组描述当前会话中处于活动状态的传输提供程序支持的地址类型。</span><span class="sxs-lookup"><span data-stu-id="c45d1-116">**EnumAdrTypes** returns an array of strings that describes address types supported by the transport providers that are active in the current session.</span></span> 
  

