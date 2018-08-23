---
title: PidLidRemoteTransport 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRemoteTransport
api_type:
- COM
ms.assetid: b3b30d6a-05cd-4dd1-a162-20768f12e680
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 124a0d8f23fcff9d1bca9d5debe4a9aa6fb6146c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587115"
---
# <a name="pidlidremotetransport-canonical-property"></a><span data-ttu-id="a25bd-103">PidLidRemoteTransport 规范属性</span><span class="sxs-lookup"><span data-stu-id="a25bd-103">PidLidRemoteTransport Canonical Property</span></span>

  
  
<span data-ttu-id="a25bd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a25bd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a25bd-105">标识哪个帐户的标头项相关联，主要是为了实现 POP 保留在服务器功能。</span><span class="sxs-lookup"><span data-stu-id="a25bd-105">Identifies what account the header item is associated with, primarily to implement the POP Leave on Server functionality.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a25bd-106">相关的属性</span><span class="sxs-lookup"><span data-stu-id="a25bd-106">Associated Properties</span></span>  <br/> |<span data-ttu-id="a25bd-107">dispidRemoteXP</span><span class="sxs-lookup"><span data-stu-id="a25bd-107">dispidRemoteXP</span></span>  <br/> |
|<span data-ttu-id="a25bd-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="a25bd-108">Property set:</span></span>  <br/> |<span data-ttu-id="a25bd-109">PSETID_Remote</span><span class="sxs-lookup"><span data-stu-id="a25bd-109">PSETID_Remote</span></span>  <br/> |
|<span data-ttu-id="a25bd-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="a25bd-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a25bd-111">0x00008F03</span><span class="sxs-lookup"><span data-stu-id="a25bd-111">0x00008F03</span></span>  <br/> |
|<span data-ttu-id="a25bd-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a25bd-112">Data type:</span></span>  <br/> |<span data-ttu-id="a25bd-113">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="a25bd-113">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="a25bd-114">区域：</span><span class="sxs-lookup"><span data-stu-id="a25bd-114">Area:</span></span>  <br/> |<span data-ttu-id="a25bd-115">远程邮件</span><span class="sxs-lookup"><span data-stu-id="a25bd-115">Remote message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a25bd-116">注解</span><span class="sxs-lookup"><span data-stu-id="a25bd-116">Remarks</span></span>

<span data-ttu-id="a25bd-117">此属性是仅对具有邮件类 IPM 的邮件。远程。</span><span class="sxs-lookup"><span data-stu-id="a25bd-117">This property is relevant only on messages that have a message class of IPM.Remote.</span></span> <span data-ttu-id="a25bd-118">Microsoft Outlook 保持在文件夹关联的信息 （从故障） 邮件中，为给定的存储到下载的各种帐户的映射，但它无法在注册表中保留此信息。</span><span class="sxs-lookup"><span data-stu-id="a25bd-118">Microsoft Outlook keeps a mapping of various accounts that are downloading to a given store in a Folder Associated Information (FAI) message, but it could also keep this information in the registry.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a25bd-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="a25bd-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a25bd-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="a25bd-120">Protocol specifications</span></span>

<span data-ttu-id="a25bd-121">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="a25bd-121">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="a25bd-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a25bd-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a25bd-123">头文件</span><span class="sxs-lookup"><span data-stu-id="a25bd-123">Header files</span></span>

<span data-ttu-id="a25bd-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a25bd-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="a25bd-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a25bd-125">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a25bd-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a25bd-126">See also</span></span>



[<span data-ttu-id="a25bd-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a25bd-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a25bd-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a25bd-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a25bd-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a25bd-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a25bd-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a25bd-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

