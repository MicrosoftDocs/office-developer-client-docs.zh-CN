---
title: 通讯簿限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ace8c03-45a7-484b-8c12-516ac0e40dc2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7419c174c1f68653794c2dbd836577e8dd3e596e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432798"
---
# <a name="address-book-restrictions"></a><span data-ttu-id="36a14-103">通讯簿限制</span><span class="sxs-lookup"><span data-stu-id="36a14-103">Address Book Restrictions</span></span>

  
  
<span data-ttu-id="36a14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="36a14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="36a14-105">通讯簿提供程序在其容器的内容表上支持三种类型的限制是必需的:</span><span class="sxs-lookup"><span data-stu-id="36a14-105">Address book providers are required to support three types of restrictions on the contents tables of their containers:</span></span>
  
- <span data-ttu-id="36a14-106">不明确的名称属性限制</span><span class="sxs-lookup"><span data-stu-id="36a14-106">Ambiguous name property restrictions</span></span>
    
- <span data-ttu-id="36a14-107">实例键属性限制</span><span class="sxs-lookup"><span data-stu-id="36a14-107">Instance key property restrictions</span></span>
    
- <span data-ttu-id="36a14-108">带前缀的显示名称内容限制</span><span class="sxs-lookup"><span data-stu-id="36a14-108">Prefixed display name content restrictions</span></span>
    
<span data-ttu-id="36a14-109">不明确的名称限制是使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性将收件人姓名与通讯簿容器中的条目相匹配的属性限制。</span><span class="sxs-lookup"><span data-stu-id="36a14-109">Ambiguous name restrictions are property restrictions using the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property to match recipient names with entries in address book containers.</span></span> <span data-ttu-id="36a14-110">**PR_ANR**属性限制是一种 "最佳推测" 类型的搜索, 使用通讯簿提供程序可以选择最适合其容器的匹配属性。</span><span class="sxs-lookup"><span data-stu-id="36a14-110">The **PR_ANR** property restriction is a "best guess" type of search whereby address book providers can choose the matching property that works best for their container.</span></span> <span data-ttu-id="36a14-111">例如, 一个通讯簿提供程序可以通过针对每个容器条目的**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 属性匹配收件人名称来实现**PR_ANR**限制, 而另一个提供程序可能会使用**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="36a14-111">For example, one address book provider might implement the **PR_ANR** restriction by matching recipient names against the **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) property of each container entry whereas another provider might use **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span>
  
<span data-ttu-id="36a14-112">MAPI 建议**PR_ANR**限制的实现在充分的性能和用户满意度之间达到平衡。</span><span class="sxs-lookup"><span data-stu-id="36a14-112">MAPI recommends that implementations of the **PR_ANR** restriction strike a balance between adequate performance and user satisfaction.</span></span> <span data-ttu-id="36a14-113">当通讯簿提供程序以这样的方式实施限制时, 可能会危及用户满意度, 因为找到的匹配项过少或过多。</span><span class="sxs-lookup"><span data-stu-id="36a14-113">User satisfaction can be compromised when an address book provider implements the restriction in such a way that too few or too many matches are found.</span></span> <span data-ttu-id="36a14-114">某些通讯簿提供程序支持称为可分辨或公用的名称, 该名称在对话框中不可显示, 但可以匹配不明确的名称限制。</span><span class="sxs-lookup"><span data-stu-id="36a14-114">Some address book providers support what is known as a distinguished, or common, name that is not displayable in a dialog box but can match an ambiguous name restriction.</span></span> 
  
<span data-ttu-id="36a14-115">典型的实现可能是将收件人的显示名称解析为词, 并匹配包含所有单词的任何条目。</span><span class="sxs-lookup"><span data-stu-id="36a14-115">A typical implementation might be to parse the recipient's display name into words, matching any entry that contains all of the words.</span></span> <span data-ttu-id="36a14-116">注意对 word 位置的敏感性、不连续单词是否匹配以及分隔符字符的选择可能不同的详细信息。</span><span class="sxs-lookup"><span data-stu-id="36a14-116">Attention to details such as sensitivity to word position, whether nonconsecutive words are matched, and the choice of separator characters can vary.</span></span> <span data-ttu-id="36a14-117">例如, 如果要解析的名称为 "Bill L", 则典型的**PR_ANR**限制将选择以下条目作为匹配:</span><span class="sxs-lookup"><span data-stu-id="36a14-117">For example, if the name to be resolved is "Bill L," a typical **PR_ANR** restriction would select the following entries as matching:</span></span> 
  
- <span data-ttu-id="36a14-118">Billy Larson</span><span class="sxs-lookup"><span data-stu-id="36a14-118">Billy Larson</span></span>
    
- <span data-ttu-id="36a14-119">帐单先生</span><span class="sxs-lookup"><span data-stu-id="36a14-119">Bill Lee</span></span>
    
- <span data-ttu-id="36a14-120">付款人 Logan 先生。</span><span class="sxs-lookup"><span data-stu-id="36a14-120">Bill Logan Jr.</span></span> 
    
- <span data-ttu-id="36a14-121">Sam 帐单先生/</span><span class="sxs-lookup"><span data-stu-id="36a14-121">Sam Bill Lee</span></span>
    
<span data-ttu-id="36a14-122">在用于查看 MAPI 表的客户端应用程序中使用列表框的实现中使用实例密钥限制或**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性限制。</span><span class="sxs-lookup"><span data-stu-id="36a14-122">Instance key restrictions, or **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property restrictions, are used in the implementation of list boxes that are used in client applications for viewing MAPI tables.</span></span> <span data-ttu-id="36a14-123">某些列表框实现允许用户进行多项选择, 向上或向下滚动, 然后返回到选定的第一个项目。</span><span class="sxs-lookup"><span data-stu-id="36a14-123">Some list box implementations allow users to make multiple selections, scroll up or down, and return to the first item selected.</span></span> <span data-ttu-id="36a14-124">若要实现此行为, 客户端调用[IMAPITable:: FindRow](imapitable-findrow.md), 并将**PR_INSTANCE_KEY**属性上的属性限制传递给方法。</span><span class="sxs-lookup"><span data-stu-id="36a14-124">To implement this behavior, clients call [IMAPITable::FindRow](imapitable-findrow.md), passing a property restriction on the **PR_INSTANCE_KEY** property to the method.</span></span> <span data-ttu-id="36a14-125">需要通讯簿提供程序来支持此限制。</span><span class="sxs-lookup"><span data-stu-id="36a14-125">Address book providers are required to support this restriction.</span></span> 
  
<span data-ttu-id="36a14-126">用于表格查看的列表框的另一项功能是能够根据一组前缀字符定位光标。</span><span class="sxs-lookup"><span data-stu-id="36a14-126">Another feature of list boxes used for table viewing is the ability to position the cursor based on a set of prefix characters.</span></span> <span data-ttu-id="36a14-127">当用户开始键入前缀字符时, 客户端会将光标移动到第一个以这些字符开头的项。</span><span class="sxs-lookup"><span data-stu-id="36a14-127">As the user starts typing prefix characters, the client moves the cursor to the first item that begins with these characters.</span></span> <span data-ttu-id="36a14-128">客户端通过基于**PR_DISPLAY_NAME**属性和 FL_PREFIX 模糊级别的内容限制来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="36a14-128">Clients implement this feature with a content restriction based on the **PR_DISPLAY_NAME** property and the FL_PREFIX fuzzy level.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="36a14-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36a14-129">See also</span></span>



[<span data-ttu-id="36a14-130">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="36a14-130">MAPI Tables</span></span>](mapi-tables.md)

