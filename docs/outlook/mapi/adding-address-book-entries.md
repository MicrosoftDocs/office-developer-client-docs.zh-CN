---
title: 添加通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63444a65-d56a-4dbd-9aa6-e60f18ba8104
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8dc82a99ee088d42c076ca9a3a75eac6553f7d35
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421338"
---
# <a name="adding-address-book-entries"></a><span data-ttu-id="3e160-103">添加通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="3e160-103">Adding Address Book Entries</span></span>

  
  
<span data-ttu-id="3e160-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e160-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e160-105">若要向容器中添加邮件用户或通讯组列表, 客户端调用[IAddrBook:: NewEntry](iaddrbook-newentry.md)或 provider 使用_lpEIDContainer_参数中的目标容器的条目标识符调用[IMAPISupport:: NewEntry](imapisupport-newentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="3e160-105">To add a messaging user or distribution list to a container, a client calls [IAddrBook::NewEntry](iaddrbook-newentry.md) or a provider calls [IMAPISupport::NewEntry](imapisupport-newentry.md) with the entry identifier of the target container in the  _lpEIDContainer_ parameter.</span></span> <span data-ttu-id="3e160-106">MAPI 反过来会调用容器的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法, 以使用一次性的一次性模板创建条目。</span><span class="sxs-lookup"><span data-stu-id="3e160-106">MAPI in turn calls the container's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create the entry using a one-off template from a one-off table.</span></span> <span data-ttu-id="3e160-107">一次性模板允许客户端创建特定类型的新收件人。</span><span class="sxs-lookup"><span data-stu-id="3e160-107">A one-off template allows the client to create a new recipient of a particular type.</span></span> <span data-ttu-id="3e160-108">大部分字段都是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="3e160-108">Most of the fields are editable.</span></span> <span data-ttu-id="3e160-109">如果您的提供程序支持外部模板, 则由_lpEntryID_参数指向的模板可能是提供程序提供的模板, 也可能是来自外部提供程序的模板。</span><span class="sxs-lookup"><span data-stu-id="3e160-109">The template pointed to by the  _lpEntryID_ parameter might be one that your provider supplies or it might be a template from a foreign provider, if your provider supports foreign templates.</span></span> <span data-ttu-id="3e160-110">可从外部模板创建收件人的提供程序的**CreateEntry**的实现通常比无法实现的提供程序更复杂。</span><span class="sxs-lookup"><span data-stu-id="3e160-110">Implementations of **CreateEntry** for providers that can create recipients from a foreign template are always more complex than implementations for providers that cannot.</span></span> 
  
 <span data-ttu-id="3e160-111">**实现 IABContainer:: CreateEntry**</span><span class="sxs-lookup"><span data-stu-id="3e160-111">**To implement IABContainer::CreateEntry**</span></span>
  
1. <span data-ttu-id="3e160-112">确定由_lpEntryID_参数指定的条目标识符的类型。</span><span class="sxs-lookup"><span data-stu-id="3e160-112">Determine the type of entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
2. <span data-ttu-id="3e160-113">如果条目标识符代表邮件用户、通讯组列表或提供商拥有的通讯簿容器的模板:</span><span class="sxs-lookup"><span data-stu-id="3e160-113">If the entry identifier represents a template for a messaging user, distribution list, or address book container owned by your provider:</span></span>
    
1. <span data-ttu-id="3e160-114">创建并初始化相应的对象。</span><span class="sxs-lookup"><span data-stu-id="3e160-114">Create and initialize the appropriate object.</span></span> <span data-ttu-id="3e160-115">提供程序可以根据需要设置一些初始属性。</span><span class="sxs-lookup"><span data-stu-id="3e160-115">Your provider can set some initial properties if desired.</span></span> <span data-ttu-id="3e160-116">这些属性取决于所创建的收件人的类型。</span><span class="sxs-lookup"><span data-stu-id="3e160-116">These properties depend on the type of recipient being created.</span></span> 
    
2. <span data-ttu-id="3e160-117">在_lppMAPIPropEntry_参数的内容中返回指向对象的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="3e160-117">Return a pointer to the object's implementation in the contents of the  _lppMAPIPropEntry_ parameter.</span></span> 
    
3. <span data-ttu-id="3e160-118">如果条目标识符表示外部提供程序的模板:</span><span class="sxs-lookup"><span data-stu-id="3e160-118">If the entry identifier represents a template for a foreign provider:</span></span>
    
1. <span data-ttu-id="3e160-119">调用[IMAPISupport:: OpenEntry](imapisupport-openentry.md)以打开外部对象。</span><span class="sxs-lookup"><span data-stu-id="3e160-119">Call [IMAPISupport::OpenEntry](imapisupport-openentry.md) to open the foreign object.</span></span> 
    
2. <span data-ttu-id="3e160-120">调用该对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法, 并为该属性标记数组传递 NULL, 以检索其属性。</span><span class="sxs-lookup"><span data-stu-id="3e160-120">Call the object's [IMAPIProp::GetProps](imapiprop-getprops.md) method, passing NULL for the property tag array, to retrieve its properties.</span></span> 
    
3. <span data-ttu-id="3e160-121">通过将不适用于新对象且不应转移的所有属性的属性标记更改为 PR_NULL, 可编辑从**GetProps**返回的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="3e160-121">Edit the property value array returned from **GetProps** by changing the property tag to PR_NULL for all properties that will not apply to the new object and should not be transferred.</span></span> 
    
4. <span data-ttu-id="3e160-122">为新对象创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3e160-122">Create an entry identifier for the new object.</span></span> 
    
5. <span data-ttu-id="3e160-123">创建一个适当类型的新对象, 即邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3e160-123">Create a new object of the appropriate type, either messaging user or distribution list.</span></span>
    
6. <span data-ttu-id="3e160-124">通过设置默认属性来初始化新对象。</span><span class="sxs-lookup"><span data-stu-id="3e160-124">Initialize the new object by setting default properties.</span></span>
    
7. <span data-ttu-id="3e160-125">检查外部对象是否支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3e160-125">Check whether or not the foreign object supports the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> 
    
8. <span data-ttu-id="3e160-126">如果外部对象支持**PR_TEMPLATEID**, 则调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)以检索来自外部提供程序的 property 对象接口, 并将_lppMAPIPropEntry_参数的内容设置为外部属性对象实现。</span><span class="sxs-lookup"><span data-stu-id="3e160-126">If the foreign object supports **PR_TEMPLATEID**, call [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) to retrieve a property object interface from the foreign provider and set the contents of the  _lppMAPIPropEntry_ parameter to the foreign property object implementation.</span></span> 
    
9. <span data-ttu-id="3e160-127">如果外部对象不支持**PR_TEMPLATEID**, 请将_lppMAPIPropEntry_参数的内容设置为提供程序的新对象实现。</span><span class="sxs-lookup"><span data-stu-id="3e160-127">If the foreign object does not support **PR_TEMPLATEID**, set the contents of the  _lppMAPIPropEntry_ parameter to your provider's implementation of the new object.</span></span> 
    
10. <span data-ttu-id="3e160-128">调用_lppMAPIPropEntry_参数指向的对象的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法, 以设置外部对象的相应属性。</span><span class="sxs-lookup"><span data-stu-id="3e160-128">Call the [IMAPIProp::SetProps](imapiprop-setprops.md) method of the object pointed to by the  _lppMAPIPropEntry_ parameter to set the appropriate properties from the foreign object.</span></span> 
    

