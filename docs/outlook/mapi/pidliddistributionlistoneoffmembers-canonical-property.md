---
title: PidLidDistributionListOneOffMembers 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidDistributionListOneOffMembers
api_type:
- COM
ms.assetid: 0b92e654-9e2d-4c2e-9a63-d5fac603b0c0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fed4395274cb790ab8ab7ecf0456d4ecb9ec0134
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335047"
---
# <a name="pidliddistributionlistoneoffmembers-canonical-property"></a><span data-ttu-id="489de-103">PidLidDistributionListOneOffMembers 规范属性</span><span class="sxs-lookup"><span data-stu-id="489de-103">PidLidDistributionListOneOffMembers Canonical Property</span></span>

  
  
<span data-ttu-id="489de-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="489de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="489de-105">指定与个人通讯组列表的成员对应的一次输入 Id 的列表。</span><span class="sxs-lookup"><span data-stu-id="489de-105">Specifies the list of one-off EntryIds that correspond to the members of the personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="489de-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="489de-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="489de-107">dispidDLOneOffMembers</span><span class="sxs-lookup"><span data-stu-id="489de-107">dispidDLOneOffMembers</span></span>  <br/> |
|<span data-ttu-id="489de-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="489de-108">Property set:</span></span>  <br/> |<span data-ttu-id="489de-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="489de-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="489de-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="489de-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="489de-111">0x00008054</span><span class="sxs-lookup"><span data-stu-id="489de-111">0x00008054</span></span>  <br/> |
|<span data-ttu-id="489de-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="489de-112">Data type:</span></span>  <br/> |<span data-ttu-id="489de-113">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="489de-113">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="489de-114">区域：</span><span class="sxs-lookup"><span data-stu-id="489de-114">Area:</span></span>  <br/> |<span data-ttu-id="489de-115">联系人</span><span class="sxs-lookup"><span data-stu-id="489de-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="489de-116">备注</span><span class="sxs-lookup"><span data-stu-id="489de-116">Remarks</span></span>

<span data-ttu-id="489de-117">这些一对一 EntryIds 封装个人通讯组列表成员的显示名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="489de-117">These one-off EntryIds encapsulate display names and email addresses of the personal distribution list members.</span></span>
  
<span data-ttu-id="489de-118">如果客户端或服务器设置此属性，则必须与 **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) 属性同步：对于 **dispidDLOneOffMembers** 属性中的每个条目 **，dispidDLMembers** 属性中必须在同一位置有一个条目。</span><span class="sxs-lookup"><span data-stu-id="489de-118">If the client or the server set this property, it must be synchronized with the **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) property: for each entry in the **dispidDLOneOffMembers** property, there must be an entry in the same position in the **dispidDLMembers** property.</span></span> 
  
<span data-ttu-id="489de-119">设置 **dispidDLOneOffMembers** 时，客户端或服务器必须确保其总大小小于 15，000 字节的大小。</span><span class="sxs-lookup"><span data-stu-id="489de-119">When setting **dispidDLOneOffMembers**, the client or the server must ensure that its total size is less than 15,000 bytes in size.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="489de-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="489de-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="489de-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="489de-121">Protocol specifications</span></span>

<span data-ttu-id="489de-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="489de-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="489de-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="489de-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="489de-124">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="489de-124">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="489de-125">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="489de-125">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="489de-126">头文件</span><span class="sxs-lookup"><span data-stu-id="489de-126">Header files</span></span>

<span data-ttu-id="489de-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="489de-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="489de-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="489de-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="489de-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="489de-129">See also</span></span>



[<span data-ttu-id="489de-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="489de-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="489de-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="489de-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="489de-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="489de-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="489de-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="489de-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

