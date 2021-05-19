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
ms.openlocfilehash: 790aa363522b9562f8f06c0806c87bba3816f566
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415787"
---
# <a name="pidlidimapdeleted-canonical-property"></a><span data-ttu-id="a7279-103">PidLidImapDeleted 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7279-103">PidLidImapDeleted Canonical Property</span></span>

  
  
<span data-ttu-id="a7279-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a7279-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a7279-105">表示 Internet 邮件访问协议 (IMAP) 标记为删除的项目。</span><span class="sxs-lookup"><span data-stu-id="a7279-105">Denotes Internet Mail Access Protocol (IMAP) items that are marked for deletion.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a7279-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a7279-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a7279-107">dispidImapDeleted</span><span class="sxs-lookup"><span data-stu-id="a7279-107">dispidImapDeleted</span></span>  <br/> |
|<span data-ttu-id="a7279-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="a7279-108">Property set:</span></span>  <br/> |<span data-ttu-id="a7279-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="a7279-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="a7279-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="a7279-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a7279-111">0x00008570</span><span class="sxs-lookup"><span data-stu-id="a7279-111">0x00008570</span></span>  <br/> |
|<span data-ttu-id="a7279-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a7279-112">Data type:</span></span>  <br/> |<span data-ttu-id="a7279-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="a7279-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="a7279-114">区域：</span><span class="sxs-lookup"><span data-stu-id="a7279-114">Area:</span></span>  <br/> |<span data-ttu-id="a7279-115">IMAP</span><span class="sxs-lookup"><span data-stu-id="a7279-115">IMAP</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a7279-116">备注</span><span class="sxs-lookup"><span data-stu-id="a7279-116">Remarks</span></span>

<span data-ttu-id="a7279-117">如果设置为非零值，则该项目已标记为删除。</span><span class="sxs-lookup"><span data-stu-id="a7279-117">If set to a nonzero value, the item has been marked for deletion.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a7279-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="a7279-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a7279-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="a7279-119">Protocol specifications</span></span>

<span data-ttu-id="a7279-120">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="a7279-120">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="a7279-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="a7279-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a7279-122">头文件</span><span class="sxs-lookup"><span data-stu-id="a7279-122">Header files</span></span>

<span data-ttu-id="a7279-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a7279-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="a7279-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a7279-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a7279-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7279-125">See also</span></span>



[<span data-ttu-id="a7279-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a7279-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a7279-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7279-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a7279-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a7279-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a7279-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a7279-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

