---
title: MAPI 地址类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eee97982-29be-4dcf-ae11-8a38f0080ea7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 20eb429b2574f67e8b28ae96eeb96f42840123d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776181"
---
# <a name="mapi-address-types"></a><span data-ttu-id="141dc-103">MAPI 地址类型</span><span class="sxs-lookup"><span data-stu-id="141dc-103">MAPI Address Types</span></span>

  
  
<span data-ttu-id="141dc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="141dc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="141dc-105">消息的每个用户相关联的地址类型，描述**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性中存储的用户的地址的格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="141dc-105">Every messaging user is associated with an address type, a character string describing the format of the user's address that is stored in the **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property.</span></span> <span data-ttu-id="141dc-106">地址类型映射到地址格式。</span><span class="sxs-lookup"><span data-stu-id="141dc-106">Address types map to address formats.</span></span> <span data-ttu-id="141dc-107">即通过查看收件人的地址类型，客户端应用程序可以确定如何设置适用于收件人的地址的格式。</span><span class="sxs-lookup"><span data-stu-id="141dc-107">That is, by looking at a recipient's address type, client applications can determine how to format an address appropriate for the recipient.</span></span> 
  
<span data-ttu-id="141dc-108">例如，`SMTP`地址类型指定的标准 Internet 地址：</span><span class="sxs-lookup"><span data-stu-id="141dc-108">For example, the  `SMTP` address type specifies the standard Internet address:</span></span> 
  
 `username@companyname.com.`
  
<span data-ttu-id="141dc-109">和，`EX`地址类型指定的 Exchange Server 地址。</span><span class="sxs-lookup"><span data-stu-id="141dc-109">And, the  `EX` address type specifies an Exchange Server address.</span></span> 
  
<span data-ttu-id="141dc-110">所有通讯簿条目必须都具有有效的地址类型。</span><span class="sxs-lookup"><span data-stu-id="141dc-110">All address book entries must have a valid address type.</span></span> <span data-ttu-id="141dc-111">客户端要求其用户创建的自定义不支持通过通讯簿提供程序的收件人类型时指定的地址类型。</span><span class="sxs-lookup"><span data-stu-id="141dc-111">Clients require their users to specify an address type when creating a type of custom recipient unsupported by the address book provider.</span></span> <span data-ttu-id="141dc-112">它们支持的条目，通讯簿提供程序所需提供有效的地址类型。</span><span class="sxs-lookup"><span data-stu-id="141dc-112">For the entries that they support, address book providers are required to supply valid address types.</span></span> 
  
<span data-ttu-id="141dc-113">MAPI 定义只有一个地址类型： MAPIPDL，代表个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="141dc-113">MAPI defines only one address type: MAPIPDL, which stands for personal distribution list.</span></span>
  
<span data-ttu-id="141dc-114">若要获取会话中支持的所有传输提供程序的地址类型的列表，客户端应用程序，请调用**IMAPISession::EnumAdrTypes**方法。</span><span class="sxs-lookup"><span data-stu-id="141dc-114">To get a list of the address types supported by all of the transport providers in the session, client applications call the **IMAPISession::EnumAdrTypes** method.</span></span> <span data-ttu-id="141dc-115">有关详细信息，请参阅[IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md)。</span><span class="sxs-lookup"><span data-stu-id="141dc-115">For more information, see [IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md).</span></span>
  

