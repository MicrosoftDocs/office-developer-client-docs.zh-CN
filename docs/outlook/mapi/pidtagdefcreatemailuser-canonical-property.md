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
ms.openlocfilehash: cd09c85e4f44bbea29807d72a273ccf6980ca6df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407478"
---
# <a name="pidtagdefcreatemailuser-canonical-property"></a><span data-ttu-id="42363-103">PidTagDefCreateMailuser 规范属性</span><span class="sxs-lookup"><span data-stu-id="42363-103">PidTagDefCreateMailuser Canonical Property</span></span>

  
  
<span data-ttu-id="42363-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="42363-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="42363-105">包含默认消息传递用户对象的模板项标识符。</span><span class="sxs-lookup"><span data-stu-id="42363-105">Contains the template entry identifier for a default messaging user object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="42363-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="42363-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="42363-107">PR_DEF_CREATE_MAILUSER</span><span class="sxs-lookup"><span data-stu-id="42363-107">PR_DEF_CREATE_MAILUSER</span></span>  <br/> |
|<span data-ttu-id="42363-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="42363-108">Identifier:</span></span>  <br/> |<span data-ttu-id="42363-109">0x3612</span><span class="sxs-lookup"><span data-stu-id="42363-109">0x3612</span></span>  <br/> |
|<span data-ttu-id="42363-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="42363-110">Data type:</span></span>  <br/> |<span data-ttu-id="42363-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="42363-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="42363-112">区域：</span><span class="sxs-lookup"><span data-stu-id="42363-112">Area:</span></span>  <br/> |<span data-ttu-id="42363-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="42363-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42363-114">备注</span><span class="sxs-lookup"><span data-stu-id="42363-114">Remarks</span></span>

<span data-ttu-id="42363-115">客户端应用程序使用此属性在容器中创建消息用户对象。</span><span class="sxs-lookup"><span data-stu-id="42363-115">Client applications use this property to create a messaging user object within a container.</span></span> <span data-ttu-id="42363-116">对于通讯簿容器，支持条目创建是可选的;不支持此属性的项不需要公开此属性。</span><span class="sxs-lookup"><span data-stu-id="42363-116">Support of entry creation is optional for address book containers; those that do not support it are not required to expose this property.</span></span> 
  
<span data-ttu-id="42363-117">此属性指定可以在邮件用户的[PidTagCreateTemplates PR_CREATE_TEMPLATES (PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 条目。 </span><span class="sxs-lookup"><span data-stu-id="42363-117">This property specifies an entry that can appear in the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property for messaging users.</span></span> <span data-ttu-id="42363-118">获取标识符后，客户端在调用 [IABContainer：：CreateEntry 方法时使用它](iabcontainer-createentry.md) 。</span><span class="sxs-lookup"><span data-stu-id="42363-118">After obtaining the identifier, the client uses it in a call to the [IABContainer::CreateEntry](iabcontainer-createentry.md) method.</span></span> <span data-ttu-id="42363-119">条目表示默认邮件用户的模板。</span><span class="sxs-lookup"><span data-stu-id="42363-119">The entry represents the template for the default messaging user.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="42363-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="42363-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="42363-121">头文件</span><span class="sxs-lookup"><span data-stu-id="42363-121">Header files</span></span>

<span data-ttu-id="42363-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="42363-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="42363-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="42363-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="42363-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="42363-124">Mapitags.h</span></span>
  
> <span data-ttu-id="42363-125">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="42363-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="42363-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42363-126">See also</span></span>



[<span data-ttu-id="42363-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="42363-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="42363-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="42363-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="42363-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="42363-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="42363-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="42363-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

