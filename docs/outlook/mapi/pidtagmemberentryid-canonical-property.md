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
ms.openlocfilehash: 3139f7cc60d19048fb17c64101f279ce377e9b26
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777846"
---
# <a name="pidtagmemberentryid-canonical-property"></a><span data-ttu-id="1f309-103">PidTagMemberEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f309-103">PidTagMemberEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="1f309-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1f309-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1f309-105">包含系统访问控制列表 (SACL) 表成员的目录对象条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1f309-105">Contains the directory object entry identifier of a system access control list (SACL) table member.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1f309-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1f309-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1f309-107">PR_MEMBER_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="1f309-107">PR_MEMBER_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="1f309-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1f309-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1f309-109">0x0FFF</span><span class="sxs-lookup"><span data-stu-id="1f309-109">0x0FFF</span></span>  <br/> |
|<span data-ttu-id="1f309-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1f309-110">Data type:</span></span>  <br/> |<span data-ttu-id="1f309-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1f309-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="1f309-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1f309-112">Area:</span></span>  <br/> |<span data-ttu-id="1f309-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="1f309-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f309-114">说明</span><span class="sxs-lookup"><span data-stu-id="1f309-114">Remarks</span></span>

<span data-ttu-id="1f309-115">此属性由[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口用于唯一标识的人员或角色 SACL 应用于其。</span><span class="sxs-lookup"><span data-stu-id="1f309-115">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to uniquely identify a person or role to whom the SACL applies.</span></span> <span data-ttu-id="1f309-116">SACL 表中创建的成员后，不能更改**ENTRYID** 。</span><span class="sxs-lookup"><span data-stu-id="1f309-116">After a member is created in the SACL table, the **ENTRYID** cannot be changed.</span></span> <span data-ttu-id="1f309-117">若要更改它，必须删除表成员，并使用不同的**ENTRYID**重新创建它。</span><span class="sxs-lookup"><span data-stu-id="1f309-117">To change it, you must delete the table member and re-create it with a different **ENTRYID**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1f309-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="1f309-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1f309-119">头文件</span><span class="sxs-lookup"><span data-stu-id="1f309-119">Header files</span></span>

<span data-ttu-id="1f309-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1f309-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="1f309-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1f309-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="1f309-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1f309-122">Mapitags.h</span></span>
  
> <span data-ttu-id="1f309-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1f309-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f309-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f309-124">See also</span></span>



[<span data-ttu-id="1f309-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1f309-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1f309-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f309-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1f309-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1f309-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1f309-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f309-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

