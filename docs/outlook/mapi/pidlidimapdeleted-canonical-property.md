---
title: PidLidImapDeleted 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidImapDeleted
api_type:
- COM
ms.assetid: ee929306-8962-494d-bc47-9b4069f01267
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3008422420dc9bd02f32cbb6900ffe4ebba38877
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595088"
---
# <a name="pidlidimapdeleted-canonical-property"></a><span data-ttu-id="04a69-103">PidLidImapDeleted 规范属性</span><span class="sxs-lookup"><span data-stu-id="04a69-103">PidLidImapDeleted Canonical Property</span></span>

  
  
<span data-ttu-id="04a69-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="04a69-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="04a69-105">表示标记为删除的 Internet 邮件访问协议 (IMAP) 项。</span><span class="sxs-lookup"><span data-stu-id="04a69-105">Denotes Internet Mail Access Protocol (IMAP) items that are marked for deletion.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="04a69-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="04a69-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="04a69-107">dispidImapDeleted</span><span class="sxs-lookup"><span data-stu-id="04a69-107">dispidImapDeleted</span></span>  <br/> |
|<span data-ttu-id="04a69-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="04a69-108">Property set:</span></span>  <br/> |<span data-ttu-id="04a69-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="04a69-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="04a69-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="04a69-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="04a69-111">0x00008570</span><span class="sxs-lookup"><span data-stu-id="04a69-111">0x00008570</span></span>  <br/> |
|<span data-ttu-id="04a69-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="04a69-112">Data type:</span></span>  <br/> |<span data-ttu-id="04a69-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="04a69-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="04a69-114">区域：</span><span class="sxs-lookup"><span data-stu-id="04a69-114">Area:</span></span>  <br/> |<span data-ttu-id="04a69-115">IMAP</span><span class="sxs-lookup"><span data-stu-id="04a69-115">IMAP</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="04a69-116">注解</span><span class="sxs-lookup"><span data-stu-id="04a69-116">Remarks</span></span>

<span data-ttu-id="04a69-117">如果设置为非零值，该项目已标记为删除。</span><span class="sxs-lookup"><span data-stu-id="04a69-117">If set to a nonzero value, the item has been marked for deletion.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="04a69-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="04a69-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="04a69-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="04a69-119">Protocol specifications</span></span>

<span data-ttu-id="04a69-120">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="04a69-120">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="04a69-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="04a69-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="04a69-122">头文件</span><span class="sxs-lookup"><span data-stu-id="04a69-122">Header files</span></span>

<span data-ttu-id="04a69-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="04a69-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="04a69-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="04a69-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="04a69-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04a69-125">See also</span></span>



[<span data-ttu-id="04a69-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="04a69-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="04a69-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="04a69-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="04a69-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="04a69-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="04a69-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="04a69-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

