---
title: PidTagIdentityEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIdentityEntryId
api_type:
- HeaderDef
ms.assetid: 61a9d403-e0e5-45c3-8d18-4d53207ab927
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 099df2211e87e253ab1be520378b3a2b2ca7d4c3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327928"
---
# <a name="pidtagidentityentryid-canonical-property"></a><span data-ttu-id="fafbf-103">PidTagIdentityEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="fafbf-103">PidTagIdentityEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="fafbf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fafbf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fafbf-105">包含在邮件系统中定义的服务提供商标识的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fafbf-105">Contains the entry identifier for a service provider's identity as defined within a messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fafbf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fafbf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fafbf-107">PR_IDENTITY_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="fafbf-107">PR_IDENTITY_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="fafbf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fafbf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fafbf-109">0x3E01</span><span class="sxs-lookup"><span data-stu-id="fafbf-109">0x3E01</span></span>  <br/> |
|<span data-ttu-id="fafbf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fafbf-110">Data type:</span></span>  <br/> |<span data-ttu-id="fafbf-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="fafbf-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="fafbf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fafbf-112">Area:</span></span>  <br/> |<span data-ttu-id="fafbf-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="fafbf-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fafbf-114">注解</span><span class="sxs-lookup"><span data-stu-id="fafbf-114">Remarks</span></span>

<span data-ttu-id="fafbf-115">此属性不显示为任何对象的属性, 而只是作为状态表中的一列。</span><span class="sxs-lookup"><span data-stu-id="fafbf-115">This property does not appear as a property on any object but only as a column in a status table.</span></span> <span data-ttu-id="fafbf-116">它是公开状态表行的服务提供程序的标识的一部分。</span><span class="sxs-lookup"><span data-stu-id="fafbf-116">It is part of the identity of the service provider exposing the status table row.</span></span> <span data-ttu-id="fafbf-117">提供程序的标识通常是指它在服务器上的帐户, 但可以引用在邮件系统中提供程序定义的任何表示形式。</span><span class="sxs-lookup"><span data-stu-id="fafbf-117">The provider's identity typically refers to its account on the server, but can refer to any representation the provider defines within the messaging system.</span></span> 
  
<span data-ttu-id="fafbf-118">此属性通常设置为相应的通讯簿条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fafbf-118">This proprerty is commonly set to the appropriate address book entry identifier.</span></span> 
  
<span data-ttu-id="fafbf-119">提供任何标识属性的服务提供商应提供所有这些标识属性。</span><span class="sxs-lookup"><span data-stu-id="fafbf-119">A service provider furnishing any of the identity properties should furnish all of them.</span></span> <span data-ttu-id="fafbf-120">属于同一邮件服务的提供程序应公开 identity 属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="fafbf-120">Providers that belong to the same message service should expose the same values for the identity properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="fafbf-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="fafbf-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fafbf-122">头文件</span><span class="sxs-lookup"><span data-stu-id="fafbf-122">Header files</span></span>

<span data-ttu-id="fafbf-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fafbf-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="fafbf-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fafbf-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="fafbf-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="fafbf-125">Mapitags.h</span></span>
  
> <span data-ttu-id="fafbf-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fafbf-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fafbf-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fafbf-127">See also</span></span>



[<span data-ttu-id="fafbf-128">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="fafbf-128">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)


[<span data-ttu-id="fafbf-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fafbf-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fafbf-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fafbf-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fafbf-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fafbf-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fafbf-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fafbf-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

