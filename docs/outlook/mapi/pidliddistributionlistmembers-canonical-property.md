---
title: PidLidDistributionListMembers 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidDistributionListMembers
api_type:
- COM
ms.assetid: 029767ab-de72-4402-9cc3-31b006591042
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c27513474048e9805bc29116aa094bc47f8f0cae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776740"
---
# <a name="pidliddistributionlistmembers-canonical-property"></a><span data-ttu-id="e2090-103">PidLidDistributionListMembers 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2090-103">PidLidDistributionListMembers Canonical Property</span></span>

  
  
<span data-ttu-id="e2090-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e2090-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e2090-105">指定对应的个人通讯组列表成员的对象的 Entryid 的列表。</span><span class="sxs-lookup"><span data-stu-id="e2090-105">Specifies the list of EntryIds of the objects that correspond to the members of the personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e2090-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e2090-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e2090-107">dispidDLMembers</span><span class="sxs-lookup"><span data-stu-id="e2090-107">dispidDLMembers</span></span>  <br/> |
|<span data-ttu-id="e2090-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="e2090-108">Property set:</span></span>  <br/> |<span data-ttu-id="e2090-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="e2090-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="e2090-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="e2090-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e2090-111">0x00008055</span><span class="sxs-lookup"><span data-stu-id="e2090-111">0x00008055</span></span>  <br/> |
|<span data-ttu-id="e2090-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e2090-112">Data type:</span></span>  <br/> |<span data-ttu-id="e2090-113">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="e2090-113">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="e2090-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e2090-114">Area:</span></span>  <br/> |<span data-ttu-id="e2090-115">联系人</span><span class="sxs-lookup"><span data-stu-id="e2090-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e2090-116">说明</span><span class="sxs-lookup"><span data-stu-id="e2090-116">Remarks</span></span>

<span data-ttu-id="e2090-117">个人通讯组列表中的成员可以是其他个人通讯组列表、 联系人、 全局地址列表用户或通讯组列表或一次性电子邮件地址中包含的电子地址。</span><span class="sxs-lookup"><span data-stu-id="e2090-117">Members of the personal distribution list can be other personal distribution lists, electronic addresses contained in a contact, Global Address List users or distribution lists, or one-off email addresses.</span></span> <span data-ttu-id="e2090-118">每个 EntryId 的格式必须是一次性的 EntryId， [[MS-OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)中指定或换行的 EntryId。</span><span class="sxs-lookup"><span data-stu-id="e2090-118">The format of each EntryId must be either a one-off EntryId, as specified in [[MS-OXCDATA],](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx) or a wrapped EntryId.</span></span> 
  
<span data-ttu-id="e2090-119">设置此属性时，客户端或服务器必须确保其总大小小于 15,000 个字节。</span><span class="sxs-lookup"><span data-stu-id="e2090-119">When setting this property, the client or the server must ensure its total size is less than 15,000 bytes.</span></span>
  
<span data-ttu-id="e2090-120">此属性指定的一次性 Entryid 对应的个人通讯组列表成员的列表。</span><span class="sxs-lookup"><span data-stu-id="e2090-120">This property specifies the list of one-off EntryIds that correspond to the members of the personal distribution list.</span></span> <span data-ttu-id="e2090-121">这些一次性 Entryid 封装的显示名称和个人通讯组列表成员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e2090-121">These one-off EntryIds encapsulate display names and email addresses of the personal distribution list members.</span></span>
  
<span data-ttu-id="e2090-122">如果客户端或服务器设置该属性，它必须为每个项的**dispidDLOneOffMembers** ([PidLidDistributionListOneOffMembers](pidliddistributionlistoneoffmembers-canonical-property.md)) 属性中此属性**dispidDLMembers**与同步，必须有中的条目**dispidDLOneOffMembers**中的相同位置。</span><span class="sxs-lookup"><span data-stu-id="e2090-122">If the client or the server set this property, it must be synchronized with this property **dispidDLMembers** for each entry in the **dispidDLOneOffMembers** ([PidLidDistributionListOneOffMembers](pidliddistributionlistoneoffmembers-canonical-property.md)) property, there must be an entry in the same position in the **dispidDLOneOffMembers**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e2090-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="e2090-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e2090-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="e2090-124">Protocol specifications</span></span>

<span data-ttu-id="e2090-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2090-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2090-126">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e2090-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e2090-127">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2090-127">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2090-128">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e2090-128">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e2090-129">头文件</span><span class="sxs-lookup"><span data-stu-id="e2090-129">Header files</span></span>

<span data-ttu-id="e2090-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e2090-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="e2090-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e2090-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e2090-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2090-132">See also</span></span>



[<span data-ttu-id="e2090-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e2090-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e2090-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2090-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e2090-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e2090-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e2090-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e2090-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

