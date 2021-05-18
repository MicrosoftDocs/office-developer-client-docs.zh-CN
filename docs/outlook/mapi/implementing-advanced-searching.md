---
title: 实现高级搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 08cc60d4-cac8-4ba5-bd7f-a56e63697be3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 35d41ff903c5ed22c5210adf6448dfded0afe4b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407387"
---
# <a name="implementing-advanced-searching"></a><span data-ttu-id="ad002-103">实现高级搜索</span><span class="sxs-lookup"><span data-stu-id="ad002-103">Implementing Advanced Searching</span></span>

  
  
<span data-ttu-id="ad002-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad002-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad002-105">某些通讯簿容器支持高级搜索功能，该功能允许客户端搜索[PidTagDisplayName](pidtagdisplayname-canonical-property.md) PR_DISPLAY_NAME (属性) 。 </span><span class="sxs-lookup"><span data-stu-id="ad002-105">Some address book containers support an advanced searching capability that allows clients to search on properties other than **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span></span> <span data-ttu-id="ad002-106">若要支持高级搜索，提供程序必须实现一个可通过其他容器的 **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 访问的特殊容器。</span><span class="sxs-lookup"><span data-stu-id="ad002-106">To support advanced searches, your provider must implement a special container that is accessible through the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property of your other containers.</span></span> <span data-ttu-id="ad002-107">**PR_SEARCH** 容器对象，该对象提供对显示表的访问，该显示表描述用于输入和编辑高级搜索条件的对话框。</span><span class="sxs-lookup"><span data-stu-id="ad002-107">**PR_SEARCH** contains a container object that provides access to a display table that describes the dialog box used to enter and edit the advanced search criteria.</span></span> 
  
 <span data-ttu-id="ad002-108">**支持高级搜索**</span><span class="sxs-lookup"><span data-stu-id="ad002-108">**To support advanced searching**</span></span>
  
1. <span data-ttu-id="ad002-109">为每个搜索条件定义一个属性。</span><span class="sxs-lookup"><span data-stu-id="ad002-109">Define a property for each of your search criteria.</span></span>
    
2. <span data-ttu-id="ad002-110">在容器的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法（用于处理 PR_SEARCH 属性 **）** 中：</span><span class="sxs-lookup"><span data-stu-id="ad002-110">In the section of code in your container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method that handles the **PR_SEARCH** property:</span></span> 
    
1. <span data-ttu-id="ad002-111">检查客户端是否正在请求 **IMAPIContainer** 接口。</span><span class="sxs-lookup"><span data-stu-id="ad002-111">Check that the client is requesting the **IMAPIContainer** interface.</span></span> <span data-ttu-id="ad002-112">如果请求的接口不正确，则失败并返回MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="ad002-112">If an inappropriate interface is being requested, fail and return MAPI_E_INTERFACE_NOT_SUPPORTED.</span></span> 
    
2. <span data-ttu-id="ad002-113">创建支持 **IMAPIContainer 接口的新搜索** 对象。</span><span class="sxs-lookup"><span data-stu-id="ad002-113">Create a new search object that supports the **IMAPIContainer** interface.</span></span> 
    
3. <span data-ttu-id="ad002-114">此时，将调用搜索容器 **的 IMAPIProp：：OpenProperty** 方法来检索其 **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ad002-114">At this point, a call will be made to your search container's **IMAPIProp::OpenProperty** method to retrieve its **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property.</span></span> <span data-ttu-id="ad002-115">提供程序必须提供显示表，通常通过调用 [BuildDisplayTable](builddisplaytable.md)来描述容器的高级搜索对话框。</span><span class="sxs-lookup"><span data-stu-id="ad002-115">Your provider must supply a display table, typically through a call to [BuildDisplayTable](builddisplaytable.md), that describes the container's advanced search dialog box.</span></span>
    
4. <span data-ttu-id="ad002-116">MAPI 显示搜索对话框，允许用户输入相应的条件。</span><span class="sxs-lookup"><span data-stu-id="ad002-116">MAPI displays the search dialog box, allowing the user to enter the appropriate criteria.</span></span> <span data-ttu-id="ad002-117">用户完成后，MAPI 将调用容器的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来存储搜索条件。</span><span class="sxs-lookup"><span data-stu-id="ad002-117">When the user has finished, MAPI calls the container's [IMAPIProp::SetProps](imapiprop-setprops.md) method to store the search criteria.</span></span> 
    
5. <span data-ttu-id="ad002-118">将进行调用以请求搜索容器的内容表。</span><span class="sxs-lookup"><span data-stu-id="ad002-118">A call will be made to request your search container's contents table.</span></span> <span data-ttu-id="ad002-119">使用与条件匹配的容器中的所有条目填充内容表。</span><span class="sxs-lookup"><span data-stu-id="ad002-119">Populate the contents table with all of the entries in the container that match the criteria.</span></span>
    

