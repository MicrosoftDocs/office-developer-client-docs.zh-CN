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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433036"
---
# <a name="pidtagmemberentryid-canonical-property"></a><span data-ttu-id="64a55-103">PidTagMemberEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="64a55-103">PidTagMemberEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="64a55-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64a55-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64a55-105">包含 SACL 表成员中的系统访问控制列表 (目录) 标识符。</span><span class="sxs-lookup"><span data-stu-id="64a55-105">Contains the directory object entry identifier of a system access control list (SACL) table member.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="64a55-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="64a55-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="64a55-107">PR_MEMBER_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="64a55-107">PR_MEMBER_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="64a55-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="64a55-108">Identifier:</span></span>  <br/> |<span data-ttu-id="64a55-109">0x0FFF</span><span class="sxs-lookup"><span data-stu-id="64a55-109">0x0FFF</span></span>  <br/> |
|<span data-ttu-id="64a55-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="64a55-110">Data type:</span></span>  <br/> |<span data-ttu-id="64a55-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="64a55-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="64a55-112">区域：</span><span class="sxs-lookup"><span data-stu-id="64a55-112">Area:</span></span>  <br/> |<span data-ttu-id="64a55-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="64a55-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="64a55-114">备注</span><span class="sxs-lookup"><span data-stu-id="64a55-114">Remarks</span></span>

<span data-ttu-id="64a55-115">[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口使用此属性来唯一标识应用 SACL 的一个或多个角色。</span><span class="sxs-lookup"><span data-stu-id="64a55-115">This property is used by the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface to uniquely identify a person or role to whom the SACL applies.</span></span> <span data-ttu-id="64a55-116">在 SACL 表中创建成员后，无法更改 **ENTRYID。**</span><span class="sxs-lookup"><span data-stu-id="64a55-116">After a member is created in the SACL table, the **ENTRYID** cannot be changed.</span></span> <span data-ttu-id="64a55-117">若要更改它，您必须删除表成员，然后使用不同的 **ENTRYID** 重新创建它。</span><span class="sxs-lookup"><span data-stu-id="64a55-117">To change it, you must delete the table member and re-create it with a different **ENTRYID**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="64a55-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="64a55-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="64a55-119">头文件</span><span class="sxs-lookup"><span data-stu-id="64a55-119">Header files</span></span>

<span data-ttu-id="64a55-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="64a55-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="64a55-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="64a55-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="64a55-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="64a55-122">Mapitags.h</span></span>
  
> <span data-ttu-id="64a55-123">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="64a55-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="64a55-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64a55-124">See also</span></span>



[<span data-ttu-id="64a55-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="64a55-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="64a55-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="64a55-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="64a55-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="64a55-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="64a55-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="64a55-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

