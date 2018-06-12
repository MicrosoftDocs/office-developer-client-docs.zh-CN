---
title: PidLidSharingResponseTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingResponseTime
api_type:
- COM
ms.assetid: 5cf0cf25-d302-44a4-bee8-53f5cff62647
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 9c7ea7d1772ac8dff69783fcff2556b34a3d18e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777028"
---
# <a name="pidlidsharingresponsetime-canonical-property"></a><span data-ttu-id="60c7e-103">PidLidSharingResponseTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="60c7e-103">PidLidSharingResponseTime Canonical Property</span></span>

  
  
<span data-ttu-id="60c7e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="60c7e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="60c7e-105">指定频率共享请求的收件人发送共享响应的时间。</span><span class="sxs-lookup"><span data-stu-id="60c7e-105">Specifies the time at which the recipient of the sharing request sent a sharing response.</span></span> <span data-ttu-id="60c7e-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="60c7e-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="60c7e-107">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="60c7e-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="60c7e-108">dispidSharingResponseTime</span><span class="sxs-lookup"><span data-stu-id="60c7e-108">dispidSharingResponseTime</span></span>  <br/> |
|<span data-ttu-id="60c7e-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="60c7e-109">Property set:</span></span>  <br/> |<span data-ttu-id="60c7e-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="60c7e-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="60c7e-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="60c7e-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="60c7e-112">0x00008A28</span><span class="sxs-lookup"><span data-stu-id="60c7e-112">0x00008A28</span></span>  <br/> |
|<span data-ttu-id="60c7e-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="60c7e-113">Data type:</span></span>  <br/> |<span data-ttu-id="60c7e-114">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="60c7e-114">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="60c7e-115">区域：</span><span class="sxs-lookup"><span data-stu-id="60c7e-115">Area:</span></span>  <br/> |<span data-ttu-id="60c7e-116">共享</span><span class="sxs-lookup"><span data-stu-id="60c7e-116">Sharing</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="60c7e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="60c7e-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="60c7e-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="60c7e-118">Protocol specifications</span></span>

<span data-ttu-id="60c7e-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="60c7e-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="60c7e-120">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="60c7e-120">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="60c7e-121">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="60c7e-121">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="60c7e-122">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="60c7e-122">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="60c7e-123">头文件</span><span class="sxs-lookup"><span data-stu-id="60c7e-123">Header files</span></span>

<span data-ttu-id="60c7e-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="60c7e-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="60c7e-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="60c7e-125">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="60c7e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60c7e-126">See also</span></span>



[<span data-ttu-id="60c7e-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="60c7e-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="60c7e-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="60c7e-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="60c7e-129">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="60c7e-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="60c7e-130">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="60c7e-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

