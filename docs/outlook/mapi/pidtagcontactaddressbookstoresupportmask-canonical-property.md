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
ms.openlocfilehash: 5cd113c263c97ba306fcf7bf97c750e710eac922
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777448"
---
# <a name="pidtagcontactaddressbookstoresupportmask-canonical-property"></a><span data-ttu-id="33cbc-103">PidTagContactAddressBookStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="33cbc-103">PidTagContactAddressBookStoreSupportMask Canonical Property</span></span>

  
  
<span data-ttu-id="33cbc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="33cbc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="33cbc-105">包含从包含联系人文件夹的存储区获得的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagcontactaddressbookstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="33cbc-105">Contains the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagcontactaddressbookstoresupportmask-canonical-property.md)) property obtained from the store that contains the Contacts folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="33cbc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="33cbc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="33cbc-107">PR_CONTAB_STORE_SUPPORT_MASK</span><span class="sxs-lookup"><span data-stu-id="33cbc-107">PR_CONTAB_STORE_SUPPORT_MASK</span></span>  <br/> |
|<span data-ttu-id="33cbc-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="33cbc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="33cbc-109">0x6611</span><span class="sxs-lookup"><span data-stu-id="33cbc-109">0x6611</span></span>  <br/> |
|<span data-ttu-id="33cbc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="33cbc-110">Data type:</span></span>  <br/> |<span data-ttu-id="33cbc-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="33cbc-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="33cbc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="33cbc-112">Area:</span></span>  <br/> |<span data-ttu-id="33cbc-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="33cbc-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="33cbc-114">说明</span><span class="sxs-lookup"><span data-stu-id="33cbc-114">Remarks</span></span>

<span data-ttu-id="33cbc-115">联系人通讯簿提供程序使用此属性来评估适用性的存储支持的功能。</span><span class="sxs-lookup"><span data-stu-id="33cbc-115">The Contact Address Book provider uses this property to evaluate the adequacy of the store's supported features.</span></span> <span data-ttu-id="33cbc-116">这是联系人通讯簿容器和联系人通讯簿容器的表中的列上的属性。</span><span class="sxs-lookup"><span data-stu-id="33cbc-116">This is a property on a Contact Address Book container, and a column in the table of Contact Address Book containers.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="33cbc-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="33cbc-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="33cbc-118">头文件</span><span class="sxs-lookup"><span data-stu-id="33cbc-118">Header files</span></span>

<span data-ttu-id="33cbc-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="33cbc-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="33cbc-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="33cbc-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="33cbc-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="33cbc-121">Mapitags.h</span></span>
  
> <span data-ttu-id="33cbc-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="33cbc-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="33cbc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33cbc-123">See also</span></span>



[<span data-ttu-id="33cbc-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="33cbc-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="33cbc-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="33cbc-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="33cbc-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="33cbc-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="33cbc-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="33cbc-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

