---
title: MAPI 记录和搜索键
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: caa7b7f3-a5a1-4f07-98c9-22652ecd5d21
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4aa641ad0a41ff8015d2ece717d5a4cb3a7c4edf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587311"
---
# <a name="mapi-record-and-search-keys"></a><span data-ttu-id="0d01b-103">MAPI 记录和搜索键</span><span class="sxs-lookup"><span data-stu-id="0d01b-103">MAPI Record and Search Keys</span></span>

  
  
<span data-ttu-id="0d01b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d01b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d01b-105">记录的键和搜索键是分配给多个 MAPI 对象的二进制标识符。</span><span class="sxs-lookup"><span data-stu-id="0d01b-105">Record keys and search keys are binary identifiers that are assigned to many MAPI objects.</span></span> <span data-ttu-id="0d01b-106">与对象的项标识符，其记录或搜索键直接是相当以及可传送。</span><span class="sxs-lookup"><span data-stu-id="0d01b-106">Unlike an object's entry identifier, its record or search key is directly comparable as well as transmittable.</span></span> 
  
## <a name="record-keys"></a><span data-ttu-id="0d01b-107">记录的键</span><span class="sxs-lookup"><span data-stu-id="0d01b-107">Record Keys</span></span>

<span data-ttu-id="0d01b-108">记录项用于比较两个对象。</span><span class="sxs-lookup"><span data-stu-id="0d01b-108">A record key is used to compare two objects.</span></span> <span data-ttu-id="0d01b-109">消息存储和地址簿对象都必须具有记录键，存储在其**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0d01b-109">Message store and address book objects must have record keys, which are stored in their **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property.</span></span> <span data-ttu-id="0d01b-110">由于记录密钥标识对象而不是其数据，每个对象的实例具有唯一的记录关键字。</span><span class="sxs-lookup"><span data-stu-id="0d01b-110">Because a record key identifies an object and not its data, every instance of an object has a unique record key.</span></span> <span data-ttu-id="0d01b-111">消息存储库文件夹和邮件的记录密钥的范围。</span><span class="sxs-lookup"><span data-stu-id="0d01b-111">The scope of a record key for folders and messages is the message store.</span></span> <span data-ttu-id="0d01b-112">通讯簿容器、 邮件用户和通讯组列表的范围是一套集成的通讯簿中用于提供 MAPI 的顶级容器。</span><span class="sxs-lookup"><span data-stu-id="0d01b-112">The scope for address book containers, messaging users, and distribution lists is the set of top-level containers provided by MAPI for use in the integrated address book.</span></span>
  
<span data-ttu-id="0d01b-113">可以在其他资源中复制记录的键。</span><span class="sxs-lookup"><span data-stu-id="0d01b-113">Record keys can be duplicated in another resource.</span></span> <span data-ttu-id="0d01b-114">例如，两个不同的消息存储中的不同消息可以具有相同记录键。</span><span class="sxs-lookup"><span data-stu-id="0d01b-114">For example, different messages in two different message stores can have the same record key.</span></span> <span data-ttu-id="0d01b-115">这一点不同于长期条目标识符;长期条目标识符包含服务提供程序的引用，因为具有更大范围。</span><span class="sxs-lookup"><span data-stu-id="0d01b-115">This is different from long-term entry identifiers; because long-term entry identifiers contain a reference to the service provider, they have a wider scope.</span></span> <span data-ttu-id="0d01b-116">消息存储记录键处于类似范围为长期条目标识符;它应是唯一的跨所有消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="0d01b-116">A message store's record key is similar in scope to a long-term entry identifier; it should be unique across all message store providers.</span></span> <span data-ttu-id="0d01b-117">若要确保此唯一性，消息存储提供程序通常将其记录项设置为一个值，则它们**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 的属性和消息存储对是唯一的标识符的组合。</span><span class="sxs-lookup"><span data-stu-id="0d01b-117">To ensure this uniqueness, message store providers typically set their record key to a value that is the combination of their **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property and an identifier that is unique to the message store.</span></span>
  
