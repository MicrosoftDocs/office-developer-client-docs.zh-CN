---
title: 设置通讯簿选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9bd31233-fc8d-4e0a-9f1b-218c5ecb6d1b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f72c916e917543b11089f8f5ef1aa4b9552a1b6a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351406"
---
# <a name="setting-address-book-options"></a><span data-ttu-id="3d293-103">设置通讯簿选项</span><span class="sxs-lookup"><span data-stu-id="3d293-103">Setting Address Book Options</span></span>

  
  
<span data-ttu-id="3d293-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3d293-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3d293-105">您可以设置三个属性来描述使用通讯簿的选项:</span><span class="sxs-lookup"><span data-stu-id="3d293-105">You can set three properties that describe options for using the address book:</span></span>
  
- <span data-ttu-id="3d293-106">**PR_AB_SEARCH_PATH**([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3d293-106">**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))</span></span>
    
    <span data-ttu-id="3d293-107">[IAddrBook:: ResolveName](iaddrbook-resolvename.md)使用**PR_AB_SEARCH_PATH**属性来确定要加入名称解析的容器以及应涉及的顺序。</span><span class="sxs-lookup"><span data-stu-id="3d293-107">The **PR_AB_SEARCH_PATH** property is used by [IAddrBook::ResolveName](iaddrbook-resolvename.md) to determine the containers to be involved in name resolution and the order that they should be involved.</span></span> <span data-ttu-id="3d293-108">对于**PR_AB_SEARCH_PATH**中的每个容器, **IAddrBook:: ResolveName**调用其[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3d293-108">For each container in **PR_AB_SEARCH_PATH**, **IAddrBook::ResolveName** calls its [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method.</span></span> <span data-ttu-id="3d293-109">在**PR_AB_SEARCH_PATH**开头的容器中搜索位于**PR_AB_SEARCH_PATH**末尾的容器。</span><span class="sxs-lookup"><span data-stu-id="3d293-109">Containers at the beginning of **PR_AB_SEARCH_PATH** are searched before containers at the end of **PR_AB_SEARCH_PATH**.</span></span> 
    
    <span data-ttu-id="3d293-110">**PR_AB_SEARCH_PATH**中的搜索顺序是使用[SRowSet](srowset.md)结构指定的, 这是用于表示表中的行的相同结构。</span><span class="sxs-lookup"><span data-stu-id="3d293-110">The search order in **PR_AB_SEARCH_PATH** is specified using an [SRowSet](srowset.md) structure, the same structure that is used to represent rows in a table.</span></span> <span data-ttu-id="3d293-111">您可以通过调用[IAddrBook:: GetSearchPath](iaddrbook-getsearchpath.md)方法并通过调用[IAddrBook:: SetSearchPath](iaddrbook-setsearchpath.md)方法来更改当前搜索路径, 从而查看该路径。</span><span class="sxs-lookup"><span data-stu-id="3d293-111">You can view the current search path by calling the [IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md) method and change it by calling the [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md) method.</span></span> 
    
- <span data-ttu-id="3d293-112">**PR_AB_DEFAULT_DIR**([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3d293-112">**PR_AB_DEFAULT_DIR** ([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))</span></span>
    
    <span data-ttu-id="3d293-113">**PR_AB_DEFAULT_DIR**属性是在显示通讯簿时最初显示的通讯簿容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3d293-113">The **PR_AB_DEFAULT_DIR** property is the entry identifier of the address book container to be displayed initially when the address book is displayed.</span></span> <span data-ttu-id="3d293-114">默认目录设置将一直保持有效, 直到您通过调用[IAddrBook:: SetDefaultDir](iaddrbook-setdefaultdir.md)方法对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="3d293-114">The default directory setting remains in effect until you change it by calling the [IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md) method.</span></span> <span data-ttu-id="3d293-115">您可以通过调用[IAddrBook:: GetDefaultDir](iaddrbook-getdefaultdir.md)方法来查看默认目录。</span><span class="sxs-lookup"><span data-stu-id="3d293-115">You can view the default directory by calling the [IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md) method.</span></span> 
    
- <span data-ttu-id="3d293-116">**PR_AB_DEFAULT_PAB**([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3d293-116">**PR_AB_DEFAULT_PAB** ([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))</span></span>
    
<span data-ttu-id="3d293-117">这三个属性是特殊的, 因为您无法使用标准的**IMAPIProp**方法来处理它们。</span><span class="sxs-lookup"><span data-stu-id="3d293-117">These three properties are special because you cannot work with them using the standard **IMAPIProp** methods.</span></span> <span data-ttu-id="3d293-118">相反, 您必须使用**IAddrBook**方法。</span><span class="sxs-lookup"><span data-stu-id="3d293-118">Instead, you must use **IAddrBook** methods.</span></span> <span data-ttu-id="3d293-119">由于无法使用**IMAPIProp:: SetProps**更改这些属性中的任何一个, 因此无需调用**IMAPIProp:: SaveChanges**以使更改永久生效。</span><span class="sxs-lookup"><span data-stu-id="3d293-119">Because none of these properties can be changed with **IMAPIProp::SetProps**, there is no need to call **IMAPIProp::SaveChanges** to make changes permanent.</span></span> <span data-ttu-id="3d293-120">通过**IAddrBook**方法所做的修改会立即生效。</span><span class="sxs-lookup"><span data-stu-id="3d293-120">Modifications made through the **IAddrBook** methods take effect immediately.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3d293-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d293-121">See also</span></span>



[<span data-ttu-id="3d293-122">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="3d293-122">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

