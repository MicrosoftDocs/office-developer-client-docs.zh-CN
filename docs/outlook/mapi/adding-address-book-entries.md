---
title: 添加通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63444a65-d56a-4dbd-9aa6-e60f18ba8104
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d5b2aa2830e2721b9f895b22df12c9d712188625
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590132"
---
# <a name="adding-address-book-entries"></a><span data-ttu-id="edd5c-103">添加通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="edd5c-103">Adding Address Book Entries</span></span>

  
  
<span data-ttu-id="edd5c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="edd5c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="edd5c-105">将邮件用户或通讯组列表添加到容器、 客户端调用[IAddrBook::NewEntry](iaddrbook-newentry.md)或提供商呼叫与目标容器_lpEIDContainer_参数中的项标识符[IMAPISupport::NewEntry](imapisupport-newentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="edd5c-105">To add a messaging user or distribution list to a container, a client calls [IAddrBook::NewEntry](iaddrbook-newentry.md) or a provider calls [IMAPISupport::NewEntry](imapisupport-newentry.md) with the entry identifier of the target container in the  _lpEIDContainer_ parameter.</span></span> <span data-ttu-id="edd5c-106">MAPI 轮流调用容器的[IABContainer::CreateEntry](iabcontainer-createentry.md)方法来创建使用一次性模板一次性表中的条目。</span><span class="sxs-lookup"><span data-stu-id="edd5c-106">MAPI in turn calls the container's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create the entry using a one-off template from a one-off table.</span></span> <span data-ttu-id="edd5c-107">一个一次性模板允许客户端创建特定类型的一个新收件人。</span><span class="sxs-lookup"><span data-stu-id="edd5c-107">A one-off template allows the client to create a new recipient of a particular type.</span></span> <span data-ttu-id="edd5c-108">大部分字段是可编辑。</span><span class="sxs-lookup"><span data-stu-id="edd5c-108">Most of the fields are editable.</span></span> <span data-ttu-id="edd5c-109">_LpEntryID_参数指向该模板可能的您的提供商提供，或者如果您的提供商支持外的模板，可能从一个外的提供程序，模板。</span><span class="sxs-lookup"><span data-stu-id="edd5c-109">The template pointed to by the  _lpEntryID_ parameter might be one that your provider supplies or it might be a template from a foreign provider, if your provider supports foreign templates.</span></span> <span data-ttu-id="edd5c-110">可以从外部模板创建收件人的提供程序实现的**CreateEntry**通常更多的提供程序不能实现比复杂。</span><span class="sxs-lookup"><span data-stu-id="edd5c-110">Implementations of **CreateEntry** for providers that can create recipients from a foreign template are always more complex than implementations for providers that cannot.</span></span> 
  
 <span data-ttu-id="edd5c-111">**若要实现 IABContainer::CreateEntry**</span><span class="sxs-lookup"><span data-stu-id="edd5c-111">**To implement IABContainer::CreateEntry**</span></span>
  
1. <span data-ttu-id="edd5c-112">确定_lpEntryID_参数指定的项标识符的类型。</span><span class="sxs-lookup"><span data-stu-id="edd5c-112">Determine the type of entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
2. <span data-ttu-id="edd5c-113">如果条目标识符代表消息的用户、 通讯组列表或您的提供商所拥有的通讯簿容器的模板：</span><span class="sxs-lookup"><span data-stu-id="edd5c-113">If the entry identifier represents a template for a messaging user, distribution list, or address book container owned by your provider:</span></span>
    
1. <span data-ttu-id="edd5c-114">创建并初始化适当的对象。</span><span class="sxs-lookup"><span data-stu-id="edd5c-114">Create and initialize the appropriate object.</span></span> <span data-ttu-id="edd5c-115">如果需要，您的提供商可以设置一些初始属性。</span><span class="sxs-lookup"><span data-stu-id="edd5c-115">Your provider can set some initial properties if desired.</span></span> <span data-ttu-id="edd5c-116">这些属性取决于要创建的收件人的类型。</span><span class="sxs-lookup"><span data-stu-id="edd5c-116">These properties depend on the type of recipient being created.</span></span> 
    
2. <span data-ttu-id="edd5c-117">返回一个指针_lppMAPIPropEntry_参数的内容中的对象的实现。</span><span class="sxs-lookup"><span data-stu-id="edd5c-117">Return a pointer to the object's implementation in the contents of the  _lppMAPIPropEntry_ parameter.</span></span> 
    
3. <span data-ttu-id="edd5c-118">如果条目标识符表示外的提供程序的模板：</span><span class="sxs-lookup"><span data-stu-id="edd5c-118">If the entry identifier represents a template for a foreign provider:</span></span>
    
1. <span data-ttu-id="edd5c-119">调用[IMAPISupport::OpenEntry](imapisupport-openentry.md)打开外的对象。</span><span class="sxs-lookup"><span data-stu-id="edd5c-119">Call [IMAPISupport::OpenEntry](imapisupport-openentry.md) to open the foreign object.</span></span> 
    
2. <span data-ttu-id="edd5c-120">调用对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法，传递 NULL 属性标记数组，若要检索其属性。</span><span class="sxs-lookup"><span data-stu-id="edd5c-120">Call the object's [IMAPIProp::GetProps](imapiprop-getprops.md) method, passing NULL for the property tag array, to retrieve its properties.</span></span> 
    
3. <span data-ttu-id="edd5c-121">编辑从**GetProps**通过更改属性标记为 PR_NULL 将不应用于新的对象并不会传输的所有属性返回的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="edd5c-121">Edit the property value array returned from **GetProps** by changing the property tag to PR_NULL for all properties that will not apply to the new object and should not be transferred.</span></span> 
    
4. <span data-ttu-id="edd5c-122">创建新的对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="edd5c-122">Create an entry identifier for the new object.</span></span> 
    
5. <span data-ttu-id="edd5c-123">创建相应的新的对象类型，或者是消息的用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="edd5c-123">Create a new object of the appropriate type, either messaging user or distribution list.</span></span>
    
6. <span data-ttu-id="edd5c-124">初始化新对象，通过设置默认属性。</span><span class="sxs-lookup"><span data-stu-id="edd5c-124">Initialize the new object by setting default properties.</span></span>
    
7. <span data-ttu-id="edd5c-125">检查外来对象支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="edd5c-125">Check whether or not the foreign object supports the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> 
    
8. <span data-ttu-id="edd5c-126">如果外来对象支持**PR_TEMPLATEID**，呼叫[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)外的提供程序检索属性对象接口，并将_lppMAPIPropEntry_参数的内容设置为 foreign 属性对象实现。</span><span class="sxs-lookup"><span data-stu-id="edd5c-126">If the foreign object supports **PR_TEMPLATEID**, call [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) to retrieve a property object interface from the foreign provider and set the contents of the  _lppMAPIPropEntry_ parameter to the foreign property object implementation.</span></span> 
    
9. <span data-ttu-id="edd5c-127">如果外来对象不支持**PR_TEMPLATEID**，设置为新的对象的提供程序的实现_lppMAPIPropEntry_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="edd5c-127">If the foreign object does not support **PR_TEMPLATEID**, set the contents of the  _lppMAPIPropEntry_ parameter to your provider's implementation of the new object.</span></span> 
    
10. <span data-ttu-id="edd5c-128">调用指向_lppMAPIPropEntry_参数从外来对象设置的相应属性的对象的[IMAPIProp::SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="edd5c-128">Call the [IMAPIProp::SetProps](imapiprop-setprops.md) method of the object pointed to by the  _lppMAPIPropEntry_ parameter to set the appropriate properties from the foreign object.</span></span> 
    