## <a name="search-keys"></a><span data-ttu-id="0d01b-118">搜索键</span><span class="sxs-lookup"><span data-stu-id="0d01b-118">Search Keys</span></span>

<span data-ttu-id="0d01b-119">搜索关键字用于比较两个对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="0d01b-119">A search key is used to compare the data in two objects.</span></span> <span data-ttu-id="0d01b-120">对象的搜索关键字都存储在其**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0d01b-120">An object's search key is stored in its **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property.</span></span> <span data-ttu-id="0d01b-121">由于搜索键表示对象的数据和对象本身，使用相同的数据的两个不同对象可以具有相同的搜索键。</span><span class="sxs-lookup"><span data-stu-id="0d01b-121">Because a search key represents an object's data and not the object itself, two different objects with the same data can have the same search key.</span></span> <span data-ttu-id="0d01b-122">复制对象时，例如原始对象和其副本具有相同的数据和相同的搜索键。</span><span class="sxs-lookup"><span data-stu-id="0d01b-122">When an object is copied, for example, both the original object and its copy have the same data and the same search key.</span></span>
  
<span data-ttu-id="0d01b-123">邮件和消息的用户具有搜索键。</span><span class="sxs-lookup"><span data-stu-id="0d01b-123">Messages and messaging users have search keys.</span></span> <span data-ttu-id="0d01b-124">搜索关键字消息的消息的数据的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0d01b-124">The search key of a message is a unique identifier of the message's data.</span></span> <span data-ttu-id="0d01b-125">创建邮件时，消息存储提供程序提供了一条消息**PR_SEARCH_KEY**属性。</span><span class="sxs-lookup"><span data-stu-id="0d01b-125">Message store providers furnish a message's **PR_SEARCH_KEY** property at message creation time.</span></span> <span data-ttu-id="0d01b-126">通讯簿条目的搜索项从其地址类型 (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))) 和地址 (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))) 计算。</span><span class="sxs-lookup"><span data-stu-id="0d01b-126">The search key of an address book entry is computed from its address type (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))) and address (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))).</span></span> <span data-ttu-id="0d01b-127">如果写通讯簿条目，其搜索键可能不可用，直到的地址类型和地址已设置通过使用[IMAPIProp::SetProps](imapiprop-setprops.md)方法，并使用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法已保存了该条目。</span><span class="sxs-lookup"><span data-stu-id="0d01b-127">If the address book entry is writeable, its search key might not be available until the address type and address have been set by using the [IMAPIProp::SetProps](imapiprop-setprops.md) method and the entry has been saved by using the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="0d01b-128">这些地址属性更改时，可能为相应的搜索关键字，无法使用**SaveChanges**呼叫提交更改之前与新的值进行同步。</span><span class="sxs-lookup"><span data-stu-id="0d01b-128">When these address properties change, it is possible for the corresponding search key not to be synchronized with the new values until the changes have been committed with a **SaveChanges** call.</span></span> 
  
<span data-ttu-id="0d01b-129">对象的记录项的值可以是相同或不同于其搜索关键字，具体取决于服务提供商的值。</span><span class="sxs-lookup"><span data-stu-id="0d01b-129">The value of an object's record key can be the same as or different than the value of its search key, depending on the service provider.</span></span> <span data-ttu-id="0d01b-130">某些服务提供商对象的搜索关键字、 记录键和项标识符使用相同的值。</span><span class="sxs-lookup"><span data-stu-id="0d01b-130">Some service providers use the same value for an object's search key, record key, and entry identifier.</span></span> <span data-ttu-id="0d01b-131">其他服务提供程序分配其对象的标识符的每个唯一值。</span><span class="sxs-lookup"><span data-stu-id="0d01b-131">Other service providers assign unique values for each of its objects' identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0d01b-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d01b-132">See also</span></span>



[<span data-ttu-id="0d01b-133">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="0d01b-133">MAPI Application Development</span></span>](mapi-application-development.md)

