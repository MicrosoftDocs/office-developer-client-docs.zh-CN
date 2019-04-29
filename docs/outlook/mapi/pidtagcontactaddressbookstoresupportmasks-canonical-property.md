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
ms.openlocfilehash: e06d9a3ee2352e05e38ab1f2d86014f970160f9d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427799"
---
# <a name="pidtagcontactaddressbookstoresupportmasks-canonical-property"></a><span data-ttu-id="96c95-103">PidTagContactAddressBookStoreSupportMasks 规范属性</span><span class="sxs-lookup"><span data-stu-id="96c95-103">PidTagContactAddressBookStoreSupportMasks Canonical Property</span></span>

  
  
<span data-ttu-id="96c95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96c95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96c95-105">包含指示存储区支持的功能的标志。</span><span class="sxs-lookup"><span data-stu-id="96c95-105">Contains flags indicating the store's supported features.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="96c95-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="96c95-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="96c95-107">PR_CONTAB_STORE_SUPPORT_MASKS</span><span class="sxs-lookup"><span data-stu-id="96c95-107">PR_CONTAB_STORE_SUPPORT_MASKS</span></span>  <br/> |
|<span data-ttu-id="96c95-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="96c95-108">Identifier:</span></span>  <br/> |<span data-ttu-id="96c95-109">0x6621</span><span class="sxs-lookup"><span data-stu-id="96c95-109">0x6621</span></span>  <br/> |
|<span data-ttu-id="96c95-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="96c95-110">Data type:</span></span>  <br/> |<span data-ttu-id="96c95-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="96c95-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="96c95-112">区域：</span><span class="sxs-lookup"><span data-stu-id="96c95-112">Area:</span></span>  <br/> |<span data-ttu-id="96c95-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="96c95-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="96c95-114">说明</span><span class="sxs-lookup"><span data-stu-id="96c95-114">Remarks</span></span>

<span data-ttu-id="96c95-115">此属性是从包含 "联系人" 文件夹的存储中获取的。</span><span class="sxs-lookup"><span data-stu-id="96c95-115">This property is obtained from the stores which contains the Contacts folders.</span></span> <span data-ttu-id="96c95-116">联系人通讯簿提供程序使用它来评估存储区支持的功能是否够用。</span><span class="sxs-lookup"><span data-stu-id="96c95-116">The Contact Address Book provider uses it to evaluate the adequacy of the store's supported features.</span></span> <span data-ttu-id="96c95-117">它是联系人通讯簿配置文件部分的属性。</span><span class="sxs-lookup"><span data-stu-id="96c95-117">It is a property on a Contact Address Book profile section.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="96c95-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="96c95-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="96c95-119">头文件</span><span class="sxs-lookup"><span data-stu-id="96c95-119">Header files</span></span>

<span data-ttu-id="96c95-120">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="96c95-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="96c95-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="96c95-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="96c95-122">Mapitags</span><span class="sxs-lookup"><span data-stu-id="96c95-122">Mapitags.h</span></span>
  
> <span data-ttu-id="96c95-123">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="96c95-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="96c95-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96c95-124">See also</span></span>



[<span data-ttu-id="96c95-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="96c95-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="96c95-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="96c95-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="96c95-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="96c95-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="96c95-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="96c95-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

