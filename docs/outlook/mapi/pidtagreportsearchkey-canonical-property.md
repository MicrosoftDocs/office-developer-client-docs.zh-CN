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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383504"
---
# <a name="pidtagreportsearchkey-canonical-property"></a><span data-ttu-id="bd5de-103">PidTagReportSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="bd5de-103">PidTagReportSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="bd5de-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bd5de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bd5de-105">包含搜索关键字的收件人的应将报告获得此消息。</span><span class="sxs-lookup"><span data-stu-id="bd5de-105">Contains the search key for the recipient that should get reports for this message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bd5de-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bd5de-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bd5de-107">PR_REPORT_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="bd5de-107">PR_REPORT_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="bd5de-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="bd5de-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bd5de-109">0x0054</span><span class="sxs-lookup"><span data-stu-id="bd5de-109">0x0054</span></span>  <br/> |
|<span data-ttu-id="bd5de-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bd5de-110">Data type:</span></span>  <br/> |<span data-ttu-id="bd5de-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="bd5de-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="bd5de-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bd5de-112">Area:</span></span>  <br/> |<span data-ttu-id="bd5de-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="bd5de-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bd5de-114">说明</span><span class="sxs-lookup"><span data-stu-id="bd5de-114">Remarks</span></span>

<span data-ttu-id="bd5de-115">此属性是一个发件人已委派接收此消息生成任何报告的收件人的地址属性。</span><span class="sxs-lookup"><span data-stu-id="bd5de-115">This property is one of the address properties for the recipient that the sender has delegated to receive any reports generated for this message.</span></span>
  
<span data-ttu-id="bd5de-116">必须将报表路由到另一个用户的客户端应用程序应在消息提交时设置此属性。</span><span class="sxs-lookup"><span data-stu-id="bd5de-116">A client application that must route reports to another user should set this property at message submission time.</span></span> <span data-ttu-id="bd5de-117">它未设置，如果报告发送到邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="bd5de-117">If it is not set, the reports are sent to the message sender.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bd5de-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="bd5de-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bd5de-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="bd5de-119">Protocol specifications</span></span>

<span data-ttu-id="bd5de-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bd5de-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bd5de-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="bd5de-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="bd5de-122">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bd5de-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bd5de-123">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="bd5de-123">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bd5de-124">头文件</span><span class="sxs-lookup"><span data-stu-id="bd5de-124">Header files</span></span>

<span data-ttu-id="bd5de-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bd5de-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="bd5de-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bd5de-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="bd5de-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="bd5de-127">Mapitags.h</span></span>
  
> <span data-ttu-id="bd5de-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bd5de-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bd5de-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd5de-129">See also</span></span>



[<span data-ttu-id="bd5de-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bd5de-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bd5de-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bd5de-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bd5de-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bd5de-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bd5de-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bd5de-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

