---
title: 实现名称解析
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a4c71b08-c47a-4421-8603-d5356d32dca9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 15c1d502947865c02973f4950b6b6fa8109b8e78
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434702"
---
# <a name="implementing-name-resolution"></a><span data-ttu-id="1f7d0-103">实现名称解析</span><span class="sxs-lookup"><span data-stu-id="1f7d0-103">Implementing Name Resolution</span></span>

  
  
<span data-ttu-id="1f7d0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f7d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f7d0-105">通讯簿提供程序负责支持名称解析 — 将条目标识符与通讯簿关联的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-105">Address book providers are responsible for supporting name resolution — the process of associating an entry identifier with a display name.</span></span> <span data-ttu-id="1f7d0-106">客户端在调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 时启动名称解析，以确保传出邮件的收件人列表的每个成员都对应一个有效的地址。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-106">Clients initiate name resolution when they call [IAddrBook::ResolveName](iaddrbook-resolvename.md) to ensure that each member of an outgoing message's recipient list corresponds to a valid address.</span></span> 
  
<span data-ttu-id="1f7d0-107">您的提供程序可以通过：</span><span class="sxs-lookup"><span data-stu-id="1f7d0-107">Your provider can support name resolution by:</span></span>
  
- <span data-ttu-id="1f7d0-108">支持[PidTagAnr PR_ANR (PidTagAnr](pidtaganr-canonical-property.md)) 属性限制，这是所有通讯簿容器的要求。 </span><span class="sxs-lookup"><span data-stu-id="1f7d0-108">Supporting the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction, a requirement for all address book containers.</span></span>
    
- <span data-ttu-id="1f7d0-109">实现 [IABContainer：：ResolveNames](iabcontainer-resolvenames.md) 方法，这是所有通讯簿容器的一个选项。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-109">Implementing the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method, an option for all address book containers.</span></span> 
    
<span data-ttu-id="1f7d0-110">如果选择支持 **IABContainer：：ResolveNames，** 则尝试在传入 _lpAdrList_ 参数的 [ADRLIST](adrlist.md)结构中查找每个未解析 显示名称 的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-110">If you choose to support **IABContainer::ResolveNames**, attempt to locate an exact match for each unresolved display name in the [ADRLIST](adrlist.md) structure passed in with the  _lpAdrList_ parameter.</span></span> <span data-ttu-id="1f7d0-111">可以标识未解析的 显示名称因为它在 **ADRLIST** 结构的 **aEntries** 成员中的属性值数组中缺少 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-111">You can identifiy an unresolved display name because it is missing the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property in the property value array in its **aEntries** member of the **ADRLIST** structure.</span></span> <span data-ttu-id="1f7d0-112">忽略任何具有零个关联的属性的条目。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-112">Ignore any entries that have zero properties associated with them.</span></span> 
  
<span data-ttu-id="1f7d0-113">在  _lpFlagList_ 参数中报告尝试解析的结果，该参数是一个标志数组，对应于  _lpAdrList_ 中的显示名称数组。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-113">Report the result of your attempt at resolution in the  _lpFlagList_ parameter, an array of flags that corresponds to the array of display names in  _lpAdrList_.</span></span> <span data-ttu-id="1f7d0-114">标志具有位置性，因此第一个标志对应于 **ADRLIST** 结构中的第一个 **aEntries** 成员，第二个标志对应于第二个 **aEntries** 成员，以此类举。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-114">The flags are positional such that the first flag corresponds to the first **aEntries** member in the **ADRLIST** structure, the second flag corresponds to the second **aEntries** member, and so on.</span></span> 
  
<span data-ttu-id="1f7d0-115">每个未解析条目有三个可能的结果：</span><span class="sxs-lookup"><span data-stu-id="1f7d0-115">There are three possible results for each unresolved entry:</span></span>
  
