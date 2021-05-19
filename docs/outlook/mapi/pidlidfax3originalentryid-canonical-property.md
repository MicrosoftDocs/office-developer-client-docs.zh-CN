---
title: PidLidFax3OriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFax3OriginalEntryId
api_type:
- COM
ms.assetid: afccacf1-0b8b-410c-b701-bf1bd8dcca99
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a77ab1fcebd729f6463a3480f1b217cd6e6041c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355872"
---
# <a name="pidlidfax3originalentryid-canonical-property"></a><span data-ttu-id="c7726-103">PidLidFax3OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="c7726-103">PidLidFax3OriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="c7726-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7726-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7726-105">指定联系人的其他传真地址的原始 EntryID。</span><span class="sxs-lookup"><span data-stu-id="c7726-105">Specifies the original EntryID of the contact's other fax address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c7726-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c7726-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c7726-107">dispidFax3OriginalEntryID</span><span class="sxs-lookup"><span data-stu-id="c7726-107">dispidFax3OriginalEntryID</span></span>  <br/> |
|<span data-ttu-id="c7726-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="c7726-108">Property set:</span></span>  <br/> |<span data-ttu-id="c7726-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="c7726-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="c7726-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="c7726-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="c7726-111">0x000080D5</span><span class="sxs-lookup"><span data-stu-id="c7726-111">0x000080D5</span></span>  <br/> |
|<span data-ttu-id="c7726-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c7726-112">Data type:</span></span>  <br/> |<span data-ttu-id="c7726-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="c7726-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="c7726-114">区域：</span><span class="sxs-lookup"><span data-stu-id="c7726-114">Area:</span></span>  <br/> |<span data-ttu-id="c7726-115">联系人</span><span class="sxs-lookup"><span data-stu-id="c7726-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c7726-116">备注</span><span class="sxs-lookup"><span data-stu-id="c7726-116">Remarks</span></span>

<span data-ttu-id="c7726-117">此属性（如果存在）必须指定对应于此传真地址的一次使用 EntryId。</span><span class="sxs-lookup"><span data-stu-id="c7726-117">This property, if present, must specify the one-off EntryId that corresponds to this fax address.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c7726-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="c7726-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c7726-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="c7726-119">Protocol specifications</span></span>

<span data-ttu-id="c7726-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c7726-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c7726-121">提供属性集定义和对相关协议Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="c7726-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c7726-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c7726-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c7726-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c7726-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c7726-124">头文件</span><span class="sxs-lookup"><span data-stu-id="c7726-124">Header files</span></span>

<span data-ttu-id="c7726-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c7726-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="c7726-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c7726-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c7726-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7726-127">See also</span></span>



[<span data-ttu-id="c7726-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c7726-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c7726-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c7726-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c7726-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c7726-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c7726-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c7726-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

