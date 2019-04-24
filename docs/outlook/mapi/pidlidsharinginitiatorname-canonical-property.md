---
title: PidLidSharingInitiatorName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingInitiatorName
api_type:
- COM
ms.assetid: f2b126fc-41fa-4dc4-9f13-07bc4f621d0b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9e3236affa9612356e68044d2943ea7b9276384
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336846"
---
# <a name="pidlidsharinginitiatorname-canonical-property"></a><span data-ttu-id="b4374-103">PidLidSharingInitiatorName 规范属性</span><span class="sxs-lookup"><span data-stu-id="b4374-103">PidLidSharingInitiatorName Canonical Property</span></span>

  
  
<span data-ttu-id="b4374-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b4374-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b4374-105">指定为共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="b4374-105">Designates as a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b4374-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b4374-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b4374-107">dispidSharingInitiatorName</span><span class="sxs-lookup"><span data-stu-id="b4374-107">dispidSharingInitiatorName</span></span>  <br/> |
|<span data-ttu-id="b4374-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="b4374-108">Property set:</span></span>  <br/> |<span data-ttu-id="b4374-109">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="b4374-109">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="b4374-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="b4374-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b4374-111">0x00008A07</span><span class="sxs-lookup"><span data-stu-id="b4374-111">0x00008A07</span></span>  <br/> |
|<span data-ttu-id="b4374-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b4374-112">Data type:</span></span>  <br/> |<span data-ttu-id="b4374-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b4374-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b4374-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b4374-114">Area:</span></span>  <br/> |<span data-ttu-id="b4374-115">共享</span><span class="sxs-lookup"><span data-stu-id="b4374-115">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b4374-116">注解</span><span class="sxs-lookup"><span data-stu-id="b4374-116">Remarks</span></span>

<span data-ttu-id="b4374-117">此属性必须设置为**dispidSharingInitiatorEid** ([PidLidSharingInitiatorEntryId](pidlidsharinginitiatorentryid-canonical-property.md)) 标识的通讯簿中的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的值, 应将其忽略。</span><span class="sxs-lookup"><span data-stu-id="b4374-117">This property must be set to the value of **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) from the Address Book identified by **dispidSharingInitiatorEid** ([PidLidSharingInitiatorEntryId](pidlidsharinginitiatorentryid-canonical-property.md)) and should be ignored.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b4374-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b4374-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b4374-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b4374-119">Protocol specifications</span></span>

<span data-ttu-id="b4374-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4374-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b4374-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b4374-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b4374-122">[[毫秒-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4374-122">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b4374-123">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="b4374-123">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b4374-124">头文件</span><span class="sxs-lookup"><span data-stu-id="b4374-124">Header files</span></span>

<span data-ttu-id="b4374-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b4374-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="b4374-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b4374-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b4374-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4374-127">See also</span></span>



[<span data-ttu-id="b4374-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b4374-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b4374-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b4374-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b4374-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b4374-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b4374-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b4374-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

