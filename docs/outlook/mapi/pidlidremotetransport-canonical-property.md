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
ms.openlocfilehash: ddedc2ca0785be2fe4850ec3cfdf979d1e5f2798
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439441"
---
# <a name="pidlidremotetransport-canonical-property"></a><span data-ttu-id="ebe70-103">PidLidRemoteTransport 规范属性</span><span class="sxs-lookup"><span data-stu-id="ebe70-103">PidLidRemoteTransport Canonical Property</span></span>

  
  
<span data-ttu-id="ebe70-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ebe70-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ebe70-105">标识与标头项关联的帐户, 主要用于对服务器功能实施 POP 保留。</span><span class="sxs-lookup"><span data-stu-id="ebe70-105">Identifies what account the header item is associated with, primarily to implement the POP Leave on Server functionality.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ebe70-106">关联属性</span><span class="sxs-lookup"><span data-stu-id="ebe70-106">Associated Properties</span></span>  <br/> |<span data-ttu-id="ebe70-107">dispidRemoteXP</span><span class="sxs-lookup"><span data-stu-id="ebe70-107">dispidRemoteXP</span></span>  <br/> |
|<span data-ttu-id="ebe70-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="ebe70-108">Property set:</span></span>  <br/> |<span data-ttu-id="ebe70-109">PSETID_Remote</span><span class="sxs-lookup"><span data-stu-id="ebe70-109">PSETID_Remote</span></span>  <br/> |
|<span data-ttu-id="ebe70-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="ebe70-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ebe70-111">0x00008F03</span><span class="sxs-lookup"><span data-stu-id="ebe70-111">0x00008F03</span></span>  <br/> |
|<span data-ttu-id="ebe70-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ebe70-112">Data type:</span></span>  <br/> |<span data-ttu-id="ebe70-113">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="ebe70-113">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="ebe70-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ebe70-114">Area:</span></span>  <br/> |<span data-ttu-id="ebe70-115">远程邮件</span><span class="sxs-lookup"><span data-stu-id="ebe70-115">Remote message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ebe70-116">说明</span><span class="sxs-lookup"><span data-stu-id="ebe70-116">Remarks</span></span>

<span data-ttu-id="ebe70-117">此属性仅与邮件类为 IPM 的邮件相关。远端.</span><span class="sxs-lookup"><span data-stu-id="ebe70-117">This property is relevant only on messages that have a message class of IPM.Remote.</span></span> <span data-ttu-id="ebe70-118">Microsoft Outlook 保留要下载到文件夹相关信息 (FAI) 邮件中的特定存储的各种帐户的映射, 但也可能将此信息保留在注册表中。</span><span class="sxs-lookup"><span data-stu-id="ebe70-118">Microsoft Outlook keeps a mapping of various accounts that are downloading to a given store in a Folder Associated Information (FAI) message, but it could also keep this information in the registry.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ebe70-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="ebe70-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ebe70-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="ebe70-120">Protocol specifications</span></span>

<span data-ttu-id="ebe70-121">[[毫秒-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="ebe70-121">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="ebe70-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ebe70-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ebe70-123">头文件</span><span class="sxs-lookup"><span data-stu-id="ebe70-123">Header files</span></span>

<span data-ttu-id="ebe70-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ebe70-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="ebe70-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ebe70-125">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ebe70-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebe70-126">See also</span></span>



[<span data-ttu-id="ebe70-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ebe70-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ebe70-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ebe70-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ebe70-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ebe70-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ebe70-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ebe70-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

