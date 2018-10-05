---
title: PidLidEmail3OriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3OriginalEntryId
api_type:
- COM
ms.assetid: b290d4a4-8d70-4656-9254-191c5179662f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fd8e600f0acb16d23690fc16245988a53e22c7c8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386780"
---
# <a name="pidlidemail3originalentryid-canonical-property"></a><span data-ttu-id="43bec-103">PidLidEmail3OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="43bec-103">PidLidEmail3OriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="43bec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="43bec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="43bec-105">指定对象对应于第三个电子邮件地址的**EntryId** 。</span><span class="sxs-lookup"><span data-stu-id="43bec-105">Specifies the **EntryId** of the object that corresponds to the third email address.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="43bec-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="43bec-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="43bec-107">dispidEmail3OriginalEntryID</span><span class="sxs-lookup"><span data-stu-id="43bec-107">dispidEmail3OriginalEntryID</span></span>  <br/> |
|<span data-ttu-id="43bec-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="43bec-108">Property set:</span></span>  <br/> |<span data-ttu-id="43bec-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="43bec-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="43bec-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="43bec-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="43bec-111">0x000080A5</span><span class="sxs-lookup"><span data-stu-id="43bec-111">0x000080A5</span></span>  <br/> |
|<span data-ttu-id="43bec-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="43bec-112">Data type:</span></span>  <br/> |<span data-ttu-id="43bec-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="43bec-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="43bec-114">区域：</span><span class="sxs-lookup"><span data-stu-id="43bec-114">Area:</span></span>  <br/> |<span data-ttu-id="43bec-115">联系人</span><span class="sxs-lookup"><span data-stu-id="43bec-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="43bec-116">说明</span><span class="sxs-lookup"><span data-stu-id="43bec-116">Remarks</span></span>

<span data-ttu-id="43bec-117">此属性的值必须是此电子通讯一次性**EntryId**或有效的通讯簿对象**EntryId**。</span><span class="sxs-lookup"><span data-stu-id="43bec-117">The value of this property must be either a one-off **EntryId** for this electronic address or a valid Address Book object **EntryId**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="43bec-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="43bec-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="43bec-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="43bec-119">Protocol specifications</span></span>

<span data-ttu-id="43bec-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43bec-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43bec-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="43bec-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="43bec-122">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43bec-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43bec-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="43bec-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="43bec-124">头文件</span><span class="sxs-lookup"><span data-stu-id="43bec-124">Header files</span></span>

<span data-ttu-id="43bec-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="43bec-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="43bec-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="43bec-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43bec-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43bec-127">See also</span></span>



[<span data-ttu-id="43bec-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="43bec-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="43bec-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="43bec-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="43bec-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="43bec-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="43bec-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43bec-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

