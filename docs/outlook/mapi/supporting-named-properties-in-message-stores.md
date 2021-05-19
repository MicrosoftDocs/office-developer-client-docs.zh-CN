---
title: 支持邮件存储中的命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1c73bb5-b44a-4ec6-89e4-0e2228572b2d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7e33c49d1ed211abf70e04a8bd3c06ca62e88572
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434919"
---
# <a name="supporting-named-properties-in-message-stores"></a><span data-ttu-id="7a170-103">支持邮件存储中的命名属性</span><span class="sxs-lookup"><span data-stu-id="7a170-103">Supporting Named Properties in Message Stores</span></span>

  
  
<span data-ttu-id="7a170-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7a170-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7a170-105">Message 对象的属性可能不在 MAPI 定义的属性集内。</span><span class="sxs-lookup"><span data-stu-id="7a170-105">Message objects can have properties in them that are not in the set of properties defined by MAPI.</span></span> <span data-ttu-id="7a170-106">此类属性可以是未命名的或已命名的。</span><span class="sxs-lookup"><span data-stu-id="7a170-106">Such properties can be unnamed or named.</span></span> <span data-ttu-id="7a170-107">未命名属性必须驻留在 MAPI 定义的一系列属性标识符中。</span><span class="sxs-lookup"><span data-stu-id="7a170-107">Unnamed properties must reside in a range of property identifiers defined by MAPI.</span></span> <span data-ttu-id="7a170-108">命名自定义属性驻留在 MAPI 定义的不同属性标识符范围内。</span><span class="sxs-lookup"><span data-stu-id="7a170-108">Named custom properties reside in a different range of property identifiers defined by MAPI.</span></span> <span data-ttu-id="7a170-109">它们通常由自定义邮件类型使用。</span><span class="sxs-lookup"><span data-stu-id="7a170-109">They are typically used by custom message types.</span></span> <span data-ttu-id="7a170-110">如果要将邮件存储提供程序用作默认邮件存储，则必须支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="7a170-110">Your message store provider must support named properties if it is to be used as the default message store.</span></span> <span data-ttu-id="7a170-111">支持命名属性意味着实现 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 和 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法，以及实现一个或多个映射签名来标识哪些名称与哪些属性标识符一起。</span><span class="sxs-lookup"><span data-stu-id="7a170-111">Supporting named properties means implementing the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods, and implementing one or more mapping signatures that identify what names go with what property identifiers.</span></span> <span data-ttu-id="7a170-112">有关详细信息，请参阅定义[新的 MAPI 属性](defining-new-mapi-properties.md)[和支持命名属性](supporting-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7a170-112">For more information, see [Defining New MAPI Properties](defining-new-mapi-properties.md) and [Supporting Named Properties](supporting-named-properties.md).</span></span>
  
<span data-ttu-id="7a170-113">大多数支持命名属性的邮件存储提供程序对邮件存储中所有对象使用单个映射签名。</span><span class="sxs-lookup"><span data-stu-id="7a170-113">Most message store providers that support named properties use a single mapping signature for all objects in the message store.</span></span> <span data-ttu-id="7a170-114">这有两个好处。</span><span class="sxs-lookup"><span data-stu-id="7a170-114">This has two benefits.</span></span> <span data-ttu-id="7a170-115">首先，如果只有一个要跟踪的映射签名，则实现映射签名会更简单。</span><span class="sxs-lookup"><span data-stu-id="7a170-115">First, it is simpler to implement mapping signatures if there is only one to keep track of.</span></span> <span data-ttu-id="7a170-116">其次，如果邮件存储中所有对象都使用相同的映射签名，则客户端应用程序会确保邮件存储中邮件的所有属性标识符实际上都引用同一命名属性。</span><span class="sxs-lookup"><span data-stu-id="7a170-116">Second, if all objects in the message store use the same mapping signature, client applications are assured that all property identifiers on messages in the message store actually refer to the same named property.</span></span> <span data-ttu-id="7a170-117">这使客户端应用程序能够显示其文件夹视图界面中命名属性的列。</span><span class="sxs-lookup"><span data-stu-id="7a170-117">This enables client applications to display columns for named properties in their folder view interface.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a170-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a170-118">See also</span></span>



[<span data-ttu-id="7a170-119">实现邮件存储中的邮件</span><span class="sxs-lookup"><span data-stu-id="7a170-119">Implementing Messages in Message Stores</span></span>](implementing-messages-in-message-stores.md)

