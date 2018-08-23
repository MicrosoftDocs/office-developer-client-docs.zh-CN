---
title: PidLidSharingInitiatorEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingInitiatorEntryId
api_type:
- COM
ms.assetid: 47f00706-83df-49cb-bda7-ef572d76a020
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 79392d892944e8ae2470c3da905e47b804d514aa
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576818"
---
# <a name="pidlidsharinginitiatorentryid-canonical-property"></a><span data-ttu-id="32c38-103">PidLidSharingInitiatorEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="32c38-103">PidLidSharingInitiatorEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="32c38-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="32c38-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="32c38-105">将指定的共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="32c38-105">Designates as a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="32c38-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="32c38-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="32c38-107">dispidSharingInitiatorEid</span><span class="sxs-lookup"><span data-stu-id="32c38-107">dispidSharingInitiatorEid</span></span>  <br/> |
|<span data-ttu-id="32c38-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="32c38-108">Property set:</span></span>  <br/> |<span data-ttu-id="32c38-109">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="32c38-109">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="32c38-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="32c38-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="32c38-111">0x00008A09</span><span class="sxs-lookup"><span data-stu-id="32c38-111">0x00008A09</span></span>  <br/> |
|<span data-ttu-id="32c38-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="32c38-112">Data type:</span></span>  <br/> |<span data-ttu-id="32c38-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="32c38-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="32c38-114">区域：</span><span class="sxs-lookup"><span data-stu-id="32c38-114">Area:</span></span>  <br/> |<span data-ttu-id="32c38-115">共享</span><span class="sxs-lookup"><span data-stu-id="32c38-115">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="32c38-116">注解</span><span class="sxs-lookup"><span data-stu-id="32c38-116">Remarks</span></span>

<span data-ttu-id="32c38-117">此属性必须为当前登录用户的通讯簿设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的值 （请参阅[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)）。</span><span class="sxs-lookup"><span data-stu-id="32c38-117">This property must be set to the value of the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property for the Address Book of the currently logged-on user (see [[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="32c38-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="32c38-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="32c38-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="32c38-119">Protocol specifications</span></span>

<span data-ttu-id="32c38-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32c38-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32c38-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="32c38-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="32c38-122">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32c38-122">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32c38-123">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="32c38-123">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="32c38-124">头文件</span><span class="sxs-lookup"><span data-stu-id="32c38-124">Header files</span></span>

<span data-ttu-id="32c38-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="32c38-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="32c38-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="32c38-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="32c38-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32c38-127">See also</span></span>



[<span data-ttu-id="32c38-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="32c38-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="32c38-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="32c38-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="32c38-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="32c38-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="32c38-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="32c38-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

