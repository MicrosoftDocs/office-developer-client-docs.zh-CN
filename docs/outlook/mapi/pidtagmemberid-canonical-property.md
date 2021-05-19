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
ms.openlocfilehash: b5d1d4456856f1640bbed8589fc0583060cd2520
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342635"
---
# <a name="pidtagmemberid-canonical-property"></a><span data-ttu-id="b1625-103">PidTagMemberId 规范属性</span><span class="sxs-lookup"><span data-stu-id="b1625-103">PidTagMemberId Canonical Property</span></span>

  
  
<span data-ttu-id="b1625-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1625-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1625-105">包含对文件夹或邮箱具有所述权限的表Microsoft Exchange Server标识符。</span><span class="sxs-lookup"><span data-stu-id="b1625-105">Contains the identifier of a table member that has the described rights on a Microsoft Exchange Server folder or mailbox.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b1625-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b1625-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b1625-107">PR_MEMBER_ID</span><span class="sxs-lookup"><span data-stu-id="b1625-107">PR_MEMBER_ID</span></span>  <br/> |
|<span data-ttu-id="b1625-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b1625-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b1625-109">0x6671</span><span class="sxs-lookup"><span data-stu-id="b1625-109">0x6671</span></span>  <br/> |
|<span data-ttu-id="b1625-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b1625-110">Data type:</span></span>  <br/> |<span data-ttu-id="b1625-111">PT_I8</span><span class="sxs-lookup"><span data-stu-id="b1625-111">PT_I8</span></span>  <br/> |
|<span data-ttu-id="b1625-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b1625-112">Area:</span></span>  <br/> |<span data-ttu-id="b1625-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="b1625-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b1625-114">备注</span><span class="sxs-lookup"><span data-stu-id="b1625-114">Remarks</span></span>

<span data-ttu-id="b1625-115">此属性返回表的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b1625-115">This property returns an identifier unique to the table.</span></span> <span data-ttu-id="b1625-116">目录用户标识符与每个成员标识符相关联，由此属性指定。</span><span class="sxs-lookup"><span data-stu-id="b1625-116">A directory user identifier is associated with each member identifier and is given by this property.</span></span> <span data-ttu-id="b1625-117">[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口使用此属性检索对文件夹具有显式权限的成员的目录条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b1625-117">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to retrieve the directory entry identifier of a member with explicit rights on a folder.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b1625-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b1625-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b1625-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b1625-119">Protocol specifications</span></span>

<span data-ttu-id="b1625-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1625-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1625-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="b1625-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b1625-122">[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1625-122">[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1625-123">处理对服务器上存储的文件夹权限列表的检索。</span><span class="sxs-lookup"><span data-stu-id="b1625-123">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b1625-124">头文件</span><span class="sxs-lookup"><span data-stu-id="b1625-124">Header files</span></span>

<span data-ttu-id="b1625-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b1625-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="b1625-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b1625-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="b1625-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b1625-127">Mapitags.h</span></span>
  
> <span data-ttu-id="b1625-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b1625-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b1625-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1625-129">See also</span></span>



[<span data-ttu-id="b1625-130">PidTagMemberEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="b1625-130">PidTagMemberEntryId Canonical Property</span></span>](pidtagmemberentryid-canonical-property.md)


[<span data-ttu-id="b1625-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b1625-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b1625-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b1625-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b1625-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b1625-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b1625-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b1625-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

