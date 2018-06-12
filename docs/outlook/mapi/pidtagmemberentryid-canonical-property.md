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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3139f7cc60d19048fb17c64101f279ce377e9b26
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777846"
---
# <a name="pidtagmemberentryid-canonical-property"></a><span data-ttu-id="d9e27-103">PidTagMemberEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="d9e27-103">PidTagMemberEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="d9e27-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d9e27-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d9e27-105">包含系统访问控制列表 (SACL) 表成员的目录对象条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d9e27-105">Contains the directory object entry identifier of a system access control list (SACL) table member.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d9e27-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="d9e27-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d9e27-107">PR_MEMBER_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d9e27-107">PR_MEMBER_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="d9e27-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d9e27-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d9e27-109">0x0FFF</span><span class="sxs-lookup"><span data-stu-id="d9e27-109">0x0FFF</span></span>  <br/> |
|<span data-ttu-id="d9e27-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d9e27-110">Data type:</span></span>  <br/> |<span data-ttu-id="d9e27-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d9e27-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d9e27-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d9e27-112">Area:</span></span>  <br/> |<span data-ttu-id="d9e27-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="d9e27-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d9e27-114">备注</span><span class="sxs-lookup"><span data-stu-id="d9e27-114">Remarks</span></span>

<span data-ttu-id="d9e27-115">此属性由[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口用于唯一标识的人员或角色 SACL 应用于其。</span><span class="sxs-lookup"><span data-stu-id="d9e27-115">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to uniquely identify a person or role to whom the SACL applies.</span></span> <span data-ttu-id="d9e27-116">SACL 表中创建的成员后，不能更改**ENTRYID** 。</span><span class="sxs-lookup"><span data-stu-id="d9e27-116">After a member is created in the SACL table, the **ENTRYID** cannot be changed.</span></span> <span data-ttu-id="d9e27-117">若要更改它，必须删除表成员，并使用不同的**ENTRYID**重新创建它。</span><span class="sxs-lookup"><span data-stu-id="d9e27-117">To change it, you must delete the table member and re-create it with a different **ENTRYID**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d9e27-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="d9e27-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d9e27-119">头文件</span><span class="sxs-lookup"><span data-stu-id="d9e27-119">Header files</span></span>

<span data-ttu-id="d9e27-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d9e27-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="d9e27-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d9e27-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="d9e27-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d9e27-122">Mapitags.h</span></span>
  
> <span data-ttu-id="d9e27-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d9e27-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9e27-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9e27-124">See also</span></span>



[<span data-ttu-id="d9e27-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d9e27-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d9e27-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d9e27-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d9e27-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d9e27-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d9e27-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d9e27-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

