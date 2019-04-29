---
title: 使用 "高级搜索" 对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9a156e6-3472-4409-a4ba-3a1a65b7bdcd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 70b62eeaf6e737747c98b3abcd6e7053f71d4308
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437299"
---
# <a name="using-an-advanced-search-dialog-box"></a><span data-ttu-id="c5a87-103">使用 "高级搜索" 对话框</span><span class="sxs-lookup"><span data-stu-id="c5a87-103">Using an Advanced Search Dialog Box</span></span>

  
  
<span data-ttu-id="c5a87-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c5a87-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c5a87-105">某些通讯簿容器支持高级搜索功能, 使客户端可以搜索除**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 以外的属性。</span><span class="sxs-lookup"><span data-stu-id="c5a87-105">Some address book containers support an advanced searching capability that allows clients to search on properties other than **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span> <span data-ttu-id="c5a87-106">支持高级搜索的通讯簿容器具有一个名为**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 的容器对象属性。</span><span class="sxs-lookup"><span data-stu-id="c5a87-106">Address book containers that support advanced searches have a container object property called **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)).</span></span> <span data-ttu-id="c5a87-107">此容器对象提供对描述 "搜索" 对话框 (用于输入和编辑高级搜索条件的对话框) 的显示表的访问。</span><span class="sxs-lookup"><span data-stu-id="c5a87-107">This container object provides access to a display table that describes the search dialog box — a dialog box used to enter and edit the advanced search criteria.</span></span>
  
 <span data-ttu-id="c5a87-108">**对通讯簿容器执行高级搜索**</span><span class="sxs-lookup"><span data-stu-id="c5a87-108">**To perform an advanced search on an address book container**</span></span>
  
1. <span data-ttu-id="c5a87-109">调用容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 并为该接口标识符指定属性标记和 IID_IMAPIContainer 的**PR_SEARCH** 。</span><span class="sxs-lookup"><span data-stu-id="c5a87-109">Call the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, specifying **PR_SEARCH** for the property tag and IID_IMAPIContainer for the interface identifier.</span></span> 
    
2. <span data-ttu-id="c5a87-110">调用 search 对象的**IMAPIProp:: OpenProperty**方法, 为该接口标识符指定属性标记和 IID_IMAPITable 的**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="c5a87-110">Call the search object 's **IMAPIProp::OpenProperty** method, specifying **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) for the property tag and IID_IMAPITable for the interface identifier.</span></span> 
    
3. <span data-ttu-id="c5a87-111">调用 search 对象的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以建立要在高级搜索中使用的属性的值。</span><span class="sxs-lookup"><span data-stu-id="c5a87-111">Call the search object's [IMAPIProp::SetProps](imapiprop-setprops.md) method to establish values for the properties to be used in the advanced search.</span></span> 
    
4. <span data-ttu-id="c5a87-112">调用搜索对象的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存高级搜索条件。</span><span class="sxs-lookup"><span data-stu-id="c5a87-112">Call the search object's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save the advanced search criteria.</span></span> 
    
<span data-ttu-id="c5a87-113">当客户端调用搜索对象的**GetSearchCriteria**方法时, 此调用序列将导致限制可用。</span><span class="sxs-lookup"><span data-stu-id="c5a87-113">This sequence of calls results in a restriction being available when a client calls the search object's **GetSearchCriteria** method.</span></span> 
  

