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
ms.openlocfilehash: a15830d1b673b44e9058e33a1499744f631d8e32
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587654"
---
# <a name="pidtagcontactaddressbookstoresupportmasks-canonical-property"></a><span data-ttu-id="f0b7c-103">PidTagContactAddressBookStoreSupportMasks 规范属性</span><span class="sxs-lookup"><span data-stu-id="f0b7c-103">PidTagContactAddressBookStoreSupportMasks Canonical Property</span></span>

  
  
<span data-ttu-id="f0b7c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0b7c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0b7c-105">包含标志指示的存储支持的功能。</span><span class="sxs-lookup"><span data-stu-id="f0b7c-105">Contains flags indicating the store's supported features.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f0b7c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f0b7c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f0b7c-107">PR_CONTAB_STORE_SUPPORT_MASKS</span><span class="sxs-lookup"><span data-stu-id="f0b7c-107">PR_CONTAB_STORE_SUPPORT_MASKS</span></span>  <br/> |
|<span data-ttu-id="f0b7c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f0b7c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f0b7c-109">0x6621</span><span class="sxs-lookup"><span data-stu-id="f0b7c-109">0x6621</span></span>  <br/> |
|<span data-ttu-id="f0b7c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f0b7c-110">Data type:</span></span>  <br/> |<span data-ttu-id="f0b7c-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="f0b7c-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="f0b7c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f0b7c-112">Area:</span></span>  <br/> |<span data-ttu-id="f0b7c-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="f0b7c-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f0b7c-114">注解</span><span class="sxs-lookup"><span data-stu-id="f0b7c-114">Remarks</span></span>

<span data-ttu-id="f0b7c-115">从包含联系人文件夹的存储中获取此属性。</span><span class="sxs-lookup"><span data-stu-id="f0b7c-115">This property is obtained from the stores which contains the Contacts folders.</span></span> <span data-ttu-id="f0b7c-116">联系人通讯簿提供程序使用它来评估适用性的存储支持的功能。</span><span class="sxs-lookup"><span data-stu-id="f0b7c-116">The Contact Address Book provider uses it to evaluate the adequacy of the store's supported features.</span></span> <span data-ttu-id="f0b7c-117">它是联系人通讯簿配置文件一节的属性。</span><span class="sxs-lookup"><span data-stu-id="f0b7c-117">It is a property on a Contact Address Book profile section.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f0b7c-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f0b7c-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f0b7c-119">头文件</span><span class="sxs-lookup"><span data-stu-id="f0b7c-119">Header files</span></span>

<span data-ttu-id="f0b7c-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f0b7c-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="f0b7c-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f0b7c-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="f0b7c-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f0b7c-122">Mapitags.h</span></span>
  
> <span data-ttu-id="f0b7c-123">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f0b7c-123">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f0b7c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0b7c-124">See also</span></span>



[<span data-ttu-id="f0b7c-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f0b7c-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f0b7c-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f0b7c-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f0b7c-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f0b7c-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f0b7c-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f0b7c-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

