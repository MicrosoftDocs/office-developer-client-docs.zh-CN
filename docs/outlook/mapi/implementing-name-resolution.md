---
title: 实现名称解析
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a4c71b08-c47a-4421-8603-d5356d32dca9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4d55404149baca07a64b75d460bdfb2a8c541725
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775805"
---
# <a name="implementing-name-resolution"></a><span data-ttu-id="bb113-103">实现名称解析</span><span class="sxs-lookup"><span data-stu-id="bb113-103">Implementing Name Resolution</span></span>

  
  
<span data-ttu-id="bb113-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bb113-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bb113-105">通讯簿提供程序负责支持名称解析 — 将条目标识符显示名称相关联的过程。</span><span class="sxs-lookup"><span data-stu-id="bb113-105">Address book providers are responsible for supporting name resolution — the process of associating an entry identifier with a display name.</span></span> <span data-ttu-id="bb113-106">客户端启动名称解析致电[IAddrBook::ResolveName](iaddrbook-resolvename.md)以确保每个成员的传出邮件的收件人列表对应于有效的地址。</span><span class="sxs-lookup"><span data-stu-id="bb113-106">Clients initiate name resolution when they call [IAddrBook::ResolveName](iaddrbook-resolvename.md) to ensure that each member of an outgoing message's recipient list corresponds to a valid address.</span></span> 
  
<span data-ttu-id="bb113-107">您的提供商可以支持名称解析的：</span><span class="sxs-lookup"><span data-stu-id="bb113-107">Your provider can support name resolution by:</span></span>
  
- <span data-ttu-id="bb113-108">支持**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制，所有通讯簿容器的要求。</span><span class="sxs-lookup"><span data-stu-id="bb113-108">Supporting the **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction, a requirement for all address book containers.</span></span>
    
