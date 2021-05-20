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
ms.openlocfilehash: e1c670cd566e838104ae3d5480c2297f8632d899
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428499"
---
# <a name="pidtagrulestable-canonical-property"></a><span data-ttu-id="98a5a-103">PidTagRulesTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="98a5a-103">PidTagRulesTable Canonical Property</span></span>

  
  
<span data-ttu-id="98a5a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="98a5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="98a5a-105">包含一个表，该表包含应用于文件夹的所有规则。</span><span class="sxs-lookup"><span data-stu-id="98a5a-105">Contains a table with all rules applied to a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="98a5a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="98a5a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="98a5a-107">PR_RULES_TABLE</span><span class="sxs-lookup"><span data-stu-id="98a5a-107">PR_RULES_TABLE</span></span>  <br/> |
|<span data-ttu-id="98a5a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="98a5a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="98a5a-109">0x3FE1</span><span class="sxs-lookup"><span data-stu-id="98a5a-109">0x3FE1</span></span>  <br/> |
|<span data-ttu-id="98a5a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="98a5a-110">Data type:</span></span>  <br/> |<span data-ttu-id="98a5a-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="98a5a-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="98a5a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="98a5a-112">Area:</span></span>  <br/> |<span data-ttu-id="98a5a-113">服务器端规则</span><span class="sxs-lookup"><span data-stu-id="98a5a-113">Server Side Rules</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="98a5a-114">备注</span><span class="sxs-lookup"><span data-stu-id="98a5a-114">Remarks</span></span>

<span data-ttu-id="98a5a-115">此属性存在于具有规则的文件夹Exchange Server上的所有文件夹对象上。</span><span class="sxs-lookup"><span data-stu-id="98a5a-115">This property is present on all folder objects on an Exchange Server that have rules.</span></span> <span data-ttu-id="98a5a-116">此属性中包含的值用于读取和修改规则。</span><span class="sxs-lookup"><span data-stu-id="98a5a-116">Values included in this property are used for reading and modifying rules.</span></span> <span data-ttu-id="98a5a-117">可以将 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法与 **IID_IExchangeModifyTable** 接口标识符一同使用，以获取文件夹上规则表的 [IExchangeModifyTable ： IUnknown](iexchangemodifytableiunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="98a5a-117">You can use the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with the **IID_IExchangeModifyTable** interface identifier to obtain an [IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md) interface to the rules table on a folder.</span></span> <span data-ttu-id="98a5a-118">您可以使用此接口读取和修改这些规则。</span><span class="sxs-lookup"><span data-stu-id="98a5a-118">You can use this interface to read and modify those rules.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="98a5a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="98a5a-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="98a5a-120">头文件</span><span class="sxs-lookup"><span data-stu-id="98a5a-120">Header files</span></span>

<span data-ttu-id="98a5a-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="98a5a-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="98a5a-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="98a5a-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="98a5a-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="98a5a-123">Mapitags.h</span></span>
  
> <span data-ttu-id="98a5a-124">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="98a5a-124">Contains definitions of properties listed as associated properties.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="98a5a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98a5a-125">See also</span></span>



[<span data-ttu-id="98a5a-126">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="98a5a-126">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
  
[<span data-ttu-id="98a5a-127">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="98a5a-127">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)


[<span data-ttu-id="98a5a-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="98a5a-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="98a5a-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="98a5a-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="98a5a-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="98a5a-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="98a5a-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="98a5a-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

