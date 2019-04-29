---
title: PidTagContactAddressBookMultipleAddressFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookMultipleAddressFlags
api_type:
- HeaderDef
ms.assetid: ed3bc585-13f6-46a5-9e71-9c8513ddfc0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ecd795490d953f1aa237dfbd77585ba79c8b3234
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429248"
---
# <a name="pidtagcontactaddressbookmultipleaddressflags-canonical-property"></a><span data-ttu-id="29d59-103">PidTagContactAddressBookMultipleAddressFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="29d59-103">PidTagContactAddressBookMultipleAddressFlags Canonical Property</span></span>

  
  
<span data-ttu-id="29d59-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29d59-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29d59-105">包含指示提供程序是否将支持每个联系人项目的多个电子邮件地址的标志。</span><span class="sxs-lookup"><span data-stu-id="29d59-105">Contains flags that indicating whether the providers will support multiple email addresses per contact item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="29d59-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="29d59-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="29d59-107">PR_CONTAB_MULTI_ADDR_FLAGS</span><span class="sxs-lookup"><span data-stu-id="29d59-107">PR_CONTAB_MULTI_ADDR_FLAGS</span></span>  <br/> |
|<span data-ttu-id="29d59-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="29d59-108">Identifier:</span></span>  <br/> |<span data-ttu-id="29d59-109">0x6625</span><span class="sxs-lookup"><span data-stu-id="29d59-109">0x6625</span></span>  <br/> |
|<span data-ttu-id="29d59-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="29d59-110">Data type:</span></span>  <br/> |<span data-ttu-id="29d59-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="29d59-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="29d59-112">区域：</span><span class="sxs-lookup"><span data-stu-id="29d59-112">Area:</span></span>  <br/> |<span data-ttu-id="29d59-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="29d59-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="29d59-114">说明</span><span class="sxs-lookup"><span data-stu-id="29d59-114">Remarks</span></span>

<span data-ttu-id="29d59-115">如果此属性中的标志为 TRUE, 则提供程序将不包含没有电子邮件地址的联系人。</span><span class="sxs-lookup"><span data-stu-id="29d59-115">If the flags in this property are TRUE, the provider does not include contacts without email addresses.</span></span> <span data-ttu-id="29d59-116">只有主电子邮件地址将生效。</span><span class="sxs-lookup"><span data-stu-id="29d59-116">Only the primary email address will be honored.</span></span> <span data-ttu-id="29d59-117">这是联系人通讯簿配置文件部分的属性。</span><span class="sxs-lookup"><span data-stu-id="29d59-117">This is a property on a Contact Address Book profile section.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="29d59-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="29d59-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="29d59-119">头文件</span><span class="sxs-lookup"><span data-stu-id="29d59-119">Header files</span></span>

<span data-ttu-id="29d59-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="29d59-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="29d59-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="29d59-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="29d59-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="29d59-122">Mapitags.h</span></span>
  
> <span data-ttu-id="29d59-123">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="29d59-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="29d59-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29d59-124">See also</span></span>



[<span data-ttu-id="29d59-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="29d59-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="29d59-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="29d59-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="29d59-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="29d59-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="29d59-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="29d59-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

