---
title: PidTagMemberEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberEntryId
api_type:
- HeaderDef
ms.assetid: b1e166fd-7e15-4371-8510-63001317fb90
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 83a645b49e5bb48051bbaedb26058d2da053348b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342495"
---
# <a name="pidtagmemberentryid-canonical-property"></a><span data-ttu-id="79070-103">PidTagMemberEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="79070-103">PidTagMemberEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="79070-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79070-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79070-105">包含系统访问控制列表 (SACL) 表成员的目录对象条目标识符。</span><span class="sxs-lookup"><span data-stu-id="79070-105">Contains the directory object entry identifier of a system access control list (SACL) table member.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="79070-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="79070-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="79070-107">PR_MEMBER_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="79070-107">PR_MEMBER_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="79070-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="79070-108">Identifier:</span></span>  <br/> |<span data-ttu-id="79070-109">0x0FFF</span><span class="sxs-lookup"><span data-stu-id="79070-109">0x0FFF</span></span>  <br/> |
|<span data-ttu-id="79070-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="79070-110">Data type:</span></span>  <br/> |<span data-ttu-id="79070-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="79070-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="79070-112">区域：</span><span class="sxs-lookup"><span data-stu-id="79070-112">Area:</span></span>  <br/> |<span data-ttu-id="79070-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="79070-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="79070-114">注解</span><span class="sxs-lookup"><span data-stu-id="79070-114">Remarks</span></span>

<span data-ttu-id="79070-115">[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口使用此属性来唯一标识对其应用了 SACL 的个人或角色。</span><span class="sxs-lookup"><span data-stu-id="79070-115">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to uniquely identify a person or role to whom the SACL applies.</span></span> <span data-ttu-id="79070-116">在 SACL 表中创建成员后, 不能更改**ENTRYID** 。</span><span class="sxs-lookup"><span data-stu-id="79070-116">After a member is created in the SACL table, the **ENTRYID** cannot be changed.</span></span> <span data-ttu-id="79070-117">若要对其进行更改, 必须删除该表成员并使用不同的**ENTRYID**重新创建它。</span><span class="sxs-lookup"><span data-stu-id="79070-117">To change it, you must delete the table member and re-create it with a different **ENTRYID**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="79070-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="79070-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="79070-119">头文件</span><span class="sxs-lookup"><span data-stu-id="79070-119">Header files</span></span>

<span data-ttu-id="79070-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="79070-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="79070-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="79070-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="79070-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="79070-122">Mapitags.h</span></span>
  
> <span data-ttu-id="79070-123">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="79070-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="79070-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79070-124">See also</span></span>



[<span data-ttu-id="79070-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="79070-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="79070-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="79070-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="79070-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="79070-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="79070-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="79070-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

