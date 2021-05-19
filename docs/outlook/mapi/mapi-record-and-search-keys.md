---
title: MAPI 记录和搜索键
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: caa7b7f3-a5a1-4f07-98c9-22652ecd5d21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b1b4c0087cecd9164fc96ce7c5b5415f75dbfb03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434562"
---
# <a name="mapi-record-and-search-keys"></a><span data-ttu-id="31967-103">MAPI 记录和搜索键</span><span class="sxs-lookup"><span data-stu-id="31967-103">MAPI Record and Search Keys</span></span>

  
  
<span data-ttu-id="31967-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="31967-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="31967-105">记录键和搜索键是分配给许多 MAPI 对象的二进制标识符。</span><span class="sxs-lookup"><span data-stu-id="31967-105">Record keys and search keys are binary identifiers that are assigned to many MAPI objects.</span></span> <span data-ttu-id="31967-106">与对象的条目标识符不同，其记录或搜索键可以直接比较，也可以传输。</span><span class="sxs-lookup"><span data-stu-id="31967-106">Unlike an object's entry identifier, its record or search key is directly comparable as well as transmittable.</span></span> 
  
## <a name="record-keys"></a><span data-ttu-id="31967-107">记录键</span><span class="sxs-lookup"><span data-stu-id="31967-107">Record Keys</span></span>