- <span data-ttu-id="1f7d0-116">未找到匹配项，这意味着容器条目中没有与 **ADRLIST** 结构中的条目匹配。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-116">No match was found, meaning that none of the entries in your container entries match the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="1f7d0-117">将  _lpFlagList_ 参数中的相应条目设置为MAPI_UNRESOLVED。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-117">Set the corresponding entry in the  _lpFlagList_ parameter to MAPI_UNRESOLVED.</span></span> 
    
- <span data-ttu-id="1f7d0-118">可以发现多个匹配项，这意味着有多个与 **ADRLIST** 结构中条目匹配的容器条目。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-118">Several matches can be found, meaning that there are multiple container entries that match the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="1f7d0-119">将  _lpFlagList_ 参数中的相应条目设置为MAPI_AMBIGUOUS。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-119">Set the corresponding entry in the  _lpFlagList_ parameter to MAPI_AMBIGUOUS.</span></span> <span data-ttu-id="1f7d0-120">不要更改 **ADRLIST** 结构的条目数。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-120">Do not change the number of entries in the **ADRLIST** structure.</span></span> 
    
- <span data-ttu-id="1f7d0-121">可以找到完全匹配，这意味着只有一个容器条目与 **ADRLIST** 结构中的条目匹配。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-121">An exact match can be found, meaning that there is only one container entry that matches the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="1f7d0-122">将  _lpFlagList_ 参数中的对应成员设置为MAPI_RESOLVED条目标识符添加到与 **ADRLIST** 条目关联的属性数组。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-122">Set the corresponding member in the  _lpFlagList_ parameter to MAPI_RESOLVED and add the entry identifier to the array of properties associated with the **ADRLIST** entry.</span></span> 
    
<span data-ttu-id="1f7d0-123">如果选择不支持 **IABContainer：：ResolveNames，** 则从MAPI_E_NO_SUPPORT返回值。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-123">If you choose not to support **IABContainer::ResolveNames**, return MAPI_E_NO_SUPPORT from your implementation.</span></span>
  
<span data-ttu-id="1f7d0-124">所有通讯簿提供程序都需要支持其容器的内容表上不明确的名称解析 **（PR_ANR** 属性限制）。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-124">All address book providers are required to support ambiguous name resolution — the **PR_ANR** property restriction — on their containers' contents tables.</span></span> <span data-ttu-id="1f7d0-125">若要提供此支持，请处理 [IMAPITable：：Restrict](imapitable-restrict.md) 实现中的 PR_ANR 限制，具体方法为执行"最佳猜测"类型的搜索，与对提供程序有意义的一个或多个特定属性匹配。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-125">To provide this support, handle the PR_ANR restriction in your implementation of [IMAPITable::Restrict](imapitable-restrict.md) by performing a "best guess" type of search, matching against one or more particular properties that make sense for your provider.</span></span> <span data-ttu-id="1f7d0-126">可以选择每次使用相同的属性，如 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或 **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) ，或者允许管理员从可接受的属性列表中选择。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-126">You can choose to use the same property or properties every time, such as **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) or **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), or allow an administrator to choose from a list of acceptable properties.</span></span> 
  
<span data-ttu-id="1f7d0-127">虽然大多数提供程序提供其自己的内容表实现，但您可以通过 [CreateTable](createtable.md) 函数自定义 MAPI 提供的实现。</span><span class="sxs-lookup"><span data-stu-id="1f7d0-127">Although most providers supply their own contents table implementation, you can customize the implementation supplied by MAPI through the [CreateTable](createtable.md) function.</span></span> <span data-ttu-id="1f7d0-128">但是，由于 MAPI 实现不支持任何类型的限制，因此必须创建包装对象以包含可截获调用的 **自定义版本的 Restrict。**</span><span class="sxs-lookup"><span data-stu-id="1f7d0-128">However, because the MAPI implementation does not support restrictions of any kind, you must create a wrapper object to include a customized version of **Restrict** that intercepts the call.</span></span> 
  

