---
title: PidTagDefCreateMailuser 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefCreateMailuser
api_type:
- HeaderDef
ms.assetid: e8293dc9-f2f1-4065-89f4-e734a8db63df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21fdff2aa713905a27a3d0cc5545ceb59f030378
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586856"
---
# <a name="pidtagdefcreatemailuser-canonical-property"></a><span data-ttu-id="d08da-103">PidTagDefCreateMailuser 规范属性</span><span class="sxs-lookup"><span data-stu-id="d08da-103">PidTagDefCreateMailuser Canonical Property</span></span>

  
  
<span data-ttu-id="d08da-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d08da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d08da-105">包含消息用户对象的默认模板条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d08da-105">Contains the template entry identifier for a default messaging user object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d08da-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d08da-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d08da-107">PR_DEF_CREATE_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="d08da-107">PR_DEF_CREATE_MAILUSER</span></span>  <br/> |
|<span data-ttu-id="d08da-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d08da-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d08da-109">0x3612</span><span class="sxs-lookup"><span data-stu-id="d08da-109">0x3612</span></span>  <br/> |
|<span data-ttu-id="d08da-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d08da-110">Data type:</span></span>  <br/> |<span data-ttu-id="d08da-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d08da-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d08da-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d08da-112">Area:</span></span>  <br/> |<span data-ttu-id="d08da-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="d08da-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d08da-114">注解</span><span class="sxs-lookup"><span data-stu-id="d08da-114">Remarks</span></span>

<span data-ttu-id="d08da-115">客户端应用程序使用此属性可创建容器内的邮件用户对象。</span><span class="sxs-lookup"><span data-stu-id="d08da-115">Client applications use this property to create a messaging user object within a container.</span></span> <span data-ttu-id="d08da-116">支持的条目创建是可选的通讯簿容器;不支持的那些无需公开此属性。</span><span class="sxs-lookup"><span data-stu-id="d08da-116">Support of entry creation is optional for address book containers; those that do not support it are not required to expose this property.</span></span> 
  
<span data-ttu-id="d08da-117">此属性指定的条目可能出现的消息的用户的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="d08da-117">This property specifies an entry that can appear in the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property for messaging users.</span></span> <span data-ttu-id="d08da-118">获取后标识符，客户端使用它对[IABContainer::CreateEntry](iabcontainer-createentry.md)方法的调用中。</span><span class="sxs-lookup"><span data-stu-id="d08da-118">After obtaining the identifier, the client uses it in a call to the [IABContainer::CreateEntry](iabcontainer-createentry.md) method.</span></span> <span data-ttu-id="d08da-119">条目代表在模板默认消息用户。</span><span class="sxs-lookup"><span data-stu-id="d08da-119">The entry represents the template for the default messaging user.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d08da-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="d08da-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d08da-121">头文件</span><span class="sxs-lookup"><span data-stu-id="d08da-121">Header files</span></span>

<span data-ttu-id="d08da-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d08da-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="d08da-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d08da-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="d08da-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d08da-124">Mapitags.h</span></span>
  
> <span data-ttu-id="d08da-125">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d08da-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d08da-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d08da-126">See also</span></span>



[<span data-ttu-id="d08da-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d08da-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d08da-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d08da-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d08da-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d08da-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d08da-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d08da-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

