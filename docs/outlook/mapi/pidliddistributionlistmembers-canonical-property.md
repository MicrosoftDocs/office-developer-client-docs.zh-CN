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
ms.openlocfilehash: f04d1593e2a13a2bfc23412340d7eb9f38f5d9ef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335068"
---
# <a name="pidliddistributionlistmembers-canonical-property"></a><span data-ttu-id="0691d-103">PidLidDistributionListMembers 规范属性</span><span class="sxs-lookup"><span data-stu-id="0691d-103">PidLidDistributionListMembers Canonical Property</span></span>

  
  
<span data-ttu-id="0691d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0691d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0691d-105">指定与个人通讯组列表的成员对应的对象的 EntryIds 列表。</span><span class="sxs-lookup"><span data-stu-id="0691d-105">Specifies the list of EntryIds of the objects that correspond to the members of the personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0691d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0691d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0691d-107">dispidDLMembers</span><span class="sxs-lookup"><span data-stu-id="0691d-107">dispidDLMembers</span></span>  <br/> |
|<span data-ttu-id="0691d-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="0691d-108">Property set:</span></span>  <br/> |<span data-ttu-id="0691d-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="0691d-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="0691d-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="0691d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0691d-111">0x00008055</span><span class="sxs-lookup"><span data-stu-id="0691d-111">0x00008055</span></span>  <br/> |
|<span data-ttu-id="0691d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0691d-112">Data type:</span></span>  <br/> |<span data-ttu-id="0691d-113">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="0691d-113">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="0691d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="0691d-114">Area:</span></span>  <br/> |<span data-ttu-id="0691d-115">联系人</span><span class="sxs-lookup"><span data-stu-id="0691d-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0691d-116">备注</span><span class="sxs-lookup"><span data-stu-id="0691d-116">Remarks</span></span>

<span data-ttu-id="0691d-117">个人通讯组列表的成员可以是其他个人通讯组列表、联系人中包含的电子地址、全局地址列表用户或通讯组列表，或者是一次电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0691d-117">Members of the personal distribution list can be other personal distribution lists, electronic addresses contained in a contact, Global Address List users or distribution lists, or one-off email addresses.</span></span> <span data-ttu-id="0691d-118">每个 EntryId 的格式必须是 [[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx) 中指定的一次 EntryId 或包装的 EntryId。</span><span class="sxs-lookup"><span data-stu-id="0691d-118">The format of each EntryId must be either a one-off EntryId, as specified in [[MS-OXCDATA],](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx) or a wrapped EntryId.</span></span> 
  
<span data-ttu-id="0691d-119">设置此属性时，客户端或服务器必须确保其总大小小于 15，000 字节。</span><span class="sxs-lookup"><span data-stu-id="0691d-119">When setting this property, the client or the server must ensure its total size is less than 15,000 bytes.</span></span>
  
<span data-ttu-id="0691d-120">此属性指定与个人通讯组列表的成员对应的一次 EntryId 的列表。</span><span class="sxs-lookup"><span data-stu-id="0691d-120">This property specifies the list of one-off EntryIds that correspond to the members of the personal distribution list.</span></span> <span data-ttu-id="0691d-121">这些一对一 EntryIds 封装个人通讯组列表成员的显示名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0691d-121">These one-off EntryIds encapsulate display names and email addresses of the personal distribution list members.</span></span>
  
<span data-ttu-id="0691d-122">如果客户端或服务器设置此属性，则它必须与 **dispidDLOneOffMembers** ([PidLidDistributionListOneOffMembers](pidliddistributionlistoneoffmembers-canonical-property.md)) 属性中每个条目的此属性 **dispidDLMembers** 同步 **，dispidDLOneOffMembers** 中必须在同一位置有一个条目。</span><span class="sxs-lookup"><span data-stu-id="0691d-122">If the client or the server set this property, it must be synchronized with this property **dispidDLMembers** for each entry in the **dispidDLOneOffMembers** ([PidLidDistributionListOneOffMembers](pidliddistributionlistoneoffmembers-canonical-property.md)) property, there must be an entry in the same position in the **dispidDLOneOffMembers**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0691d-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="0691d-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0691d-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="0691d-124">Protocol specifications</span></span>

<span data-ttu-id="0691d-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0691d-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0691d-126">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="0691d-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0691d-127">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0691d-127">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0691d-128">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0691d-128">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0691d-129">头文件</span><span class="sxs-lookup"><span data-stu-id="0691d-129">Header files</span></span>

<span data-ttu-id="0691d-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0691d-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="0691d-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0691d-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0691d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0691d-132">See also</span></span>



[<span data-ttu-id="0691d-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0691d-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0691d-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0691d-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0691d-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0691d-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0691d-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0691d-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

