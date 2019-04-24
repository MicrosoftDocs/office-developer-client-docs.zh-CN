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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310078"
---
# <a name="implementing-name-resolution"></a><span data-ttu-id="9b9f0-103">实现名称解析</span><span class="sxs-lookup"><span data-stu-id="9b9f0-103">Implementing Name Resolution</span></span>

  
  
<span data-ttu-id="9b9f0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b9f0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b9f0-105">通讯簿提供程序负责支持名称解析, 即将条目标识符与显示名称关联的过程。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-105">Address book providers are responsible for supporting name resolution — the process of associating an entry identifier with a display name.</span></span> <span data-ttu-id="9b9f0-106">客户端在调用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)时启动名称解析, 以确保传出邮件的收件人列表的每个成员都对应于一个有效的地址。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-106">Clients initiate name resolution when they call [IAddrBook::ResolveName](iaddrbook-resolvename.md) to ensure that each member of an outgoing message's recipient list corresponds to a valid address.</span></span> 
  
<span data-ttu-id="9b9f0-107">提供程序可以通过以下方式支持名称解析:</span><span class="sxs-lookup"><span data-stu-id="9b9f0-107">Your provider can support name resolution by:</span></span>
  
- <span data-ttu-id="9b9f0-108">支持**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制, 这是对所有通讯簿容器的要求。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-108">Supporting the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction, a requirement for all address book containers.</span></span>
    
- <span data-ttu-id="9b9f0-109">实现[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法, 一个适用于所有通讯簿容器的选项。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-109">Implementing the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method, an option for all address book containers.</span></span> 
    
<span data-ttu-id="9b9f0-110">如果选择支持**IABContainer:: ResolveNames**, 请尝试查找与使用_lpAdrList_参数传入的[ADRLIST](adrlist.md)结构中的每个未解析的显示名称完全匹配的项。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-110">If you choose to support **IABContainer::ResolveNames**, attempt to locate an exact match for each unresolved display name in the [ADRLIST](adrlist.md) structure passed in with the  _lpAdrList_ parameter.</span></span> <span data-ttu-id="9b9f0-111">您可以 identifiy 一个未解析的显示名称, 因为它在**ADRLIST**结构的**aEntries**成员的属性值数组中缺少**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-111">You can identifiy an unresolved display name because it is missing the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property in the property value array in its **aEntries** member of the **ADRLIST** structure.</span></span> <span data-ttu-id="9b9f0-112">忽略任何与零属性相关联的条目。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-112">Ignore any entries that have zero properties associated with them.</span></span> 
  
<span data-ttu-id="9b9f0-113">报告_lpFlagList_参数中的解析结果, 即与_lpAdrList_中的显示名称数组相对应的标志数组。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-113">Report the result of your attempt at resolution in the  _lpFlagList_ parameter, an array of flags that corresponds to the array of display names in  _lpAdrList_.</span></span> <span data-ttu-id="9b9f0-114">这些标志的位置如下: 第一个标志对应于**ADRLIST**结构中的第一个**aEntries**成员, 第二个标志对应于第二个**aEntries**成员, 依此类推。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-114">The flags are positional such that the first flag corresponds to the first **aEntries** member in the **ADRLIST** structure, the second flag corresponds to the second **aEntries** member, and so on.</span></span> 
  
<span data-ttu-id="9b9f0-115">每个未解析的条目都有三个可能的结果:</span><span class="sxs-lookup"><span data-stu-id="9b9f0-115">There are three possible results for each unresolved entry:</span></span>
  
- <span data-ttu-id="9b9f0-116">找不到匹配项, 这意味着容器条目中的任何条目都与**ADRLIST**结构中的条目不匹配。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-116">No match was found, meaning that none of the entries in your container entries match the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="9b9f0-117">将_lpFlagList_参数中对应的条目设置为 MAPI_UNRESOLVED。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-117">Set the corresponding entry in the  _lpFlagList_ parameter to MAPI_UNRESOLVED.</span></span> 
    
- <span data-ttu-id="9b9f0-118">可以找到多个匹配项, 这意味着有多个容器条目与**ADRLIST**结构中的条目相匹配。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-118">Several matches can be found, meaning that there are multiple container entries that match the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="9b9f0-119">将_lpFlagList_参数中对应的条目设置为 MAPI_AMBIGUOUS。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-119">Set the corresponding entry in the  _lpFlagList_ parameter to MAPI_AMBIGUOUS.</span></span> <span data-ttu-id="9b9f0-120">请勿更改**ADRLIST**结构中的条目数。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-120">Do not change the number of entries in the **ADRLIST** structure.</span></span> 
    
- <span data-ttu-id="9b9f0-121">可以找到完全匹配的, 这意味着只有一个容器条目与**ADRLIST**结构中的条目相匹配。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-121">An exact match can be found, meaning that there is only one container entry that matches the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="9b9f0-122">将_lpFlagList_参数中对应的成员设置为 MAPI_RESOLVED, 并将条目标识符添加到与**ADRLIST**条目关联的属性数组中。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-122">Set the corresponding member in the  _lpFlagList_ parameter to MAPI_RESOLVED and add the entry identifier to the array of properties associated with the **ADRLIST** entry.</span></span> 
    
<span data-ttu-id="9b9f0-123">如果您选择不支持**IABContainer:: ResolveNames**, 请从您的实现返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-123">If you choose not to support **IABContainer::ResolveNames**, return MAPI_E_NO_SUPPORT from your implementation.</span></span>
  
<span data-ttu-id="9b9f0-124">所有通讯簿提供程序都需要在其容器的内容表上支持不明确的名称解析 ( **PR_ANR**属性限制)。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-124">All address book providers are required to support ambiguous name resolution — the **PR_ANR** property restriction — on their containers' contents tables.</span></span> <span data-ttu-id="9b9f0-125">若要提供此支持, 请在您的[IMAPITable:: Restrict](imapitable-restrict.md)中通过执行 "最佳推测" 类型的搜索来处理 PR_ANR 限制, 使其与对您的提供商有意义的一个或多个特定属性相匹配。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-125">To provide this support, handle the PR_ANR restriction in your implementation of [IMAPITable::Restrict](imapitable-restrict.md) by performing a "best guess" type of search, matching against one or more particular properties that make sense for your provider.</span></span> <span data-ttu-id="9b9f0-126">您可以选择每次使用相同的属性或属性, 例如**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), 或允许管理员从可接受的属性列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-126">You can choose to use the same property or properties every time, such as **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) or **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), or allow an administrator to choose from a list of acceptable properties.</span></span> 
  
<span data-ttu-id="9b9f0-127">尽管大多数提供程序都提供其自己的内容表实现, 但您可以通过[CreateTable](createtable.md)函数自定义 MAPI 提供的实现。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-127">Although most providers supply their own contents table implementation, you can customize the implementation supplied by MAPI through the [CreateTable](createtable.md) function.</span></span> <span data-ttu-id="9b9f0-128">但是, 由于 MAPI 实现不支持任何种类的限制, 因此您必须创建一个包装对象, 以包含截获该调用的自定义版本的**限制**。</span><span class="sxs-lookup"><span data-stu-id="9b9f0-128">However, because the MAPI implementation does not support restrictions of any kind, you must create a wrapper object to include a customized version of **Restrict** that intercepts the call.</span></span> 
  

