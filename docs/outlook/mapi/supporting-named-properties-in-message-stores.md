---
title: 支持邮件存储区中的命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1c73bb5-b44a-4ec6-89e4-0e2228572b2d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7e33c49d1ed211abf70e04a8bd3c06ca62e88572
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349642"
---
# <a name="supporting-named-properties-in-message-stores"></a><span data-ttu-id="c7f12-103">支持邮件存储区中的命名属性</span><span class="sxs-lookup"><span data-stu-id="c7f12-103">Supporting Named Properties in Message Stores</span></span>

  
  
<span data-ttu-id="c7f12-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7f12-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7f12-105">Message 对象的属性可能不在 MAPI 定义的属性集中。</span><span class="sxs-lookup"><span data-stu-id="c7f12-105">Message objects can have properties in them that are not in the set of properties defined by MAPI.</span></span> <span data-ttu-id="c7f12-106">此类属性可以是未命名的或命名的。</span><span class="sxs-lookup"><span data-stu-id="c7f12-106">Such properties can be unnamed or named.</span></span> <span data-ttu-id="c7f12-107">未命名属性必须驻留在由 MAPI 定义的属性标识符区域中。</span><span class="sxs-lookup"><span data-stu-id="c7f12-107">Unnamed properties must reside in a range of property identifiers defined by MAPI.</span></span> <span data-ttu-id="c7f12-108">命名的自定义属性驻留在由 MAPI 定义的不同范围的属性标识符中。</span><span class="sxs-lookup"><span data-stu-id="c7f12-108">Named custom properties reside in a different range of property identifiers defined by MAPI.</span></span> <span data-ttu-id="c7f12-109">它们通常由自定义邮件类型使用。</span><span class="sxs-lookup"><span data-stu-id="c7f12-109">They are typically used by custom message types.</span></span> <span data-ttu-id="c7f12-110">如果要将其用作默认邮件存储区, 则您的邮件存储区提供程序必须支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="c7f12-110">Your message store provider must support named properties if it is to be used as the default message store.</span></span> <span data-ttu-id="c7f12-111">支持命名属性意味着实现[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法, 并实现一个或多个映射签名, 这些映射签名可标识名称与属性标识符的不同之处。</span><span class="sxs-lookup"><span data-stu-id="c7f12-111">Supporting named properties means implementing the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods, and implementing one or more mapping signatures that identify what names go with what property identifiers.</span></span> <span data-ttu-id="c7f12-112">有关详细信息, 请参阅[定义新的 MAPI 属性](defining-new-mapi-properties.md)和[支持命名属性](supporting-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c7f12-112">For more information, see [Defining New MAPI Properties](defining-new-mapi-properties.md) and [Supporting Named Properties](supporting-named-properties.md).</span></span>
  
<span data-ttu-id="c7f12-113">大多数支持命名属性的邮件存储提供程序对邮件存储区中的所有对象使用单个映射签名。</span><span class="sxs-lookup"><span data-stu-id="c7f12-113">Most message store providers that support named properties use a single mapping signature for all objects in the message store.</span></span> <span data-ttu-id="c7f12-114">这有两个优点。</span><span class="sxs-lookup"><span data-stu-id="c7f12-114">This has two benefits.</span></span> <span data-ttu-id="c7f12-115">首先, 如果只有一个签名可供跟踪, 则实现映射签名更简单。</span><span class="sxs-lookup"><span data-stu-id="c7f12-115">First, it is simpler to implement mapping signatures if there is only one to keep track of.</span></span> <span data-ttu-id="c7f12-116">其次, 如果邮件存储区中的所有对象都使用相同的映射签名, 客户端应用程序可确保邮件存储区中的邮件的所有属性标识符实际引用相同的命名属性。</span><span class="sxs-lookup"><span data-stu-id="c7f12-116">Second, if all objects in the message store use the same mapping signature, client applications are assured that all property identifiers on messages in the message store actually refer to the same named property.</span></span> <span data-ttu-id="c7f12-117">这使客户端应用程序能够在其文件夹视图界面中显示命名属性的列。</span><span class="sxs-lookup"><span data-stu-id="c7f12-117">This enables client applications to display columns for named properties in their folder view interface.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7f12-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7f12-118">See also</span></span>



[<span data-ttu-id="c7f12-119">实现邮件存储中的邮件</span><span class="sxs-lookup"><span data-stu-id="c7f12-119">Implementing Messages in Message Stores</span></span>](implementing-messages-in-message-stores.md)

