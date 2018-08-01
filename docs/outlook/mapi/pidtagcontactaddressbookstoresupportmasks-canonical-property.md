---
title: PidTagContactAddressBookStoreSupportMasks 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookStoreSupportMasks
api_type:
- HeaderDef
ms.assetid: 68f5aac1-714c-48fc-a0cf-a0c0401a6070
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 29e842584e5145f747aa0ef0c7796e5f7b3a8e0b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777436"
---
# <a name="pidtagcontactaddressbookstoresupportmasks-canonical-property"></a><span data-ttu-id="27185-103">PidTagContactAddressBookStoreSupportMasks 规范属性</span><span class="sxs-lookup"><span data-stu-id="27185-103">PidTagContactAddressBookStoreSupportMasks Canonical Property</span></span>

  
  
<span data-ttu-id="27185-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="27185-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="27185-105">包含标志指示的存储支持的功能。</span><span class="sxs-lookup"><span data-stu-id="27185-105">Contains flags indicating the store's supported features.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="27185-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="27185-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="27185-107">PR_CONTAB_STORE_SUPPORT_MASKS</span><span class="sxs-lookup"><span data-stu-id="27185-107">PR_CONTAB_STORE_SUPPORT_MASKS</span></span>  <br/> |
|<span data-ttu-id="27185-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="27185-108">Identifier:</span></span>  <br/> |<span data-ttu-id="27185-109">0x6621</span><span class="sxs-lookup"><span data-stu-id="27185-109">0x6621</span></span>  <br/> |
|<span data-ttu-id="27185-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="27185-110">Data type:</span></span>  <br/> |<span data-ttu-id="27185-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="27185-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="27185-112">区域：</span><span class="sxs-lookup"><span data-stu-id="27185-112">Area:</span></span>  <br/> |<span data-ttu-id="27185-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="27185-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="27185-114">说明</span><span class="sxs-lookup"><span data-stu-id="27185-114">Remarks</span></span>

<span data-ttu-id="27185-115">从包含联系人文件夹的存储中获取此属性。</span><span class="sxs-lookup"><span data-stu-id="27185-115">This property is obtained from the stores which contains the Contacts folders.</span></span> <span data-ttu-id="27185-116">联系人通讯簿提供程序使用它来评估适用性的存储支持的功能。</span><span class="sxs-lookup"><span data-stu-id="27185-116">The Contact Address Book provider uses it to evaluate the adequacy of the store's supported features.</span></span> <span data-ttu-id="27185-117">它是联系人通讯簿配置文件一节的属性。</span><span class="sxs-lookup"><span data-stu-id="27185-117">It is a property on a Contact Address Book profile section.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="27185-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="27185-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="27185-119">头文件</span><span class="sxs-lookup"><span data-stu-id="27185-119">Header files</span></span>

<span data-ttu-id="27185-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="27185-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="27185-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="27185-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="27185-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="27185-122">Mapitags.h</span></span>
  
> <span data-ttu-id="27185-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="27185-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="27185-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27185-124">See also</span></span>



[<span data-ttu-id="27185-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="27185-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="27185-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="27185-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="27185-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="27185-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="27185-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="27185-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

