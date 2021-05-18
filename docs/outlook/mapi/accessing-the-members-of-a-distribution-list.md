---
title: 访问通讯组列表的成员
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f724cac8-2d5d-42bc-a15e-99f77a99ce21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2944a53d27bc916ccafcfa649d79e3c00afaf622
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412385"
---
# <a name="accessing-the-members-of-a-distribution-list"></a><span data-ttu-id="a4872-103">访问通讯组列表的成员</span><span class="sxs-lookup"><span data-stu-id="a4872-103">Accessing the Members of a Distribution List</span></span>

  
  
<span data-ttu-id="a4872-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4872-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="a4872-105">**获取通讯组列表的成员**</span><span class="sxs-lookup"><span data-stu-id="a4872-105">**To get the members of a distribution list**</span></span>
  
1. <span data-ttu-id="a4872-106">使用要检索的成员的属性（如 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md) **) 、PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和 **PR_DISPLAY_TYPE**  ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) ）创建大小属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="a4872-106">Create a sized property tag array with the properties of the members you would like to retrieve, such as **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)), and **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)).</span></span>
    
2. <span data-ttu-id="a4872-107">调用 [IAddrBook：：OpenEntry](iaddrbook-openentry.md) 打开通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a4872-107">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md) to open the distribution list.</span></span> 
    
3. <span data-ttu-id="a4872-108">调用通讯组列表的 **IABContainer：：GetContentsTable** 方法以访问其内容表。</span><span class="sxs-lookup"><span data-stu-id="a4872-108">Call the distribution list's **IABContainer::GetContentsTable** method to access its contents table.</span></span> 
    
4. <span data-ttu-id="a4872-109">调用 [HrQueryAllRows](hrqueryallrows.md) 以检索表示通讯组列表成员的表的所有行。</span><span class="sxs-lookup"><span data-stu-id="a4872-109">Call [HrQueryAllRows](hrqueryallrows.md) to retrieve all of the table's rows representing the members of the distribution list.</span></span> 
    

