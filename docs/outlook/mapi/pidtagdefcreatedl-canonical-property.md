---
title: PidTagDefCreateDl 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefCreateDl
api_type:
- HeaderDef
ms.assetid: 172dc15b-7bda-403f-a93a-446b2f9ff1d3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 48c068599506e5c050c69594caca46f28be83b0b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565800"
---
# <a name="pidtagdefcreatedl-canonical-property"></a><span data-ttu-id="13f83-103">PidTagDefCreateDl 规范属性</span><span class="sxs-lookup"><span data-stu-id="13f83-103">PidTagDefCreateDl Canonical Property</span></span>

  
  
<span data-ttu-id="13f83-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13f83-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13f83-105">包含默认通讯组列表的模板条目标识符。</span><span class="sxs-lookup"><span data-stu-id="13f83-105">Contains the template entry identifier for a default distribution list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="13f83-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="13f83-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="13f83-107">PR_DEF_CREATE_DL</span><span class="sxs-lookup"><span data-stu-id="13f83-107">PR_DEF_CREATE_DL</span></span>  <br/> |
|<span data-ttu-id="13f83-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="13f83-108">Identifier:</span></span>  <br/> |<span data-ttu-id="13f83-109">0x3611</span><span class="sxs-lookup"><span data-stu-id="13f83-109">0x3611</span></span>  <br/> |
|<span data-ttu-id="13f83-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="13f83-110">Data type:</span></span>  <br/> |<span data-ttu-id="13f83-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="13f83-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="13f83-112">区域：</span><span class="sxs-lookup"><span data-stu-id="13f83-112">Area:</span></span>  <br/> |<span data-ttu-id="13f83-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="13f83-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="13f83-114">注解</span><span class="sxs-lookup"><span data-stu-id="13f83-114">Remarks</span></span>

<span data-ttu-id="13f83-115">客户端应用程序使用此属性来创建通讯组列表容器中。</span><span class="sxs-lookup"><span data-stu-id="13f83-115">Client applications use this property to create a distribution list within a container.</span></span> <span data-ttu-id="13f83-116">支持的条目创建是可选的通讯簿容器;不支持的那些无需公开此属性。</span><span class="sxs-lookup"><span data-stu-id="13f83-116">Support of entry creation is optional for address book containers; those that do not support it are not required to expose this property.</span></span> 
  
<span data-ttu-id="13f83-117">此属性指定通讯组列表的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性中可显示一个条目。</span><span class="sxs-lookup"><span data-stu-id="13f83-117">This property specifies an entry that can appear in the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property for distribution lists.</span></span> <span data-ttu-id="13f83-118">获取后标识符，客户端使用它对[IABContainer::CreateEntry](iabcontainer-createentry.md)方法的调用中。</span><span class="sxs-lookup"><span data-stu-id="13f83-118">After obtaining the identifier, the client uses it in a call to the [IABContainer::CreateEntry](iabcontainer-createentry.md) method.</span></span> <span data-ttu-id="13f83-119">条目代表在默认通讯组列表的模板。</span><span class="sxs-lookup"><span data-stu-id="13f83-119">The entry represents the template for the default distribution list.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="13f83-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="13f83-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="13f83-121">头文件</span><span class="sxs-lookup"><span data-stu-id="13f83-121">Header files</span></span>

<span data-ttu-id="13f83-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="13f83-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="13f83-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="13f83-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="13f83-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="13f83-124">Mapitags.h</span></span>
  
> <span data-ttu-id="13f83-125">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="13f83-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="13f83-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13f83-126">See also</span></span>



[<span data-ttu-id="13f83-127">IABLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="13f83-127">IABLogon::CompareEntryIDs</span></span>](iablogon-compareentryids.md)


[<span data-ttu-id="13f83-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="13f83-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="13f83-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="13f83-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="13f83-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="13f83-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="13f83-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="13f83-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

