---
title: 实现高级搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 08cc60d4-cac8-4ba5-bd7f-a56e63697be3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0ba9958588c476ae330b0f4a413361e80d54667a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571967"
---
# <a name="implementing-advanced-searching"></a><span data-ttu-id="37ace-103">实现高级搜索</span><span class="sxs-lookup"><span data-stu-id="37ace-103">Implementing Advanced Searching</span></span>

  
  
<span data-ttu-id="37ace-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="37ace-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="37ace-105">一些地址簿容器支持高级搜索功能，允许客户端搜索之外**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性。</span><span class="sxs-lookup"><span data-stu-id="37ace-105">Some address book containers support an advanced searching capability that allows clients to search on properties other than **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span> <span data-ttu-id="37ace-106">若要支持高级的搜索，您的提供商必须实现通过您的其他容器的**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性可访问的特殊容器。</span><span class="sxs-lookup"><span data-stu-id="37ace-106">To support advanced searches, your provider must implement a special container that is accessible through the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property of your other containers.</span></span> <span data-ttu-id="37ace-107">**PR_SEARCH**包含容器对象提供对显示表介绍用于输入和编辑高级的搜索条件对话框中的访问权。</span><span class="sxs-lookup"><span data-stu-id="37ace-107">**PR_SEARCH** contains a container object that provides access to a display table that describes the dialog box used to enter and edit the advanced search criteria.</span></span> 
  
 <span data-ttu-id="37ace-108">**若要支持高级搜索**</span><span class="sxs-lookup"><span data-stu-id="37ace-108">**To support advanced searching**</span></span>
  
1. <span data-ttu-id="37ace-109">定义您的搜索条件的每个属性。</span><span class="sxs-lookup"><span data-stu-id="37ace-109">Define a property for each of your search criteria.</span></span>
    
2. <span data-ttu-id="37ace-110">在容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法中的代码部分的处理**PR_SEARCH**属性：</span><span class="sxs-lookup"><span data-stu-id="37ace-110">In the section of code in your container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method that handles the **PR_SEARCH** property:</span></span> 
    
1. <span data-ttu-id="37ace-111">检查客户端请求**IMAPIContainer**接口。</span><span class="sxs-lookup"><span data-stu-id="37ace-111">Check that the client is requesting the **IMAPIContainer** interface.</span></span> <span data-ttu-id="37ace-112">请求不合适接口时，如果失败，并返回 MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="37ace-112">If an inappropriate interface is being requested, fail and return MAPI_E_INTERFACE_NOT_SUPPORTED.</span></span> 
    
2. <span data-ttu-id="37ace-113">创建新的搜索对象支持**IMAPIContainer**接口的。</span><span class="sxs-lookup"><span data-stu-id="37ace-113">Create a new search object that supports the **IMAPIContainer** interface.</span></span> 
    
3. <span data-ttu-id="37ace-114">此时，将您的搜索容器**IMAPIProp::OpenProperty**方法进行调用，若要检索其**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="37ace-114">At this point, a call will be made to your search container's **IMAPIProp::OpenProperty** method to retrieve its **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property.</span></span> <span data-ttu-id="37ace-115">您的提供商必须提供显示表，通常通过调用[BuildDisplayTable](builddisplaytable.md)，描述容器的高级的搜索对话框。</span><span class="sxs-lookup"><span data-stu-id="37ace-115">Your provider must supply a display table, typically through a call to [BuildDisplayTable](builddisplaytable.md), that describes the container's advanced search dialog box.</span></span>
    
4. <span data-ttu-id="37ace-116">MAPI 显示搜索对话框，允许用户输入适当的条件。</span><span class="sxs-lookup"><span data-stu-id="37ace-116">MAPI displays the search dialog box, allowing the user to enter the appropriate criteria.</span></span> <span data-ttu-id="37ace-117">完成用户后，MAPI 调用容器的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以存储搜索条件。</span><span class="sxs-lookup"><span data-stu-id="37ace-117">When the user has finished, MAPI calls the container's [IMAPIProp::SetProps](imapiprop-setprops.md) method to store the search criteria.</span></span> 
    
5. <span data-ttu-id="37ace-118">将进行调用以请求您搜索容器内容表。</span><span class="sxs-lookup"><span data-stu-id="37ace-118">A call will be made to request your search container's contents table.</span></span> <span data-ttu-id="37ace-119">填充使用的所有符合条件的容器中条目的内容表。</span><span class="sxs-lookup"><span data-stu-id="37ace-119">Populate the contents table with all of the entries in the container that match the criteria.</span></span>
    

