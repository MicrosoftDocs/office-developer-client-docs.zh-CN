---
title: PidTagRulesTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: fc520720-8190-4dff-8f6c-1bebf7080b57
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 945dabec4ee34d38d2474c918e779d894f4a917c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778296"
---
# <a name="pidtagrulestable-canonical-property"></a><span data-ttu-id="263e6-103">PidTagRulesTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="263e6-103">PidTagRulesTable Canonical Property</span></span>

  
  
<span data-ttu-id="263e6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="263e6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="263e6-105">与所有规则应用于文件夹中包含的表。</span><span class="sxs-lookup"><span data-stu-id="263e6-105">Contains a table with all rules applied to a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="263e6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="263e6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="263e6-107">PR_RULES_TABLE</span><span class="sxs-lookup"><span data-stu-id="263e6-107">PR_RULES_TABLE</span></span>  <br/> |
|<span data-ttu-id="263e6-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="263e6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="263e6-109">0x3FE1</span><span class="sxs-lookup"><span data-stu-id="263e6-109">0x3FE1</span></span>  <br/> |
|<span data-ttu-id="263e6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="263e6-110">Data type:</span></span>  <br/> |<span data-ttu-id="263e6-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="263e6-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="263e6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="263e6-112">Area:</span></span>  <br/> |<span data-ttu-id="263e6-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="263e6-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="263e6-114">说明</span><span class="sxs-lookup"><span data-stu-id="263e6-114">Remarks</span></span>

<span data-ttu-id="263e6-115">此属性是位于 Exchange 服务器上具有规则的所有 folder 对象。</span><span class="sxs-lookup"><span data-stu-id="263e6-115">This property is present on all folder objects on an Exchange Server that have rules.</span></span> <span data-ttu-id="263e6-116">包含此属性的值用于读取和修改的规则。</span><span class="sxs-lookup"><span data-stu-id="263e6-116">Values included in this property are used for reading and modifying rules.</span></span> <span data-ttu-id="263e6-117">您可以使用具有**IID_IExchangeModifyTable**接口标识符[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法获取[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)接口到的文件夹的规则表。</span><span class="sxs-lookup"><span data-stu-id="263e6-117">You can use the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with the **IID_IExchangeModifyTable** interface identifier to obtain an [IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md) interface to the rules table on a folder.</span></span> <span data-ttu-id="263e6-118">您可以使用此接口读取和修改这些规则。</span><span class="sxs-lookup"><span data-stu-id="263e6-118">You can use this interface to read and modify those rules.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="263e6-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="263e6-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="263e6-120">头文件</span><span class="sxs-lookup"><span data-stu-id="263e6-120">Header files</span></span>

<span data-ttu-id="263e6-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="263e6-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="263e6-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="263e6-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="263e6-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="263e6-123">Mapitags.h</span></span>
  
> <span data-ttu-id="263e6-124">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="263e6-124">Contains definitions of properties listed as associated properties.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="263e6-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="263e6-125">See also</span></span>



[<span data-ttu-id="263e6-126">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="263e6-126">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
  
[<span data-ttu-id="263e6-127">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="263e6-127">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)


[<span data-ttu-id="263e6-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="263e6-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="263e6-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="263e6-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="263e6-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="263e6-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="263e6-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="263e6-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

