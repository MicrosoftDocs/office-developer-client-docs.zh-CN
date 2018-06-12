---
title: 支持在消息存储中的命名的属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1c73bb5-b44a-4ec6-89e4-0e2228572b2d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b1aa0228cdc8cf6f0b2bb321e62e40127775a6de
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778912"
---
# <a name="supporting-named-properties-in-message-stores"></a><span data-ttu-id="87271-103">支持在消息存储中的命名的属性</span><span class="sxs-lookup"><span data-stu-id="87271-103">Supporting Named Properties in Message Stores</span></span>

  
  
<span data-ttu-id="87271-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="87271-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="87271-105">消息对象可在其集合中的定义的 MAPI 属性不具有属性。</span><span class="sxs-lookup"><span data-stu-id="87271-105">Message objects can have properties in them that are not in the set of properties defined by MAPI.</span></span> <span data-ttu-id="87271-106">此类属性可未命名的或名为。</span><span class="sxs-lookup"><span data-stu-id="87271-106">Such properties can be unnamed or named.</span></span> <span data-ttu-id="87271-107">未命名的属性必须驻留在范围定义的 MAPI 属性标识符。</span><span class="sxs-lookup"><span data-stu-id="87271-107">Unnamed properties must reside in a range of property identifiers defined by MAPI.</span></span> <span data-ttu-id="87271-108">命名自定义属性位于不同范围的定义的 MAPI 属性标识符。</span><span class="sxs-lookup"><span data-stu-id="87271-108">Named custom properties reside in a different range of property identifiers defined by MAPI.</span></span> <span data-ttu-id="87271-109">他们通常使用自定义消息类型。</span><span class="sxs-lookup"><span data-stu-id="87271-109">They are typically used by custom message types.</span></span> <span data-ttu-id="87271-110">消息存储提供程序必须支持命名的属性，它是否要用作默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="87271-110">Your message store provider must support named properties if it is to be used as the default message store.</span></span> <span data-ttu-id="87271-111">支持命名属性是指实现[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法和实现确定哪些名称的一个或多个映射签名转与哪些属性标识符。</span><span class="sxs-lookup"><span data-stu-id="87271-111">Supporting named properties means implementing the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods, and implementing one or more mapping signatures that identify what names go with what property identifiers.</span></span> <span data-ttu-id="87271-112">有关详细信息，请参阅[定义新的 MAPI 属性](defining-new-mapi-properties.md)和[支持命名属性](supporting-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="87271-112">For more information, see [Defining New MAPI Properties](defining-new-mapi-properties.md) and [Supporting Named Properties](supporting-named-properties.md).</span></span>
  
<span data-ttu-id="87271-113">大多数消息存储提供程序支持的名为属性使用的单个映射签名的消息存储区中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="87271-113">Most message store providers that support named properties use a single mapping signature for all objects in the message store.</span></span> <span data-ttu-id="87271-114">这有两个好处。</span><span class="sxs-lookup"><span data-stu-id="87271-114">This has two benefits.</span></span> <span data-ttu-id="87271-115">首先，它是实现映射签名，如果只有一个以跟踪变得简单。</span><span class="sxs-lookup"><span data-stu-id="87271-115">First, it is simpler to implement mapping signatures if there is only one to keep track of.</span></span> <span data-ttu-id="87271-116">其次，如果邮件存储区中的所有对象都使用相同的映射签名，客户端应用程序并能保证邮件存储区中的邮件的所有属性标识符实际都引用相同的命名属性。</span><span class="sxs-lookup"><span data-stu-id="87271-116">Second, if all objects in the message store use the same mapping signature, client applications are assured that all property identifiers on messages in the message store actually refer to the same named property.</span></span> <span data-ttu-id="87271-117">这样，客户端应用程序在其文件夹视图界面中显示的命名属性的列。</span><span class="sxs-lookup"><span data-stu-id="87271-117">This enables client applications to display columns for named properties in their folder view interface.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="87271-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87271-118">See also</span></span>



[<span data-ttu-id="87271-119">消息存储库中实现消息</span><span class="sxs-lookup"><span data-stu-id="87271-119">Implementing Messages in Message Stores</span></span>](implementing-messages-in-message-stores.md)

