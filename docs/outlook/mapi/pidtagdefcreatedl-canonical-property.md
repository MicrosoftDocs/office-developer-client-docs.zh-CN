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
ms.openlocfilehash: ff5d35104e9effc27c405b716cb61cf4643677b3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359953"
---
# <a name="pidtagdefcreatedl-canonical-property"></a><span data-ttu-id="8a9cc-103">PidTagDefCreateDl 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a9cc-103">PidTagDefCreateDl Canonical Property</span></span>

  
  
<span data-ttu-id="8a9cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a9cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a9cc-105">包含默认通讯组列表的模板条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-105">Contains the template entry identifier for a default distribution list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8a9cc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8a9cc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8a9cc-107">PR_DEF_CREATE_DL</span><span class="sxs-lookup"><span data-stu-id="8a9cc-107">PR_DEF_CREATE_DL</span></span>  <br/> |
|<span data-ttu-id="8a9cc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8a9cc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8a9cc-109">0x3611</span><span class="sxs-lookup"><span data-stu-id="8a9cc-109">0x3611</span></span>  <br/> |
|<span data-ttu-id="8a9cc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8a9cc-110">Data type:</span></span>  <br/> |<span data-ttu-id="8a9cc-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8a9cc-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8a9cc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8a9cc-112">Area:</span></span>  <br/> |<span data-ttu-id="8a9cc-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="8a9cc-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8a9cc-114">注解</span><span class="sxs-lookup"><span data-stu-id="8a9cc-114">Remarks</span></span>

<span data-ttu-id="8a9cc-115">客户端应用程序使用此属性在容器中创建通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-115">Client applications use this property to create a distribution list within a container.</span></span> <span data-ttu-id="8a9cc-116">对 "条目创建" 的支持对于通讯簿容器是可选的;不支持它的方法不需要公开此属性。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-116">Support of entry creation is optional for address book containers; those that do not support it are not required to expose this property.</span></span> 
  
<span data-ttu-id="8a9cc-117">此属性指定可显示在通讯组列表的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性中的条目。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-117">This property specifies an entry that can appear in the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property for distribution lists.</span></span> <span data-ttu-id="8a9cc-118">获取标识符后, 客户端将在调用[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法时使用它。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-118">After obtaining the identifier, the client uses it in a call to the [IABContainer::CreateEntry](iabcontainer-createentry.md) method.</span></span> <span data-ttu-id="8a9cc-119">条目表示默认通讯组列表的模板。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-119">The entry represents the template for the default distribution list.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8a9cc-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="8a9cc-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8a9cc-121">头文件</span><span class="sxs-lookup"><span data-stu-id="8a9cc-121">Header files</span></span>

<span data-ttu-id="8a9cc-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8a9cc-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="8a9cc-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="8a9cc-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8a9cc-124">Mapitags.h</span></span>
  
> <span data-ttu-id="8a9cc-125">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8a9cc-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8a9cc-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a9cc-126">See also</span></span>



[<span data-ttu-id="8a9cc-127">IABLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="8a9cc-127">IABLogon::CompareEntryIDs</span></span>](iablogon-compareentryids.md)


[<span data-ttu-id="8a9cc-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8a9cc-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8a9cc-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a9cc-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8a9cc-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8a9cc-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8a9cc-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8a9cc-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

