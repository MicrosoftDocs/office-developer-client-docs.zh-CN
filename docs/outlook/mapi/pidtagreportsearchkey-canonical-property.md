---
title: PidTagReportSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReportSearchKey
api_type:
- COM
ms.assetid: d4f4c40b-b6a8-45f3-b750-07b92c535322
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 889b43bb606cbe9c96d52c8a21ffda5dfcebb1da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359176"
---
# <a name="pidtagreportsearchkey-canonical-property"></a><span data-ttu-id="838ac-103">PidTagReportSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="838ac-103">PidTagReportSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="838ac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="838ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="838ac-105">包含应获取此邮件报告的收件人的搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="838ac-105">Contains the search key for the recipient that should get reports for this message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="838ac-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="838ac-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="838ac-107">PR_REPORT_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="838ac-107">PR_REPORT_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="838ac-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="838ac-108">Identifier:</span></span>  <br/> |<span data-ttu-id="838ac-109">0x0054</span><span class="sxs-lookup"><span data-stu-id="838ac-109">0x0054</span></span>  <br/> |
|<span data-ttu-id="838ac-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="838ac-110">Data type:</span></span>  <br/> |<span data-ttu-id="838ac-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="838ac-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="838ac-112">区域：</span><span class="sxs-lookup"><span data-stu-id="838ac-112">Area:</span></span>  <br/> |<span data-ttu-id="838ac-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="838ac-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="838ac-114">注解</span><span class="sxs-lookup"><span data-stu-id="838ac-114">Remarks</span></span>

<span data-ttu-id="838ac-115">此属性是发件人为接收此邮件生成的任何报告而委派的收件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="838ac-115">This property is one of the address properties for the recipient that the sender has delegated to receive any reports generated for this message.</span></span>
  
<span data-ttu-id="838ac-116">必须将报告路由到另一个用户的客户端应用程序应在邮件提交时设置此属性。</span><span class="sxs-lookup"><span data-stu-id="838ac-116">A client application that must route reports to another user should set this property at message submission time.</span></span> <span data-ttu-id="838ac-117">如果未设置, 则将报告发送给邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="838ac-117">If it is not set, the reports are sent to the message sender.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="838ac-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="838ac-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="838ac-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="838ac-119">Protocol specifications</span></span>

<span data-ttu-id="838ac-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="838ac-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="838ac-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="838ac-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="838ac-122">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="838ac-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="838ac-123">指定在电子邮件中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="838ac-123">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="838ac-124">头文件</span><span class="sxs-lookup"><span data-stu-id="838ac-124">Header files</span></span>

<span data-ttu-id="838ac-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="838ac-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="838ac-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="838ac-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="838ac-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="838ac-127">Mapitags.h</span></span>
  
> <span data-ttu-id="838ac-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="838ac-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="838ac-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="838ac-129">See also</span></span>



[<span data-ttu-id="838ac-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="838ac-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="838ac-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="838ac-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="838ac-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="838ac-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="838ac-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="838ac-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

