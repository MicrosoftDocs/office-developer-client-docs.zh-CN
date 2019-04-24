---
title: MAPI 记录和搜索关键字
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: caa7b7f3-a5a1-4f07-98c9-22652ecd5d21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b1b4c0087cecd9164fc96ce7c5b5415f75dbfb03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328131"
---
# <a name="mapi-record-and-search-keys"></a><span data-ttu-id="16499-103">MAPI 记录和搜索关键字</span><span class="sxs-lookup"><span data-stu-id="16499-103">MAPI Record and Search Keys</span></span>

  
  
<span data-ttu-id="16499-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="16499-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="16499-105">记录键和搜索键是分配给多个 MAPI 对象的二进制标识符。</span><span class="sxs-lookup"><span data-stu-id="16499-105">Record keys and search keys are binary identifiers that are assigned to many MAPI objects.</span></span> <span data-ttu-id="16499-106">与对象的条目标识符不同的是, 它的记录或搜索键可直接比较并传输。</span><span class="sxs-lookup"><span data-stu-id="16499-106">Unlike an object's entry identifier, its record or search key is directly comparable as well as transmittable.</span></span> 
  
## <a name="record-keys"></a><span data-ttu-id="16499-107">记录键</span><span class="sxs-lookup"><span data-stu-id="16499-107">Record Keys</span></span>

<span data-ttu-id="16499-108">记录键用于比较两个对象。</span><span class="sxs-lookup"><span data-stu-id="16499-108">A record key is used to compare two objects.</span></span> <span data-ttu-id="16499-109">邮件存储和通讯簿对象必须具有记录关键字, 这些关键字存储在其**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="16499-109">Message store and address book objects must have record keys, which are stored in their **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property.</span></span> <span data-ttu-id="16499-110">由于记录键标识的是对象而不是其数据, 因此对象的每个实例都有一个唯一的 record 关键字。</span><span class="sxs-lookup"><span data-stu-id="16499-110">Because a record key identifies an object and not its data, every instance of an object has a unique record key.</span></span> <span data-ttu-id="16499-111">文件夹和邮件的记录密钥的范围是邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="16499-111">The scope of a record key for folders and messages is the message store.</span></span> <span data-ttu-id="16499-112">通讯簿容器、邮件用户和通讯组列表的作用域是 MAPI 提供的用于集成通讯簿的一组顶级容器。</span><span class="sxs-lookup"><span data-stu-id="16499-112">The scope for address book containers, messaging users, and distribution lists is the set of top-level containers provided by MAPI for use in the integrated address book.</span></span>
  
<span data-ttu-id="16499-113">记录键可以复制到其他资源中。</span><span class="sxs-lookup"><span data-stu-id="16499-113">Record keys can be duplicated in another resource.</span></span> <span data-ttu-id="16499-114">例如, 两个不同邮件存储区中的不同邮件可以具有相同的记录密钥。</span><span class="sxs-lookup"><span data-stu-id="16499-114">For example, different messages in two different message stores can have the same record key.</span></span> <span data-ttu-id="16499-115">这与长期条目标识符不同;由于长期条目标识符包含对服务提供程序的引用, 因此它们具有更宽的作用域。</span><span class="sxs-lookup"><span data-stu-id="16499-115">This is different from long-term entry identifiers; because long-term entry identifiers contain a reference to the service provider, they have a wider scope.</span></span> <span data-ttu-id="16499-116">邮件存储的记录密钥在范围内与长期条目标识符相似;它在所有邮件存储区提供程序中应是唯一的。</span><span class="sxs-lookup"><span data-stu-id="16499-116">A message store's record key is similar in scope to a long-term entry identifier; it should be unique across all message store providers.</span></span> <span data-ttu-id="16499-117">为了确保这种唯一性, 邮件存储提供程序通常会将其记录密钥设置为其**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性和唯一的邮件存储区的标识符的值。</span><span class="sxs-lookup"><span data-stu-id="16499-117">To ensure this uniqueness, message store providers typically set their record key to a value that is the combination of their **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property and an identifier that is unique to the message store.</span></span>
  
## <a name="search-keys"></a><span data-ttu-id="16499-118">搜索键</span><span class="sxs-lookup"><span data-stu-id="16499-118">Search Keys</span></span>

<span data-ttu-id="16499-119">搜索关键字用于比较两个对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="16499-119">A search key is used to compare the data in two objects.</span></span> <span data-ttu-id="16499-120">对象的搜索关键字存储在其**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="16499-120">An object's search key is stored in its **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property.</span></span> <span data-ttu-id="16499-121">由于搜索关键字代表对象的数据而不是对象本身, 因此具有相同数据的两个不同对象可以具有相同的搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="16499-121">Because a search key represents an object's data and not the object itself, two different objects with the same data can have the same search key.</span></span> <span data-ttu-id="16499-122">例如, 在复制对象时, 原始对象及其副本都具有相同的数据和相同的搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="16499-122">When an object is copied, for example, both the original object and its copy have the same data and the same search key.</span></span>
  
<span data-ttu-id="16499-123">邮件和邮件用户具有搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="16499-123">Messages and messaging users have search keys.</span></span> <span data-ttu-id="16499-124">邮件的搜索关键字是邮件数据的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="16499-124">The search key of a message is a unique identifier of the message's data.</span></span> <span data-ttu-id="16499-125">邮件存储区提供程序在邮件创建时提供邮件的**PR_SEARCH_KEY**属性。</span><span class="sxs-lookup"><span data-stu-id="16499-125">Message store providers furnish a message's **PR_SEARCH_KEY** property at message creation time.</span></span> <span data-ttu-id="16499-126">通讯簿条目的搜索关键字是通过其地址类型 (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))) 和 address (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))) 计算得出的。</span><span class="sxs-lookup"><span data-stu-id="16499-126">The search key of an address book entry is computed from its address type (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))) and address (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))).</span></span> <span data-ttu-id="16499-127">如果通讯簿条目是可写的, 则在使用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法设置地址类型和地址并使用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法保存条目之前, 其搜索关键字可能不可用。</span><span class="sxs-lookup"><span data-stu-id="16499-127">If the address book entry is writeable, its search key might not be available until the address type and address have been set by using the [IMAPIProp::SetProps](imapiprop-setprops.md) method and the entry has been saved by using the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="16499-128">当这些地址属性发生更改时, 在使用**SaveChanges**调用提交更改之前, 相应的搜索关键字可能不会与新值同步。</span><span class="sxs-lookup"><span data-stu-id="16499-128">When these address properties change, it is possible for the corresponding search key not to be synchronized with the new values until the changes have been committed with a **SaveChanges** call.</span></span> 
  
<span data-ttu-id="16499-129">对象的记录键的值可以与它的搜索键的值相同或不同, 具体取决于服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="16499-129">The value of an object's record key can be the same as or different than the value of its search key, depending on the service provider.</span></span> <span data-ttu-id="16499-130">某些服务提供程序对对象的搜索关键字、记录键和条目标识符使用相同的值。</span><span class="sxs-lookup"><span data-stu-id="16499-130">Some service providers use the same value for an object's search key, record key, and entry identifier.</span></span> <span data-ttu-id="16499-131">其他服务提供程序为其每个对象的标识符分配唯一值。</span><span class="sxs-lookup"><span data-stu-id="16499-131">Other service providers assign unique values for each of its objects' identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="16499-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16499-132">See also</span></span>



[<span data-ttu-id="16499-133">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="16499-133">MAPI Application Development</span></span>](mapi-application-development.md)

