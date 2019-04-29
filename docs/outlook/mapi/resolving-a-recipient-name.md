---
title: 解析收件人姓名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2baed391-85bd-4e88-8800-c19bc2d2d54a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a3faed3dda2461cab749c824fc97c2074e62375f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405862"
---
# <a name="resolving-a-recipient-name"></a><span data-ttu-id="48a1a-103">解析收件人姓名</span><span class="sxs-lookup"><span data-stu-id="48a1a-103">Resolving a Recipient Name</span></span>

  
  
<span data-ttu-id="48a1a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48a1a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48a1a-105">发送邮件时, 将使用与每个收件人相关的属性生成收件人列表。</span><span class="sxs-lookup"><span data-stu-id="48a1a-105">When a message is addressed, a recipient list is built with properties relating to each recipient.</span></span> <span data-ttu-id="48a1a-106">在发送邮件时, 其中一个属性必须是收件人的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="48a1a-106">By the time the message is sent, one of those properties must be the recipient's long-term entry identifier.</span></span> <span data-ttu-id="48a1a-107">若要确保每个收件人都包含**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性, 请在对 IAddrBook 的调用中传递在_lpAdrList_参数的内容中描述您的收件人列表的[ADRLIST](adrlist.md)结构[::ResolveName](iaddrbook-resolvename.md)。</span><span class="sxs-lookup"><span data-stu-id="48a1a-107">To ensure that each recipient includes the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, pass the [ADRLIST](adrlist.md) structure describing your recipient list in the contents of the  _lpAdrList_ parameter in a call to [IAddrBook::ResolveName](iaddrbook-resolvename.md).</span></span>
  
 <span data-ttu-id="48a1a-108">**ResolveName**通过忽略已解决的**ADRLIST**结构中的条目来开始处理, 如相应[ADRENTRY](adrentry.md)结构的**SPropValue**中的条目标识符的存在所示。数组.</span><span class="sxs-lookup"><span data-stu-id="48a1a-108">**ResolveName** begins processing by ignoring the entries in the **ADRLIST** structure that have already been resolved, as indicated by the presence of an entry identifier in the corresponding [ADRENTRY](adrentry.md) structure's **SPropValue** array.</span></span> <span data-ttu-id="48a1a-109">接下来, **ResolveName**自动为两种类型的收件人分配一次性条目标识符:</span><span class="sxs-lookup"><span data-stu-id="48a1a-109">Next, **ResolveName** automatically assigns one-off entry identifiers to two types of recipients:</span></span> 
  
- <span data-ttu-id="48a1a-110">地址格式为 Internet 地址的收件人</span><span class="sxs-lookup"><span data-stu-id="48a1a-110">Recipients with an address formatted as an Internet address</span></span>
    
- <span data-ttu-id="48a1a-111">地址格式如下所示的收件人:</span><span class="sxs-lookup"><span data-stu-id="48a1a-111">Recipients with an address formatted as follows:</span></span>
    
     `displayname[address type:email address]`
    
<span data-ttu-id="48a1a-112">对于其余的所有条目, **ResolveName**在通讯簿中搜索显示名称的精确匹配项。</span><span class="sxs-lookup"><span data-stu-id="48a1a-112">For all remaining entries, **ResolveName** searches the address book for an exact match on the display name.</span></span> <span data-ttu-id="48a1a-113">**ResolveName**使用**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性确定要搜索的容器集和搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="48a1a-113">**ResolveName** uses the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property to determine the set of containers to search and the search order.</span></span> <span data-ttu-id="48a1a-114">MAPI 调用每个容器的[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法来尝试解析所有名称。</span><span class="sxs-lookup"><span data-stu-id="48a1a-114">MAPI calls the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method of every container to attempt to resolve all of the names.</span></span> <span data-ttu-id="48a1a-115">由于某些容器不支持**ResolveNames**, 如果容器返回 MAPI_E_NO_SUPPORT, 则 MAPI 会对其内容表应用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制。</span><span class="sxs-lookup"><span data-stu-id="48a1a-115">Because some containers do not support **ResolveNames**, if the container returns MAPI_E_NO_SUPPORT, MAPI applies a **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction against its contents table.</span></span> <span data-ttu-id="48a1a-116">必须使用所有通讯簿容器来支持此限制中的名称解析。</span><span class="sxs-lookup"><span data-stu-id="48a1a-116">All address book containers are required to support name resolution with this restriction.</span></span> <span data-ttu-id="48a1a-117">解析所有名称后, 将不会再进行容器调用。</span><span class="sxs-lookup"><span data-stu-id="48a1a-117">Once all the names are resolved, no further container calls are made.</span></span> <span data-ttu-id="48a1a-118">如果所有容器都已被调用, 但保留不明确或未解析的名称, MAPI 将显示一个对话框, 提示用户解决其余的名称。</span><span class="sxs-lookup"><span data-stu-id="48a1a-118">If all the containers have been called, but ambiguous or unresolved names remain, MAPI displays a dialog box if possible to prompt the user to resolve the remaining names.</span></span>
  
<span data-ttu-id="48a1a-119">**PR_ANR**限制将**PR_ANR**属性的值与**ADRLIST**结构中的显示名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="48a1a-119">The **PR_ANR** restriction matches the value of the **PR_ANR** property against the display name in the **ADRLIST** structure.</span></span> <span data-ttu-id="48a1a-120">使用**PR_ANR**属性限制限制容器的内容表的视图会导致通讯簿提供程序执行 "最佳推测" 类型的搜索, 使其符合对提供程序有意义的属性。</span><span class="sxs-lookup"><span data-stu-id="48a1a-120">Limiting the view of a container's contents table with the **PR_ANR** property restriction causes the address book provider to perform a "best guess" type of search, matching against the property that makes sense for the provider.</span></span> <span data-ttu-id="48a1a-121">例如, 一个通讯簿提供程序可能始终会将收件人列表中的名称与**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 相匹配, 而另一个通讯簿提供程序可能允许管理员选择该属性。</span><span class="sxs-lookup"><span data-stu-id="48a1a-121">For example, one address book provider might always match names in the recipient list against **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) while another might allow an administrator to select the property.</span></span>
  
 <span data-ttu-id="48a1a-122">**在通讯簿容器的内容表上设置 PR_ANR 属性限制**</span><span class="sxs-lookup"><span data-stu-id="48a1a-122">**To set a PR_ANR property restriction on an address book container's contents table**</span></span>
  
1. <span data-ttu-id="48a1a-123">创建[SRestriction](srestriction.md)结构, 如以下代码所示:</span><span class="sxs-lookup"><span data-stu-id="48a1a-123">Create an [SRestriction](srestriction.md) structure as shown in the following code:</span></span> 
    
  ```cpp
  SRestriction SRestrict;
  SRestrict.rt = RES_PROPERTY;
  SRestrict.res.resProperty.relop = RELOP_EQ;
  SRestrict.res.resProperty.ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->Value.LPSZ = lpszName;
   
  ```

2. <span data-ttu-id="48a1a-124">调用内容表的[IMAPITable:: Restrict](imapitable-restrict.md)方法, 并将**SRestriction**结构作为_lpRestriction_参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="48a1a-124">Call the contents table's [IMAPITable::Restrict](imapitable-restrict.md) method, passing the **SRestriction** structure as the  _lpRestriction_ parameter.</span></span> 
    