<span data-ttu-id="31967-108">记录键用于比较两个对象。</span><span class="sxs-lookup"><span data-stu-id="31967-108">A record key is used to compare two objects.</span></span> <span data-ttu-id="31967-109">邮件存储和通讯簿对象必须具有记录密钥，这些记录键存储在[PidTagRecordKey PR_RECORD_KEY (PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性中。 </span><span class="sxs-lookup"><span data-stu-id="31967-109">Message store and address book objects must have record keys, which are stored in their **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property.</span></span> <span data-ttu-id="31967-110">由于记录键标识对象而不是其数据，因此对象的每个实例都有一个唯一的记录键。</span><span class="sxs-lookup"><span data-stu-id="31967-110">Because a record key identifies an object and not its data, every instance of an object has a unique record key.</span></span> <span data-ttu-id="31967-111">文件夹和邮件的记录密钥的范围是邮件存储。</span><span class="sxs-lookup"><span data-stu-id="31967-111">The scope of a record key for folders and messages is the message store.</span></span> <span data-ttu-id="31967-112">通讯簿容器、邮件用户和通讯组列表的范围是 MAPI 提供的用于集成通讯簿的顶级容器集。</span><span class="sxs-lookup"><span data-stu-id="31967-112">The scope for address book containers, messaging users, and distribution lists is the set of top-level containers provided by MAPI for use in the integrated address book.</span></span>
  
<span data-ttu-id="31967-113">记录键可以在另一个资源中重复。</span><span class="sxs-lookup"><span data-stu-id="31967-113">Record keys can be duplicated in another resource.</span></span> <span data-ttu-id="31967-114">例如，两个不同邮件存储中的不同邮件可以具有相同的记录密钥。</span><span class="sxs-lookup"><span data-stu-id="31967-114">For example, different messages in two different message stores can have the same record key.</span></span> <span data-ttu-id="31967-115">这不同于长期条目标识符;因为长期条目标识符包含对服务提供商的引用，所以它们的范围更广。</span><span class="sxs-lookup"><span data-stu-id="31967-115">This is different from long-term entry identifiers; because long-term entry identifiers contain a reference to the service provider, they have a wider scope.</span></span> <span data-ttu-id="31967-116">邮件存储的记录键在作用域中类似于长期条目标识符;它应在所有邮件存储提供程序中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="31967-116">A message store's record key is similar in scope to a long-term entry identifier; it should be unique across all message store providers.</span></span> <span data-ttu-id="31967-117">为了确保这种唯一性，邮件存储提供程序通常将记录键设置为一个值，该值是 **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 属性与邮件存储唯一标识符的组合。</span><span class="sxs-lookup"><span data-stu-id="31967-117">To ensure this uniqueness, message store providers typically set their record key to a value that is the combination of their **PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) property and an identifier that is unique to the message store.</span></span>
  
## <a name="search-keys"></a><span data-ttu-id="31967-118">搜索键</span><span class="sxs-lookup"><span data-stu-id="31967-118">Search Keys</span></span>

<span data-ttu-id="31967-119">搜索键用于比较两个对象的数据。</span><span class="sxs-lookup"><span data-stu-id="31967-119">A search key is used to compare the data in two objects.</span></span> <span data-ttu-id="31967-120">对象的搜索键存储在该对象的 PR_SEARCH_KEY ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。 </span><span class="sxs-lookup"><span data-stu-id="31967-120">An object's search key is stored in its **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property.</span></span> <span data-ttu-id="31967-121">因为搜索键表示对象的数据，而不是对象本身，所以两个具有相同的数据的不同对象可以具有相同的搜索键。</span><span class="sxs-lookup"><span data-stu-id="31967-121">Because a search key represents an object's data and not the object itself, two different objects with the same data can have the same search key.</span></span> <span data-ttu-id="31967-122">例如，在复制对象时，原始对象及其副本具有相同的数据和相同的搜索键。</span><span class="sxs-lookup"><span data-stu-id="31967-122">When an object is copied, for example, both the original object and its copy have the same data and the same search key.</span></span>
  
<span data-ttu-id="31967-123">邮件和消息用户具有搜索键。</span><span class="sxs-lookup"><span data-stu-id="31967-123">Messages and messaging users have search keys.</span></span> <span data-ttu-id="31967-124">邮件的搜索键是邮件数据的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="31967-124">The search key of a message is a unique identifier of the message's data.</span></span> <span data-ttu-id="31967-125">邮件存储提供程序在邮件 **创建PR_SEARCH_KEY提供** 邮件的托管属性。</span><span class="sxs-lookup"><span data-stu-id="31967-125">Message store providers furnish a message's **PR_SEARCH_KEY** property at message creation time.</span></span> <span data-ttu-id="31967-126">通讯簿条目的搜索键从通讯簿条目的地址类型 (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) ) 和地址 (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) ) 计算。</span><span class="sxs-lookup"><span data-stu-id="31967-126">The search key of an address book entry is computed from its address type (**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))) and address (**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))).</span></span> <span data-ttu-id="31967-127">如果通讯簿条目是可写的，则除非已使用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法设置了地址类型和地址，并且已使用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法保存了该条目，所以该条目可能不可用。</span><span class="sxs-lookup"><span data-stu-id="31967-127">If the address book entry is writeable, its search key might not be available until the address type and address have been set by using the [IMAPIProp::SetProps](imapiprop-setprops.md) method and the entry has been saved by using the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="31967-128">当这些地址属性发生更改时，在通过 **SaveChanges** 调用提交更改之前，相应的搜索键可能未与新值同步。</span><span class="sxs-lookup"><span data-stu-id="31967-128">When these address properties change, it is possible for the corresponding search key not to be synchronized with the new values until the changes have been committed with a **SaveChanges** call.</span></span> 
  
<span data-ttu-id="31967-129">对象的记录键的值可以与搜索键的值相同或不同，具体取决于服务提供商。</span><span class="sxs-lookup"><span data-stu-id="31967-129">The value of an object's record key can be the same as or different than the value of its search key, depending on the service provider.</span></span> <span data-ttu-id="31967-130">某些服务提供商对对象的搜索键、记录键和条目标识符使用相同的值。</span><span class="sxs-lookup"><span data-stu-id="31967-130">Some service providers use the same value for an object's search key, record key, and entry identifier.</span></span> <span data-ttu-id="31967-131">其他服务提供商为其每个对象的标识符分配唯一值。</span><span class="sxs-lookup"><span data-stu-id="31967-131">Other service providers assign unique values for each of its objects' identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="31967-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31967-132">See also</span></span>



[<span data-ttu-id="31967-133">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="31967-133">MAPI Application Development</span></span>](mapi-application-development.md)

