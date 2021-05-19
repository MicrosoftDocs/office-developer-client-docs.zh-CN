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
# <a name="address-book-restrictions"></a><span data-ttu-id="d9a54-103">通讯簿限制</span><span class="sxs-lookup"><span data-stu-id="d9a54-103">Address Book Restrictions</span></span>

  
  
<span data-ttu-id="d9a54-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9a54-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9a54-105">通讯簿提供程序需要支持对容器的内容表的三种类型的限制：</span><span class="sxs-lookup"><span data-stu-id="d9a54-105">Address book providers are required to support three types of restrictions on the contents tables of their containers:</span></span>
  
- <span data-ttu-id="d9a54-106">不明确的名称属性限制</span><span class="sxs-lookup"><span data-stu-id="d9a54-106">Ambiguous name property restrictions</span></span>
    
- <span data-ttu-id="d9a54-107">实例键属性限制</span><span class="sxs-lookup"><span data-stu-id="d9a54-107">Instance key property restrictions</span></span>
    
- <span data-ttu-id="d9a54-108">前缀显示名称内容限制</span><span class="sxs-lookup"><span data-stu-id="d9a54-108">Prefixed display name content restrictions</span></span>
    
<span data-ttu-id="d9a54-109">不明确的名称限制是使用 PR_ANR ( [PidTagAnr](pidtaganr-canonical-property.md)) 属性将收件人姓名与通讯簿容器中的条目相匹配的属性限制。</span><span class="sxs-lookup"><span data-stu-id="d9a54-109">Ambiguous name restrictions are property restrictions using the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property to match recipient names with entries in address book containers.</span></span> <span data-ttu-id="d9a54-110">PR_ANR **属性** 限制是一种"最佳猜测"类型的搜索，通过该搜索，通讯簿提供程序可以选择最适合其容器的匹配属性。</span><span class="sxs-lookup"><span data-stu-id="d9a54-110">The **PR_ANR** property restriction is a "best guess" type of search whereby address book providers can choose the matching property that works best for their container.</span></span> <span data-ttu-id="d9a54-111">例如，一个通讯簿提供商可能通过针对每个容器 **条目** 的 **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 属性匹配收件人姓名来实现 PR_ANR 限制，而另一个提供商可能使用 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="d9a54-111">For example, one address book provider might implement the **PR_ANR** restriction by matching recipient names against the **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) property of each container entry whereas another provider might use **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span>
  
<span data-ttu-id="d9a54-112">MAPI 建议实现该 **PR_ANR在足够的** 性能和用户满意度之间取得平衡。</span><span class="sxs-lookup"><span data-stu-id="d9a54-112">MAPI recommends that implementations of the **PR_ANR** restriction strike a balance between adequate performance and user satisfaction.</span></span> <span data-ttu-id="d9a54-113">当通讯簿提供程序实现限制时，发现匹配数过少或匹配过多，可能会损害用户满意度。</span><span class="sxs-lookup"><span data-stu-id="d9a54-113">User satisfaction can be compromised when an address book provider implements the restriction in such a way that too few or too many matches are found.</span></span> <span data-ttu-id="d9a54-114">某些通讯簿提供程序支持所谓的可分辨名称或常用名称，该名称在对话框中无法显示，但可以匹配不明确的名称限制。</span><span class="sxs-lookup"><span data-stu-id="d9a54-114">Some address book providers support what is known as a distinguished, or common, name that is not displayable in a dialog box but can match an ambiguous name restriction.</span></span> 
  
<span data-ttu-id="d9a54-115">典型的实现可能是将收件人的显示名称解析为单词，与包含所有单词的任何条目匹配。</span><span class="sxs-lookup"><span data-stu-id="d9a54-115">A typical implementation might be to parse the recipient's display name into words, matching any entry that contains all of the words.</span></span> <span data-ttu-id="d9a54-116">注意详细信息，例如对单词位置的敏感性、是否匹配非安全单词以及分隔符的选择可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="d9a54-116">Attention to details such as sensitivity to word position, whether nonconsecutive words are matched, and the choice of separator characters can vary.</span></span> <span data-ttu-id="d9a54-117">例如，如果要解析的名称为"Bill L"，则典型的 **PR_ANR限制会** 选择以下条目作为匹配项：</span><span class="sxs-lookup"><span data-stu-id="d9a54-117">For example, if the name to be resolved is "Bill L," a typical **PR_ANR** restriction would select the following entries as matching:</span></span> 
  
- <span data-ttu-id="d9a54-118">Billy Larson</span><span class="sxs-lookup"><span data-stu-id="d9a54-118">Billy Larson</span></span>
    
- <span data-ttu-id="d9a54-119">Bill Lee</span><span class="sxs-lookup"><span data-stu-id="d9a54-119">Bill Lee</span></span>
    
- <span data-ttu-id="d9a54-120">Bill Logan Jr.</span><span class="sxs-lookup"><span data-stu-id="d9a54-120">Bill Logan Jr.</span></span> 
    
- <span data-ttu-id="d9a54-121">Sam Bill Lee</span><span class="sxs-lookup"><span data-stu-id="d9a54-121">Sam Bill Lee</span></span>
    
<span data-ttu-id="d9a54-122">实例键限制PR_INSTANCE_KEY ( [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性限制）用于实现用于查看 MAPI 表的客户端应用程序的列表框。</span><span class="sxs-lookup"><span data-stu-id="d9a54-122">Instance key restrictions, or **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property restrictions, are used in the implementation of list boxes that are used in client applications for viewing MAPI tables.</span></span> <span data-ttu-id="d9a54-123">某些列表框实现允许用户进行多重选择、向上或向下滚动，并返回到选择的第一个项目。</span><span class="sxs-lookup"><span data-stu-id="d9a54-123">Some list box implementations allow users to make multiple selections, scroll up or down, and return to the first item selected.</span></span> <span data-ttu-id="d9a54-124">为了实现此行为，客户端调用 [IMAPITable：：FindRow，](imapitable-findrow.md)将 PR_INSTANCE_KEY **属性的属性** 限制传递给 方法。</span><span class="sxs-lookup"><span data-stu-id="d9a54-124">To implement this behavior, clients call [IMAPITable::FindRow](imapitable-findrow.md), passing a property restriction on the **PR_INSTANCE_KEY** property to the method.</span></span> <span data-ttu-id="d9a54-125">通讯簿提供程序需要支持此限制。</span><span class="sxs-lookup"><span data-stu-id="d9a54-125">Address book providers are required to support this restriction.</span></span> 
  
<span data-ttu-id="d9a54-126">用于表查看的列表框的另一个功能是基于一组前缀字符定位光标的功能。</span><span class="sxs-lookup"><span data-stu-id="d9a54-126">Another feature of list boxes used for table viewing is the ability to position the cursor based on a set of prefix characters.</span></span> <span data-ttu-id="d9a54-127">在用户开始键入前缀字符时，客户端会将光标移到以这些字符开头的第一个项目。</span><span class="sxs-lookup"><span data-stu-id="d9a54-127">As the user starts typing prefix characters, the client moves the cursor to the first item that begins with these characters.</span></span> <span data-ttu-id="d9a54-128">客户端通过基于 PR_DISPLAY_NAME **属性和** 模糊级别的内容FL_PREFIX此功能。</span><span class="sxs-lookup"><span data-stu-id="d9a54-128">Clients implement this feature with a content restriction based on the **PR_DISPLAY_NAME** property and the FL_PREFIX fuzzy level.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d9a54-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9a54-129">See also</span></span>



[<span data-ttu-id="d9a54-130">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="d9a54-130">MAPI Tables</span></span>](mapi-tables.md)

