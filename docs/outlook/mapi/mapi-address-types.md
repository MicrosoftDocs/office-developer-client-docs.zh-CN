---
title: MAPI 地址类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eee97982-29be-4dcf-ae11-8a38f0080ea7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b0ff4ecff7a6e834f1e017adc11244657896db03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298010"
---
# <a name="mapi-address-types"></a><span data-ttu-id="fde13-103">MAPI 地址类型</span><span class="sxs-lookup"><span data-stu-id="fde13-103">MAPI Address Types</span></span>

  
  
<span data-ttu-id="fde13-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fde13-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fde13-105">每个邮件用户都与一个地址类型相关联, 该字符串描述存储在**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性中的用户地址的格式。</span><span class="sxs-lookup"><span data-stu-id="fde13-105">Every messaging user is associated with an address type, a character string describing the format of the user's address that is stored in the **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property.</span></span> <span data-ttu-id="fde13-106">地址类型映射到地址格式。</span><span class="sxs-lookup"><span data-stu-id="fde13-106">Address types map to address formats.</span></span> <span data-ttu-id="fde13-107">也就是说, 通过查看收件人的地址类型, 客户端应用程序可以确定如何设置适用于收件人的地址的格式。</span><span class="sxs-lookup"><span data-stu-id="fde13-107">That is, by looking at a recipient's address type, client applications can determine how to format an address appropriate for the recipient.</span></span> 
  
<span data-ttu-id="fde13-108">例如, `SMTP`地址类型指定标准 Internet 地址:</span><span class="sxs-lookup"><span data-stu-id="fde13-108">For example, the  `SMTP` address type specifies the standard Internet address:</span></span> 
  
 `username@companyname.com.`
  
<span data-ttu-id="fde13-109">和, `EX`地址类型指定一个 Exchange 服务器地址。</span><span class="sxs-lookup"><span data-stu-id="fde13-109">And, the  `EX` address type specifies an Exchange Server address.</span></span> 
  
<span data-ttu-id="fde13-110">所有通讯簿条目都必须具有有效的地址类型。</span><span class="sxs-lookup"><span data-stu-id="fde13-110">All address book entries must have a valid address type.</span></span> <span data-ttu-id="fde13-111">当创建通讯簿提供程序不支持的自定义收件人类型时, 客户端要求其用户指定地址类型。</span><span class="sxs-lookup"><span data-stu-id="fde13-111">Clients require their users to specify an address type when creating a type of custom recipient unsupported by the address book provider.</span></span> <span data-ttu-id="fde13-112">对于它们支持的条目, 需要通讯簿提供程序提供有效的地址类型。</span><span class="sxs-lookup"><span data-stu-id="fde13-112">For the entries that they support, address book providers are required to supply valid address types.</span></span> 
  
<span data-ttu-id="fde13-113">MAPI 仅定义一种地址类型: MAPIPDL, 代表个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="fde13-113">MAPI defines only one address type: MAPIPDL, which stands for personal distribution list.</span></span>
  
<span data-ttu-id="fde13-114">若要获取会话中所有传输提供程序支持的地址类型的列表, 客户端应用程序将调用**IMAPISession:: EnumAdrTypes**方法。</span><span class="sxs-lookup"><span data-stu-id="fde13-114">To get a list of the address types supported by all of the transport providers in the session, client applications call the **IMAPISession::EnumAdrTypes** method.</span></span> <span data-ttu-id="fde13-115">有关详细信息, 请参阅[IMAPISession:: EnumAdrTypes](imapisession-enumadrtypes.md)。</span><span class="sxs-lookup"><span data-stu-id="fde13-115">For more information, see [IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md).</span></span>
  

