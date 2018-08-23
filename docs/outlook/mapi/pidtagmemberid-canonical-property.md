---
title: PidTagMemberId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberId
api_type:
- HeaderDef
ms.assetid: 64faef3c-27b2-49d2-9d0c-8b9d33f1cb71
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: caf1cb2e16c298af452e638631293379fdd68b10
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589782"
---
# <a name="pidtagmemberid-canonical-property"></a><span data-ttu-id="43696-103">PidTagMemberId 规范属性</span><span class="sxs-lookup"><span data-stu-id="43696-103">PidTagMemberId Canonical Property</span></span>

  
  
<span data-ttu-id="43696-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="43696-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="43696-105">包含在 Microsoft Exchange Server 文件夹或邮箱上具有所述的权限表成员标识符。</span><span class="sxs-lookup"><span data-stu-id="43696-105">Contains the identifier of a table member that has the described rights on a Microsoft Exchange Server folder or mailbox.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="43696-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="43696-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="43696-107">PR_MEMBER_ID</span><span class="sxs-lookup"><span data-stu-id="43696-107">PR_MEMBER_ID</span></span>  <br/> |
|<span data-ttu-id="43696-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="43696-108">Identifier:</span></span>  <br/> |<span data-ttu-id="43696-109">0x6671</span><span class="sxs-lookup"><span data-stu-id="43696-109">0x6671</span></span>  <br/> |
|<span data-ttu-id="43696-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="43696-110">Data type:</span></span>  <br/> |<span data-ttu-id="43696-111">PT_I8</span><span class="sxs-lookup"><span data-stu-id="43696-111">PT_I8</span></span>  <br/> |
|<span data-ttu-id="43696-112">区域：</span><span class="sxs-lookup"><span data-stu-id="43696-112">Area:</span></span>  <br/> |<span data-ttu-id="43696-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="43696-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="43696-114">注解</span><span class="sxs-lookup"><span data-stu-id="43696-114">Remarks</span></span>

<span data-ttu-id="43696-115">此属性返回的标识符到表唯一。</span><span class="sxs-lookup"><span data-stu-id="43696-115">This property returns an identifier unique to the table.</span></span> <span data-ttu-id="43696-116">目录用户标识符与每个成员标识符相关联，并由该属性。</span><span class="sxs-lookup"><span data-stu-id="43696-116">A directory user identifier is associated with each member identifier and is given by this property.</span></span> <span data-ttu-id="43696-117">此属性由[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口用于检索具有显式权限的文件夹的成员的目录项标识符。</span><span class="sxs-lookup"><span data-stu-id="43696-117">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to retrieve the directory entry identifier of a member with explicit rights on a folder.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="43696-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="43696-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="43696-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="43696-119">Protocol specifications</span></span>

<span data-ttu-id="43696-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43696-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43696-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="43696-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="43696-122">[[MS OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43696-122">[[MS-OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43696-123">处理检索存储在服务器的文件夹的权限列表。</span><span class="sxs-lookup"><span data-stu-id="43696-123">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="43696-124">头文件</span><span class="sxs-lookup"><span data-stu-id="43696-124">Header files</span></span>

<span data-ttu-id="43696-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="43696-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="43696-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="43696-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="43696-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="43696-127">Mapitags.h</span></span>
  
> <span data-ttu-id="43696-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="43696-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43696-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43696-129">See also</span></span>



[<span data-ttu-id="43696-130">PidTagMemberEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="43696-130">PidTagMemberEntryId Canonical Property</span></span>](pidtagmemberentryid-canonical-property.md)


[<span data-ttu-id="43696-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="43696-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="43696-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="43696-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="43696-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="43696-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="43696-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43696-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

