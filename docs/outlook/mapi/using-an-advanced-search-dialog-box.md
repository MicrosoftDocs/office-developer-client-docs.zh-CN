---
title: 使用“高级搜索”对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9a156e6-3472-4409-a4ba-3a1a65b7bdcd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3c27b859f6d056d3b9a98bd4d71db8e500dff696
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779070"
---
# <a name="using-an-advanced-search-dialog-box"></a><span data-ttu-id="28b02-103">使用“高级搜索”对话框</span><span class="sxs-lookup"><span data-stu-id="28b02-103">Using an Advanced Search Dialog Box</span></span>

  
  
<span data-ttu-id="28b02-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="28b02-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="28b02-105">一些地址簿容器支持高级搜索功能，允许客户端搜索之外**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性。</span><span class="sxs-lookup"><span data-stu-id="28b02-105">Some address book containers support an advanced searching capability that allows clients to search on properties other than **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span> <span data-ttu-id="28b02-106">支持高级的搜索的通讯簿容器具有名为**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 的容器对象属性。</span><span class="sxs-lookup"><span data-stu-id="28b02-106">Address book containers that support advanced searches have a container object property called **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)).</span></span> <span data-ttu-id="28b02-107">此容器对象提供对介绍搜索对话框中显示表访问 — 用于输入和编辑高级的搜索条件的对话框。</span><span class="sxs-lookup"><span data-stu-id="28b02-107">This container object provides access to a display table that describes the search dialog box — a dialog box used to enter and edit the advanced search criteria.</span></span>
  
 <span data-ttu-id="28b02-108">**对通讯簿容器执行高级的搜索**</span><span class="sxs-lookup"><span data-stu-id="28b02-108">**To perform an advanced search on an address book container**</span></span>
  
1. <span data-ttu-id="28b02-109">调用容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，指定**PR_SEARCH**属性标记和 IID_IMAPIContainer 接口标识符。</span><span class="sxs-lookup"><span data-stu-id="28b02-109">Call the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, specifying **PR_SEARCH** for the property tag and IID_IMAPIContainer for the interface identifier.</span></span> 
    
2. <span data-ttu-id="28b02-110">调用 search 对象的**IMAPIProp::OpenProperty**方法，该接口的标识符的属性标记和 IID_IMAPITable 指定**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="28b02-110">Call the search object 's **IMAPIProp::OpenProperty** method, specifying **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) for the property tag and IID_IMAPITable for the interface identifier.</span></span> 
    
3. <span data-ttu-id="28b02-111">调用 search 对象的[IMAPIProp::SetProps](imapiprop-setprops.md)方法来建立在高级搜索中使用的属性值。</span><span class="sxs-lookup"><span data-stu-id="28b02-111">Call the search object's [IMAPIProp::SetProps](imapiprop-setprops.md) method to establish values for the properties to be used in the advanced search.</span></span> 
    
4. <span data-ttu-id="28b02-112">调用 search 对象的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，以保存高级的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="28b02-112">Call the search object's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save the advanced search criteria.</span></span> 
    
<span data-ttu-id="28b02-113">调用此顺序将导致时搜索对象的**GetSearchCriteria**方法在客户端调用的限制。</span><span class="sxs-lookup"><span data-stu-id="28b02-113">This sequence of calls results in a restriction being available when a client calls the search object's **GetSearchCriteria** method.</span></span> 
  

