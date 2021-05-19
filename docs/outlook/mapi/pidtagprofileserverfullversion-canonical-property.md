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
ms.openlocfilehash: 9456178e9426d7a5fe17382d876f507daa0251f4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341599"
---
# <a name="pidtagprofileserverfullversion-canonical-property"></a><span data-ttu-id="dc0c2-103">PidTagProfileServerFullVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc0c2-103">PidTagProfileServerFullVersion Canonical Property</span></span>

  
  
<span data-ttu-id="dc0c2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc0c2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc0c2-105">指定有关配置文件中的帐户Microsoft Exchange Server的完整版本和内部版本信息。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-105">Specifies complete version and build information about the Microsoft Exchange Server to which accounts in a profile are connected.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="dc0c2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dc0c2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dc0c2-107">PR_PROFILE_SERVER_FULL_VERSION</span><span class="sxs-lookup"><span data-stu-id="dc0c2-107">PR_PROFILE_SERVER_FULL_VERSION</span></span>  <br/> |
|<span data-ttu-id="dc0c2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="dc0c2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dc0c2-109">0x663B</span><span class="sxs-lookup"><span data-stu-id="dc0c2-109">0x663B</span></span>  <br/> |
|<span data-ttu-id="dc0c2-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="dc0c2-110">Property type:</span></span>  <br/> |<span data-ttu-id="dc0c2-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="dc0c2-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="dc0c2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dc0c2-112">Area:</span></span>  <br/> |<span data-ttu-id="dc0c2-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="dc0c2-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc0c2-114">备注</span><span class="sxs-lookup"><span data-stu-id="dc0c2-114">Remarks</span></span>

<span data-ttu-id="dc0c2-115">配置文件可以指定一个或多个连接到Exchange Server帐户，但它们必须连接到同一Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-115">A profile can specify one or more accounts that connect to an Exchange Server, but they must be connected to the same Exchange Server.</span></span>
  
<span data-ttu-id="dc0c2-116">2007 Outlook 2007 Microsoft Office Outlook版本不支持此属性。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-116">Versions of Outlook earlier than Microsoft Office Outlook 2007 do not support this property.</span></span> <span data-ttu-id="dc0c2-117">对于这些版本的Outlook，请检查配置文件 **[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** 是否存在。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-117">For those versions of Outlook, check for the existence of **[PR_PROFILE_SERVER_VERSION](pidtagprofileserverversion-canonical-property.md)** in the profile.</span></span> 
  
<span data-ttu-id="dc0c2-118">通常，如果活动邮箱连接到 Exchange Server，Outlook 2007 存储活动配置文件Exchange Server PR_PROFILE_SERVER_FULL_VERSION 属性中的完整 **PR_PROFILE_SERVER_FULL_VERSION** 版本信息。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-118">Generally, if the active mailbox is connected to an Exchange Server, Outlook 2007 stores complete Exchange Server version information in the **PR_PROFILE_SERVER_FULL_VERSION** property in the active profile.</span></span> <span data-ttu-id="dc0c2-119">Outlook将信息存储在一个EXCHANGE_STORE_VERSION_NUM结构中，其中包含主版本号和次要版本号以及主版本号和次要内部版本号。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-119">Outlook stores the information in an **EXCHANGE_STORE_VERSION_NUM** structure that contains the major and minor version numbers and the major and minor build numbers.</span></span> <span data-ttu-id="dc0c2-120">例如，若要存储 Exchange Server 版本标识符 **8.0.685.24，** 主版本号为 8，次要版本号为 0，主内部版本号为 685，次要内部版本号为 24。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-120">For example, to store the Exchange Server version identifier of **8.0.685.24**, the major version number is 8 and minor version number is 0, and the major build number is 685 and minor build number is 24.</span></span>
  
<span data-ttu-id="dc0c2-121">配置文件中 **PR_PROFILE_SERVER_VERSION** 或PR_PROFILE_SERVER_FULL_VERSION中的一个，但无法保证配置文件中始终存在其中一个。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-121">Only one of **PR_PROFILE_SERVER_VERSION** or **PR_PROFILE_SERVER_FULL_VERSION** is likely to exist in a profile, but there is no guarantee that either always exists in a profile.</span></span> <span data-ttu-id="dc0c2-122">Outlook在成功连接到任一属性之前，不会向该属性Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-122">Outlook does not write to either property until it has successfully connected to the Exchange Server.</span></span> 
  
<span data-ttu-id="dc0c2-123">在Outlook模型中，可以使用 **NameSpace** 对象的 **ExchangeMailboxServerVersion** 属性查找托管活动邮箱的 Exchange Server 版本。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-123">In the Outlook object model, you can use the **ExchangeMailboxServerVersion** property of the **NameSpace** object to find the version of Exchange Server on which the active mailbox is hosted.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="dc0c2-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="dc0c2-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dc0c2-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="dc0c2-125">Protocol specifications</span></span>

<span data-ttu-id="dc0c2-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc0c2-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc0c2-127">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-127">Provides property set definitions.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dc0c2-128">头文件</span><span class="sxs-lookup"><span data-stu-id="dc0c2-128">Header files</span></span>

<span data-ttu-id="dc0c2-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dc0c2-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="dc0c2-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="dc0c2-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dc0c2-131">Mapitags.h</span></span>
  
> <span data-ttu-id="dc0c2-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dc0c2-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dc0c2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc0c2-133">See also</span></span>



[<span data-ttu-id="dc0c2-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dc0c2-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dc0c2-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc0c2-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dc0c2-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dc0c2-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dc0c2-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dc0c2-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

