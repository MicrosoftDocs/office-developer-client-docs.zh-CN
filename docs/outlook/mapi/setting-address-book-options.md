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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417341"
---
# <a name="setting-address-book-options"></a><span data-ttu-id="3bf9e-103">设置通讯簿选项</span><span class="sxs-lookup"><span data-stu-id="3bf9e-103">Setting Address Book Options</span></span>

  
  
<span data-ttu-id="3bf9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3bf9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3bf9e-105">您可以设置三个描述通讯簿使用选项的属性：</span><span class="sxs-lookup"><span data-stu-id="3bf9e-105">You can set three properties that describe options for using the address book:</span></span>
  
- <span data-ttu-id="3bf9e-106">**PR_AB_SEARCH_PATH (** [PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="3bf9e-106">**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))</span></span>
    
    <span data-ttu-id="3bf9e-107">[IAddrBook：：ResolveName](iaddrbook-resolvename.md)使用 **PR_AB_SEARCH_PATH** 属性来确定名称解析中涉及的容器及其参与顺序。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-107">The **PR_AB_SEARCH_PATH** property is used by [IAddrBook::ResolveName](iaddrbook-resolvename.md) to determine the containers to be involved in name resolution and the order that they should be involved.</span></span> <span data-ttu-id="3bf9e-108">对于每个容器 **，PR_AB_SEARCH_PATH IAddrBook：：ResolveName** 调用其 [IABContainer：：ResolveNames](iabcontainer-resolvenames.md)方法。 </span><span class="sxs-lookup"><span data-stu-id="3bf9e-108">For each container in **PR_AB_SEARCH_PATH**, **IAddrBook::ResolveName** calls its [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method.</span></span> <span data-ttu-id="3bf9e-109">在容器末尾 **PR_AB_SEARCH_PATH** 在容器之前搜索位于 **PR_AB_SEARCH_PATH。**</span><span class="sxs-lookup"><span data-stu-id="3bf9e-109">Containers at the beginning of **PR_AB_SEARCH_PATH** are searched before containers at the end of **PR_AB_SEARCH_PATH**.</span></span> 
    
    <span data-ttu-id="3bf9e-110">使用 [SRowSet](srowset.md) **PR_AB_SEARCH_PATH** 指定搜索顺序，该结构与用于表示表格中的行的结构相同。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-110">The search order in **PR_AB_SEARCH_PATH** is specified using an [SRowSet](srowset.md) structure, the same structure that is used to represent rows in a table.</span></span> <span data-ttu-id="3bf9e-111">可以通过调用 [IAddrBook：：GetSearchPath](iaddrbook-getsearchpath.md) 方法查看当前搜索路径，然后通过调用 [IAddrBook：：SetSearchPath](iaddrbook-setsearchpath.md) 方法更改它。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-111">You can view the current search path by calling the [IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md) method and change it by calling the [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md) method.</span></span> 
    
- <span data-ttu-id="3bf9e-112">**PR_AB_DEFAULT_DIR (** [PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="3bf9e-112">**PR_AB_DEFAULT_DIR** ([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))</span></span>
    
    <span data-ttu-id="3bf9e-113">the **PR_AB_DEFAULT_DIR** property is the entry identifier of the address book container to be displayed initially when the address book is displayed.</span><span class="sxs-lookup"><span data-stu-id="3bf9e-113">The **PR_AB_DEFAULT_DIR** property is the entry identifier of the address book container to be displayed initially when the address book is displayed.</span></span> <span data-ttu-id="3bf9e-114">默认目录设置将一直有效，直到通过调用 [IAddrBook：：SetDefaultDir](iaddrbook-setdefaultdir.md) 方法更改它。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-114">The default directory setting remains in effect until you change it by calling the [IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md) method.</span></span> <span data-ttu-id="3bf9e-115">可以通过调用 [IAddrBook：：GetDefaultDir 方法来查看默认](iaddrbook-getdefaultdir.md) 目录。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-115">You can view the default directory by calling the [IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md) method.</span></span> 
    
- <span data-ttu-id="3bf9e-116">**PR_AB_DEFAULT_PAB (** [PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="3bf9e-116">**PR_AB_DEFAULT_PAB** ([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))</span></span>
    
<span data-ttu-id="3bf9e-117">这三个属性很特殊，因为您无法使用标准 **IMAPIProp** 方法使用它们。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-117">These three properties are special because you cannot work with them using the standard **IMAPIProp** methods.</span></span> <span data-ttu-id="3bf9e-118">相反，必须使用 **IAddrBook** 方法。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-118">Instead, you must use **IAddrBook** methods.</span></span> <span data-ttu-id="3bf9e-119">由于这些属性都不是使用 **IMAPIProp：：SetProps** 更改的，因此无需调用 **IMAPIProp：：SaveChanges** 来永久进行更改。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-119">Because none of these properties can be changed with **IMAPIProp::SetProps**, there is no need to call **IMAPIProp::SaveChanges** to make changes permanent.</span></span> <span data-ttu-id="3bf9e-120">通过 **IAddrBook** 方法所做的修改会立即生效。</span><span class="sxs-lookup"><span data-stu-id="3bf9e-120">Modifications made through the **IAddrBook** methods take effect immediately.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3bf9e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bf9e-121">See also</span></span>



[<span data-ttu-id="3bf9e-122">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="3bf9e-122">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

