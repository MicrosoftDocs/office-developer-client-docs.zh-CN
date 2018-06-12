---
title: 设置通讯簿选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9bd31233-fc8d-4e0a-9f1b-218c5ecb6d1b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c64f84da6bece809176bf67985b6f55ce92414a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778758"
---
# <a name="setting-address-book-options"></a><span data-ttu-id="8aad1-103">设置通讯簿选项</span><span class="sxs-lookup"><span data-stu-id="8aad1-103">Setting Address Book Options</span></span>

  
  
<span data-ttu-id="8aad1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8aad1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8aad1-105">您可以设置介绍了使用通讯簿选项的三个属性：</span><span class="sxs-lookup"><span data-stu-id="8aad1-105">You can set three properties that describe options for using the address book:</span></span>
  
- <span data-ttu-id="8aad1-106">**PR_AB_SEARCH_PATH**([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8aad1-106">**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))</span></span>
    
    <span data-ttu-id="8aad1-107">**PR_AB_SEARCH_PATH**属性是[IAddrBook::ResolveName](iaddrbook-resolvename.md)用于确定要名称解析和应所涉及的顺序中所涉及的容器。</span><span class="sxs-lookup"><span data-stu-id="8aad1-107">The **PR_AB_SEARCH_PATH** property is used by [IAddrBook::ResolveName](iaddrbook-resolvename.md) to determine the containers to be involved in name resolution and the order that they should be involved.</span></span> <span data-ttu-id="8aad1-108">对于每个容器中**PR_AB_SEARCH_PATH**， **IAddrBook::ResolveName**调用其[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8aad1-108">For each container in **PR_AB_SEARCH_PATH**, **IAddrBook::ResolveName** calls its [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method.</span></span> <span data-ttu-id="8aad1-109">之前的**PR_AB_SEARCH_PATH**末尾的容器搜索**PR_AB_SEARCH_PATH**开头的容器。</span><span class="sxs-lookup"><span data-stu-id="8aad1-109">Containers at the beginning of **PR_AB_SEARCH_PATH** are searched before containers at the end of **PR_AB_SEARCH_PATH**.</span></span> 
    
    <span data-ttu-id="8aad1-110">使用[SRowSet](srowset.md)结构，用于表示表中的行的相同结构指定**PR_AB_SEARCH_PATH**中的搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="8aad1-110">The search order in **PR_AB_SEARCH_PATH** is specified using an [SRowSet](srowset.md) structure, the same structure that is used to represent rows in a table.</span></span> <span data-ttu-id="8aad1-111">您可以通过调用[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)方法查看当前的搜索路径，并更改通过调用[IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8aad1-111">You can view the current search path by calling the [IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md) method and change it by calling the [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md) method.</span></span> 
    
- <span data-ttu-id="8aad1-112">**PR_AB_DEFAULT_DIR**([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8aad1-112">**PR_AB_DEFAULT_DIR** ([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))</span></span>
    
    <span data-ttu-id="8aad1-113">**PR_AB_DEFAULT_DIR**属性是通讯簿容器，以显示通讯簿时最初显示的项标识符。</span><span class="sxs-lookup"><span data-stu-id="8aad1-113">The **PR_AB_DEFAULT_DIR** property is the entry identifier of the address book container to be displayed initially when the address book is displayed.</span></span> <span data-ttu-id="8aad1-114">默认目录设置保持有效，直到您更改通过调用[IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8aad1-114">The default directory setting remains in effect until you change it by calling the [IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md) method.</span></span> <span data-ttu-id="8aad1-115">您可以通过调用[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)方法来查看默认目录。</span><span class="sxs-lookup"><span data-stu-id="8aad1-115">You can view the default directory by calling the [IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md) method.</span></span> 
    
- <span data-ttu-id="8aad1-116">**PR_AB_DEFAULT_PAB**([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8aad1-116">**PR_AB_DEFAULT_PAB** ([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))</span></span>
    
<span data-ttu-id="8aad1-117">这三个属性是特殊的因为您无法使用它们使用标准**IMAPIProp**方法。</span><span class="sxs-lookup"><span data-stu-id="8aad1-117">These three properties are special because you cannot work with them using the standard **IMAPIProp** methods.</span></span> <span data-ttu-id="8aad1-118">相反，您必须使用**IAddrBook**方法。</span><span class="sxs-lookup"><span data-stu-id="8aad1-118">Instead, you must use **IAddrBook** methods.</span></span> <span data-ttu-id="8aad1-119">因为无这些属性可与**IMAPIProp::SetProps**更改，则无需调用**IMAPIProp::SaveChanges**进行永久更改。</span><span class="sxs-lookup"><span data-stu-id="8aad1-119">Because none of these properties can be changed with **IMAPIProp::SetProps**, there is no need to call **IMAPIProp::SaveChanges** to make changes permanent.</span></span> <span data-ttu-id="8aad1-120">通过**IAddrBook**方法所做的更改立即生效。</span><span class="sxs-lookup"><span data-stu-id="8aad1-120">Modifications made through the **IAddrBook** methods take effect immediately.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8aad1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8aad1-121">See also</span></span>



[<span data-ttu-id="8aad1-122">IAddrBook: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8aad1-122">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

