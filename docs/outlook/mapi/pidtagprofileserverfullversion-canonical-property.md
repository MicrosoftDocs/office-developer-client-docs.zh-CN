---
title: PidTagProfileServerFullVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8c88a625-da57-3b1d-9887-0a898b722766
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a10209bd965591e9049027e46d84d904bba14065
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580227"
---
# <a name="pidtagprofileserverfullversion-canonical-property"></a><span data-ttu-id="cced3-103">PidTagProfileServerFullVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="cced3-103">PidTagProfileServerFullVersion Canonical Property</span></span>

  
  
<span data-ttu-id="cced3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cced3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cced3-105">指定配置文件中的帐户连接到 Microsoft Exchange Server 完整的版本和内部版本信息。</span><span class="sxs-lookup"><span data-stu-id="cced3-105">Specifies complete version and build information about the Microsoft Exchange Server to which accounts in a profile are connected.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="cced3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cced3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cced3-107">PR_PROFILE_SERVER_FULL_VERSION</span><span class="sxs-lookup"><span data-stu-id="cced3-107">PR_PROFILE_SERVER_FULL_VERSION</span></span>  <br/> |
|<span data-ttu-id="cced3-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="cced3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cced3-109">0x663B</span><span class="sxs-lookup"><span data-stu-id="cced3-109">0x663B</span></span>  <br/> |
|<span data-ttu-id="cced3-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="cced3-110">Property type:</span></span>  <br/> |<span data-ttu-id="cced3-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="cced3-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="cced3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cced3-112">Area:</span></span>  <br/> |<span data-ttu-id="cced3-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="cced3-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cced3-114">注解</span><span class="sxs-lookup"><span data-stu-id="cced3-114">Remarks</span></span>

<span data-ttu-id="cced3-115">一个配置文件可以指定一个或多个帐户连接到 Exchange 服务器，但他们必须连接到同一 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="cced3-115">A profile can specify one or more accounts that connect to an Exchange Server, but they must be connected to the same Exchange Server.</span></span>
  
<span data-ttu-id="cced3-116">早于 Microsoft Office Outlook 2007 的 Outlook 版本不支持此属性。</span><span class="sxs-lookup"><span data-stu-id="cced3-116">Versions of Outlook earlier than Microsoft Office Outlook 2007 do not support this property.</span></span> <span data-ttu-id="cced3-117">对于那些版本的 Outlook 中，查看配置文件中存在**[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** 。</span><span class="sxs-lookup"><span data-stu-id="cced3-117">For those versions of Outlook, check for the existence of **[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** in the profile.</span></span> 
  
<span data-ttu-id="cced3-118">通常，如果活动邮箱已连接到 Exchange 服务器中，Outlook 2007 **PR_PROFILE_SERVER_FULL_VERSION**属性中的活动配置文件存储完成 Exchange Server 版本信息。</span><span class="sxs-lookup"><span data-stu-id="cced3-118">Generally, if the active mailbox is connected to an Exchange Server, Outlook 2007 stores complete Exchange Server version information in the **PR_PROFILE_SERVER_FULL_VERSION** property in the active profile.</span></span> <span data-ttu-id="cced3-119">Outlook 中包含的主要和次要版本号和主要和次要版本号**EXCHANGE_STORE_VERSION_NUM**结构存储信息。</span><span class="sxs-lookup"><span data-stu-id="cced3-119">Outlook stores the information in an **EXCHANGE_STORE_VERSION_NUM** structure that contains the major and minor version numbers and the major and minor build numbers.</span></span> <span data-ttu-id="cced3-120">例如，若要存储**8.0.685.24**的 Exchange Server 版本标识符的主版本号为 8 和次要版本数字为 0，和主要版本号是 685 和次要版本号为 24。</span><span class="sxs-lookup"><span data-stu-id="cced3-120">For example, to store the Exchange Server version identifier of **8.0.685.24**, the major version number is 8 and minor version number is 0, and the major build number is 685 and minor build number is 24.</span></span>
  
<span data-ttu-id="cced3-121">只有一个**PR_PROFILE_SERVER_VERSION**或**PR_PROFILE_SERVER_FULL_VERSION**可能存在于配置文件，但以下任意始终存在配置文件中不能保证。</span><span class="sxs-lookup"><span data-stu-id="cced3-121">Only one of **PR_PROFILE_SERVER_VERSION** or **PR_PROFILE_SERVER_FULL_VERSION** is likely to exist in a profile, but there is no guarantee that either always exists in a profile.</span></span> <span data-ttu-id="cced3-122">Outlook 不会写入这两个属性，直到成功连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="cced3-122">Outlook does not write to either property until it has successfully connected to the Exchange Server.</span></span> 
  
<span data-ttu-id="cced3-123">在 Outlook 对象模型中，您可以使用**NameSpace**对象的**ExchangeMailboxServerVersion**属性查找在其托管主动邮箱的 Exchange Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="cced3-123">In the Outlook object model, you can use the **ExchangeMailboxServerVersion** property of the **NameSpace** object to find the version of Exchange Server on which the active mailbox is hosted.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="cced3-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="cced3-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cced3-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="cced3-125">Protocol specifications</span></span>

<span data-ttu-id="cced3-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cced3-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cced3-127">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="cced3-127">Provides property set definitions.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cced3-128">头文件</span><span class="sxs-lookup"><span data-stu-id="cced3-128">Header files</span></span>

<span data-ttu-id="cced3-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cced3-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="cced3-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cced3-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="cced3-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cced3-131">Mapitags.h</span></span>
  
> <span data-ttu-id="cced3-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cced3-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cced3-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cced3-133">See also</span></span>



[<span data-ttu-id="cced3-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cced3-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cced3-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cced3-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cced3-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cced3-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cced3-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cced3-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

