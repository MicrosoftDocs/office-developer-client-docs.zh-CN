---
title: PidTagRuleProvider 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleProvider
api_type:
- COM
ms.assetid: 64f80a03-9ba4-495a-9666-b3a909335cb6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 19889a1f48a6088f0d5ad224f7e9189b112622fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280603"
---
# <a name="pidtagruleprovider-canonical-property"></a><span data-ttu-id="fb692-103">PidTagRuleProvider 规范属性</span><span class="sxs-lookup"><span data-stu-id="fb692-103">PidTagRuleProvider Canonical Property</span></span>

  
  
<span data-ttu-id="fb692-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb692-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb692-105">包含设置规则的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="fb692-105">Contains the name of the application that sets a rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fb692-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fb692-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fb692-107">PR_RULE_PROVIDER、PR_RULE_PROVIDER_A、PR_RULE_PROVIDER_W</span><span class="sxs-lookup"><span data-stu-id="fb692-107">PR_RULE_PROVIDER, PR_RULE_PROVIDER_A , PR_RULE_PROVIDER_W</span></span>  <br/> |
|<span data-ttu-id="fb692-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fb692-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fb692-109">0x6681</span><span class="sxs-lookup"><span data-stu-id="fb692-109">0x6681</span></span>  <br/> |
|<span data-ttu-id="fb692-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fb692-110">Data type:</span></span>  <br/> |<span data-ttu-id="fb692-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fb692-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="fb692-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fb692-112">Area:</span></span>  <br/> |<span data-ttu-id="fb692-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="fb692-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fb692-114">备注</span><span class="sxs-lookup"><span data-stu-id="fb692-114">Remarks</span></span>

<span data-ttu-id="fb692-115">延迟操作需要这些属性来标识必须解释和执行规则操作的代码。</span><span class="sxs-lookup"><span data-stu-id="fb692-115">Deferred actions need these properties to identify the code that must interpret and execute the rule action.</span></span>
  
<span data-ttu-id="fb692-116">存储在邮箱和文件夹上的规则通过规则提供程序字符串与拥有这些规则的应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="fb692-116">Rules stored on mailboxes and folders are associated with the application that owns them by a rule provider string.</span></span> <span data-ttu-id="fb692-117">规则提供程序设置和处理规则表中的规则。</span><span class="sxs-lookup"><span data-stu-id="fb692-117">A rule provider sets and handles rules in a rule table.</span></span> <span data-ttu-id="fb692-118">它还提供了一种处理任何延迟操作（如果设置了此类规则）的方式。</span><span class="sxs-lookup"><span data-stu-id="fb692-118">It also provides a means of handling any deferred actions if such rules are set.</span></span> <span data-ttu-id="fb692-119">延迟操作由信息存储隐式创建。</span><span class="sxs-lookup"><span data-stu-id="fb692-119">Deferred actions are created implicitly by the information store.</span></span> <span data-ttu-id="fb692-120">对于将操作移动或复制到其他存储区，如果提供程序设置了延迟操作规则，则提供程序必须提供处理程序，以在触发规则并创建延迟操作时执行该操作。</span><span class="sxs-lookup"><span data-stu-id="fb692-120">For move or copy operations to a different store, if a provider sets a deferred action rule, it must provide a handler to perform the action when the rule is fired and a deferred action is created.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fb692-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="fb692-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fb692-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="fb692-122">Protocol specifications</span></span>

<span data-ttu-id="fb692-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fb692-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fb692-124">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="fb692-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fb692-125">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fb692-125">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fb692-126">在服务器上处理传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fb692-126">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fb692-127">头文件</span><span class="sxs-lookup"><span data-stu-id="fb692-127">Header files</span></span>

<span data-ttu-id="fb692-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fb692-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="fb692-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fb692-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="fb692-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fb692-130">Mapitags.h</span></span>
  
> <span data-ttu-id="fb692-131">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fb692-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fb692-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb692-132">See also</span></span>



[<span data-ttu-id="fb692-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fb692-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fb692-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fb692-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fb692-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fb692-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fb692-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fb692-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

