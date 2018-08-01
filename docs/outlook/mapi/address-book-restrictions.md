---
title: 通讯簿限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ace8c03-45a7-484b-8c12-516ac0e40dc2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b8ad765a2bbd3aafd87a7eff79993978816729b2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774517"
---
# <a name="address-book-restrictions"></a><span data-ttu-id="fad56-103">通讯簿限制</span><span class="sxs-lookup"><span data-stu-id="fad56-103">Address Book Restrictions</span></span>

  
  
<span data-ttu-id="fad56-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fad56-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fad56-105">要在其容器的内容表支持三种类型的限制，通讯簿提供程序被必需:</span><span class="sxs-lookup"><span data-stu-id="fad56-105">Address book providers are required to support three types of restrictions on the contents tables of their containers:</span></span>
  
- <span data-ttu-id="fad56-106">模糊名称属性限制</span><span class="sxs-lookup"><span data-stu-id="fad56-106">Ambiguous name property restrictions</span></span>
    
- <span data-ttu-id="fad56-107">实例 key 属性限制</span><span class="sxs-lookup"><span data-stu-id="fad56-107">Instance key property restrictions</span></span>
    
- <span data-ttu-id="fad56-108">前缀的显示名称内容限制</span><span class="sxs-lookup"><span data-stu-id="fad56-108">Prefixed display name content restrictions</span></span>
    
<span data-ttu-id="fad56-109">模糊名称限制是属性限制使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性来匹配地址簿容器中条目的收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="fad56-109">Ambiguous name restrictions are property restrictions using the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property to match recipient names with entries in address book containers.</span></span> <span data-ttu-id="fad56-110">**PR_ANR**属性限制是"最佳猜测"搜索通讯簿提供程序，从而使得可以选择最适合其容器的匹配属性的类型。</span><span class="sxs-lookup"><span data-stu-id="fad56-110">The **PR_ANR** property restriction is a "best guess" type of search whereby address book providers can choose the matching property that works best for their container.</span></span> <span data-ttu-id="fad56-111">例如，一个通讯簿提供程序可能通过匹配的收件人姓名，针对每个容器条目的**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 属性来实现**PR_ANR**限制，而其他提供程序可能使用**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="fad56-111">For example, one address book provider might implement the **PR_ANR** restriction by matching recipient names against the **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) property of each container entry whereas another provider might use **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span>
  
<span data-ttu-id="fad56-112">MAPI 建议的**PR_ANR**限制实现 strike 足够性能和用户满意度之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="fad56-112">MAPI recommends that implementations of the **PR_ANR** restriction strike a balance between adequate performance and user satisfaction.</span></span> <span data-ttu-id="fad56-113">通讯簿提供程序实现如限制时，可能会破坏用户满意度找到太少或太多的匹配项的方式。</span><span class="sxs-lookup"><span data-stu-id="fad56-113">User satisfaction can be compromised when an address book provider implements the restriction in such a way that too few or too many matches are found.</span></span> <span data-ttu-id="fad56-114">某些通讯簿提供程序支持称为不可显示在对话框中，但可以匹配模糊名称限制的可分辨，或常见，名称。</span><span class="sxs-lookup"><span data-stu-id="fad56-114">Some address book providers support what is known as a distinguished, or common, name that is not displayable in a dialog box but can match an ambiguous name restriction.</span></span> 
  
<span data-ttu-id="fad56-115">典型的实现可能为单词、 匹配任何项，其中包含的所有单词解析收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fad56-115">A typical implementation might be to parse the recipient's display name into words, matching any entry that contains all of the words.</span></span> <span data-ttu-id="fad56-116">注意详细信息，如敏感度 word 位置、 是否匹配不连续的单词，和选择分隔符可能不同。</span><span class="sxs-lookup"><span data-stu-id="fad56-116">Attention to details such as sensitivity to word position, whether nonconsecutive words are matched, and the choice of separator characters can vary.</span></span> <span data-ttu-id="fad56-117">例如，如果解析名称为"Bill L"，典型的**PR_ANR**限制将视为匹配选择以下项：</span><span class="sxs-lookup"><span data-stu-id="fad56-117">For example, if the name to be resolved is "Bill L," a typical **PR_ANR** restriction would select the following entries as matching:</span></span> 
  
- <span data-ttu-id="fad56-118">Billy Larson</span><span class="sxs-lookup"><span data-stu-id="fad56-118">Billy Larson</span></span>
    
- <span data-ttu-id="fad56-119">Bill 李</span><span class="sxs-lookup"><span data-stu-id="fad56-119">Bill Lee</span></span>
    
- <span data-ttu-id="fad56-120">Bill 日志职位需求。</span><span class="sxs-lookup"><span data-stu-id="fad56-120">Bill Logan Jr.</span></span> 
    
- <span data-ttu-id="fad56-121">Sam Bill 李</span><span class="sxs-lookup"><span data-stu-id="fad56-121">Sam Bill Lee</span></span>
    
<span data-ttu-id="fad56-122">实例键限制或**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性限制的客户端应用程序中使用查看 MAPI 表的列表框实现中使用。</span><span class="sxs-lookup"><span data-stu-id="fad56-122">Instance key restrictions, or **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property restrictions, are used in the implementation of list boxes that are used in client applications for viewing MAPI tables.</span></span> <span data-ttu-id="fad56-123">某些列表框实现允许用户进行多个选择，向上滚动或向下，并返回到第一项选择。</span><span class="sxs-lookup"><span data-stu-id="fad56-123">Some list box implementations allow users to make multiple selections, scroll up or down, and return to the first item selected.</span></span> <span data-ttu-id="fad56-124">若要实现此行为，客户端调用[IMAPITable::FindRow](imapitable-findrow.md)，将属性限制**PR_INSTANCE_KEY**属性传递给方法。</span><span class="sxs-lookup"><span data-stu-id="fad56-124">To implement this behavior, clients call [IMAPITable::FindRow](imapitable-findrow.md), passing a property restriction on the **PR_INSTANCE_KEY** property to the method.</span></span> <span data-ttu-id="fad56-125">通讯簿提供程序需要支持此限制。</span><span class="sxs-lookup"><span data-stu-id="fad56-125">Address book providers are required to support this restriction.</span></span> 
  
<span data-ttu-id="fad56-126">用于查看表的列表框的另一个功能是能够将光标基于一的前缀字符。</span><span class="sxs-lookup"><span data-stu-id="fad56-126">Another feature of list boxes used for table viewing is the ability to position the cursor based on a set of prefix characters.</span></span> <span data-ttu-id="fad56-127">在用户启动键入前缀字符时，客户端将光标移到这些字符开头的第一项。</span><span class="sxs-lookup"><span data-stu-id="fad56-127">As the user starts typing prefix characters, the client moves the cursor to the first item that begins with these characters.</span></span> <span data-ttu-id="fad56-128">客户端与基于**PR_DISPLAY_NAME**属性和 FL_PREFIX 模糊级别内容限制实现此功能。</span><span class="sxs-lookup"><span data-stu-id="fad56-128">Clients implement this feature with a content restriction based on the **PR_DISPLAY_NAME** property and the FL_PREFIX fuzzy level.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fad56-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fad56-129">See also</span></span>



[<span data-ttu-id="fad56-130">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="fad56-130">MAPI Tables</span></span>](mapi-tables.md)

