---
title: PidTagContactAddressBookStoreSupportMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookStoreSupportMask
api_type:
- HeaderDef
ms.assetid: 34f649c8-29bf-470f-9b05-31b69d069259
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fb40e2c191056fe164c6a06bfdcf4b8e3d6eb92c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434436"
---
# <a name="pidtagcontactaddressbookstoresupportmask-canonical-property"></a><span data-ttu-id="6a261-103">PidTagContactAddressBookStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a261-103">PidTagContactAddressBookStoreSupportMask Canonical Property</span></span>

  
  
<span data-ttu-id="6a261-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a261-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a261-105">包含从包含 "联系人" 文件夹的存储区获取的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagcontactaddressbookstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="6a261-105">Contains the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagcontactaddressbookstoresupportmask-canonical-property.md)) property obtained from the store that contains the Contacts folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6a261-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6a261-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6a261-107">PR_CONTAB_STORE_SUPPORT_MASK</span><span class="sxs-lookup"><span data-stu-id="6a261-107">PR_CONTAB_STORE_SUPPORT_MASK</span></span>  <br/> |
|<span data-ttu-id="6a261-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6a261-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6a261-109">0x6611</span><span class="sxs-lookup"><span data-stu-id="6a261-109">0x6611</span></span>  <br/> |
|<span data-ttu-id="6a261-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6a261-110">Data type:</span></span>  <br/> |<span data-ttu-id="6a261-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6a261-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6a261-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6a261-112">Area:</span></span>  <br/> |<span data-ttu-id="6a261-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="6a261-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a261-114">说明</span><span class="sxs-lookup"><span data-stu-id="6a261-114">Remarks</span></span>

<span data-ttu-id="6a261-115">联系人通讯簿提供程序使用此属性来评估存储区支持的功能是否够用。</span><span class="sxs-lookup"><span data-stu-id="6a261-115">The Contact Address Book provider uses this property to evaluate the adequacy of the store's supported features.</span></span> <span data-ttu-id="6a261-116">这是联系人通讯簿容器的属性, 以及联系人通讯簿容器表中的列。</span><span class="sxs-lookup"><span data-stu-id="6a261-116">This is a property on a Contact Address Book container, and a column in the table of Contact Address Book containers.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6a261-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="6a261-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="6a261-118">头文件</span><span class="sxs-lookup"><span data-stu-id="6a261-118">Header files</span></span>

<span data-ttu-id="6a261-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6a261-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="6a261-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6a261-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="6a261-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6a261-121">Mapitags.h</span></span>
  
> <span data-ttu-id="6a261-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6a261-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a261-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a261-123">See also</span></span>



[<span data-ttu-id="6a261-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6a261-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6a261-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a261-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6a261-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6a261-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6a261-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a261-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