- <span data-ttu-id="bb113-109">实现[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法，用于所有通讯簿容器的选项。</span><span class="sxs-lookup"><span data-stu-id="bb113-109">Implementing the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method, an option for all address book containers.</span></span> 
    
<span data-ttu-id="bb113-110">如果您选择支持**IABContainer::ResolveNames**，尝试在使用_lpAdrList_参数传递的[ADRLIST](adrlist.md)结构中找到的每个未解析的显示名称的准确匹配。</span><span class="sxs-lookup"><span data-stu-id="bb113-110">If you choose to support **IABContainer::ResolveNames**, attempt to locate an exact match for each unresolved display name in the [ADRLIST](adrlist.md) structure passed in with the  _lpAdrList_ parameter.</span></span> <span data-ttu-id="bb113-111">您可以标识未解析的显示名称，因为它缺少**ADRLIST**结构中的其**aEntries**成员中的属性值数组中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bb113-111">You can identifiy an unresolved display name because it is missing the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property in the property value array in its **aEntries** member of the **ADRLIST** structure.</span></span> <span data-ttu-id="bb113-112">忽略具有零个属性及其相关联的任何项。</span><span class="sxs-lookup"><span data-stu-id="bb113-112">Ignore any entries that have zero properties associated with them.</span></span> 
  
<span data-ttu-id="bb113-113">报告您尝试分辨率_lpFlagList_参数，对应于_lpAdrList_中的显示名称的数组的标志数组中的结果。</span><span class="sxs-lookup"><span data-stu-id="bb113-113">Report the result of your attempt at resolution in the  _lpFlagList_ parameter, an array of flags that corresponds to the array of display names in  _lpAdrList_.</span></span> <span data-ttu-id="bb113-114">Flags 位置以便第一个标志对应于**ADRLIST**结构中的第一个**aEntries**成员，第二个标志对应于第二个**aEntries**成员，依此类推。</span><span class="sxs-lookup"><span data-stu-id="bb113-114">The flags are positional such that the first flag corresponds to the first **aEntries** member in the **ADRLIST** structure, the second flag corresponds to the second **aEntries** member, and so on.</span></span> 
  
<span data-ttu-id="bb113-115">有三种可能的结果，为每个未解析的项：</span><span class="sxs-lookup"><span data-stu-id="bb113-115">There are three possible results for each unresolved entry:</span></span>
  
- <span data-ttu-id="bb113-116">未找到匹配，这意味着无容器条目中的条目匹配**ADRLIST**结构中的条目。</span><span class="sxs-lookup"><span data-stu-id="bb113-116">No match was found, meaning that none of the entries in your container entries match the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="bb113-117">设置 MAPI_UNRESOLVED 的_lpFlagList_参数中的相应项。</span><span class="sxs-lookup"><span data-stu-id="bb113-117">Set the corresponding entry in the  _lpFlagList_ parameter to MAPI_UNRESOLVED.</span></span> 
    
- <span data-ttu-id="bb113-118">可以找到多个匹配，这意味着有多个容器条目相匹配的**ADRLIST**结构中的条目。</span><span class="sxs-lookup"><span data-stu-id="bb113-118">Several matches can be found, meaning that there are multiple container entries that match the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="bb113-119">设置 MAPI_AMBIGUOUS 的_lpFlagList_参数中的相应项。</span><span class="sxs-lookup"><span data-stu-id="bb113-119">Set the corresponding entry in the  _lpFlagList_ parameter to MAPI_AMBIGUOUS.</span></span> <span data-ttu-id="bb113-120">不要更改**ADRLIST**结构中的条目数。</span><span class="sxs-lookup"><span data-stu-id="bb113-120">Do not change the number of entries in the **ADRLIST** structure.</span></span> 
    
- <span data-ttu-id="bb113-121">可以找到精确的匹配，这意味着只有一个容器条目相匹配的**ADRLIST**结构中的条目。</span><span class="sxs-lookup"><span data-stu-id="bb113-121">An exact match can be found, meaning that there is only one container entry that matches the entry in the **ADRLIST** structure.</span></span> <span data-ttu-id="bb113-122">MAPI_RESOLVED _lpFlagList_参数中设置的相应成员并将条目标识符添加到与**ADRLIST**条目关联的属性的数组。</span><span class="sxs-lookup"><span data-stu-id="bb113-122">Set the corresponding member in the  _lpFlagList_ parameter to MAPI_RESOLVED and add the entry identifier to the array of properties associated with the **ADRLIST** entry.</span></span> 
    
<span data-ttu-id="bb113-123">如果您选择不支持**IABContainer::ResolveNames**，返回 MAPI_E_NO_SUPPORT 从您的实现。</span><span class="sxs-lookup"><span data-stu-id="bb113-123">If you choose not to support **IABContainer::ResolveNames**, return MAPI_E_NO_SUPPORT from your implementation.</span></span>
  
<span data-ttu-id="bb113-124">所有通讯簿提供程序都需要支持模糊名称解析- **PR_ANR**属性限制 — 对其容器的内容表。</span><span class="sxs-lookup"><span data-stu-id="bb113-124">All address book providers are required to support ambiguous name resolution — the **PR_ANR** property restriction — on their containers' contents tables.</span></span> <span data-ttu-id="bb113-125">提供支持，请通过执行搜索，针对一个或多个提供程序有意义的特定属性的匹配"最佳猜测"类型处理的[IMAPITable::Restrict](imapitable-restrict.md)实现中 PR_ANR 限制。</span><span class="sxs-lookup"><span data-stu-id="bb113-125">To provide this support, handle the PR_ANR restriction in your implementation of [IMAPITable::Restrict](imapitable-restrict.md) by performing a "best guess" type of search, matching against one or more particular properties that make sense for your provider.</span></span> <span data-ttu-id="bb113-126">您可以选择使用同一个或多个属性每次时，如**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))，或允许管理员可供选择的可接受的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="bb113-126">You can choose to use the same property or properties every time, such as **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) or **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), or allow an administrator to choose from a list of acceptable properties.</span></span> 
  
<span data-ttu-id="bb113-127">尽管大多数提供程序提供自己的内容表实现，可以自定义由 MAPI 提供通过[CreateTable](createtable.md)函数的实现。</span><span class="sxs-lookup"><span data-stu-id="bb113-127">Although most providers supply their own contents table implementation, you can customize the implementation supplied by MAPI through the [CreateTable](createtable.md) function.</span></span> <span data-ttu-id="bb113-128">但是，由于 MAPI 实现不支持任何类型的限制，您必须创建包装对象包含截取调用的**限制**的自定义的版本。</span><span class="sxs-lookup"><span data-stu-id="bb113-128">However, because the MAPI implementation does not support restrictions of any kind, you must create a wrapper object to include a customized version of **Restrict** that intercepts the call.</span></span> 
  

