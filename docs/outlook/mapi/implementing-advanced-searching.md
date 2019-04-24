---
title: 实施高级搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 08cc60d4-cac8-4ba5-bd7f-a56e63697be3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 35d41ff903c5ed22c5210adf6448dfded0afe4b6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332814"
---
# <a name="implementing-advanced-searching"></a><span data-ttu-id="50a2d-103">实施高级搜索</span><span class="sxs-lookup"><span data-stu-id="50a2d-103">Implementing Advanced Searching</span></span>

  
  
<span data-ttu-id="50a2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50a2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50a2d-105">某些通讯簿容器支持高级搜索功能, 使客户端可以搜索除**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 以外的属性。</span><span class="sxs-lookup"><span data-stu-id="50a2d-105">Some address book containers support an advanced searching capability that allows clients to search on properties other than **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span> <span data-ttu-id="50a2d-106">若要支持高级搜索, 提供程序必须实现可通过其他容器的**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性访问的特殊容器。</span><span class="sxs-lookup"><span data-stu-id="50a2d-106">To support advanced searches, your provider must implement a special container that is accessible through the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property of your other containers.</span></span> <span data-ttu-id="50a2d-107">**PR_SEARCH**包含一个 container 对象, 该对象提供对显示表的访问, 该对象描述用于输入和编辑高级搜索条件的对话框。</span><span class="sxs-lookup"><span data-stu-id="50a2d-107">**PR_SEARCH** contains a container object that provides access to a display table that describes the dialog box used to enter and edit the advanced search criteria.</span></span> 
  
 <span data-ttu-id="50a2d-108">**支持高级搜索**</span><span class="sxs-lookup"><span data-stu-id="50a2d-108">**To support advanced searching**</span></span>
  
1. <span data-ttu-id="50a2d-109">为每个搜索条件定义属性。</span><span class="sxs-lookup"><span data-stu-id="50a2d-109">Define a property for each of your search criteria.</span></span>
    
2. <span data-ttu-id="50a2d-110">在容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法中处理**PR_SEARCH**属性的代码部分:</span><span class="sxs-lookup"><span data-stu-id="50a2d-110">In the section of code in your container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method that handles the **PR_SEARCH** property:</span></span> 
    
1. <span data-ttu-id="50a2d-111">检查客户端是否正在请求**IMAPIContainer**接口。</span><span class="sxs-lookup"><span data-stu-id="50a2d-111">Check that the client is requesting the **IMAPIContainer** interface.</span></span> <span data-ttu-id="50a2d-112">如果请求的接口不正确, 将失败并返回 MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="50a2d-112">If an inappropriate interface is being requested, fail and return MAPI_E_INTERFACE_NOT_SUPPORTED.</span></span> 
    
2. <span data-ttu-id="50a2d-113">创建支持**IMAPIContainer**接口的新搜索对象。</span><span class="sxs-lookup"><span data-stu-id="50a2d-113">Create a new search object that supports the **IMAPIContainer** interface.</span></span> 
    
3. <span data-ttu-id="50a2d-114">此时, 将对您的搜索容器的**IMAPIProp:: OpenProperty**方法进行调用, 以检索其**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="50a2d-114">At this point, a call will be made to your search container's **IMAPIProp::OpenProperty** method to retrieve its **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property.</span></span> <span data-ttu-id="50a2d-115">提供程序必须提供一个显示表 (通常通过调用[BuildDisplayTable](builddisplaytable.md)) 来描述容器的 "高级搜索" 对话框。</span><span class="sxs-lookup"><span data-stu-id="50a2d-115">Your provider must supply a display table, typically through a call to [BuildDisplayTable](builddisplaytable.md), that describes the container's advanced search dialog box.</span></span>
    
4. <span data-ttu-id="50a2d-116">MAPI 显示 "搜索" 对话框, 允许用户输入相应的条件。</span><span class="sxs-lookup"><span data-stu-id="50a2d-116">MAPI displays the search dialog box, allowing the user to enter the appropriate criteria.</span></span> <span data-ttu-id="50a2d-117">当用户完成时, MAPI 将调用容器的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法来存储搜索条件。</span><span class="sxs-lookup"><span data-stu-id="50a2d-117">When the user has finished, MAPI calls the container's [IMAPIProp::SetProps](imapiprop-setprops.md) method to store the search criteria.</span></span> 
    
5. <span data-ttu-id="50a2d-118">将发出调用以请求搜索容器的内容表。</span><span class="sxs-lookup"><span data-stu-id="50a2d-118">A call will be made to request your search container's contents table.</span></span> <span data-ttu-id="50a2d-119">使用容器中与条件匹配的所有条目填充 "内容" 表。</span><span class="sxs-lookup"><span data-stu-id="50a2d-119">Populate the contents table with all of the entries in the container that match the criteria.</span></span>
    

