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
ms.openlocfilehash: fa2770daf38fe93eb9fb69990eebc2a6fcfd6a27
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778225"
---
# <a name="pidtagreportsearchkey-canonical-property"></a><span data-ttu-id="f5886-103">PidTagReportSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="f5886-103">PidTagReportSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="f5886-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f5886-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f5886-105">包含搜索关键字的收件人的应将报告获得此消息。</span><span class="sxs-lookup"><span data-stu-id="f5886-105">Contains the search key for the recipient that should get reports for this message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f5886-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f5886-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f5886-107">PR_REPORT_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="f5886-107">PR_REPORT_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="f5886-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f5886-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f5886-109">0x0054</span><span class="sxs-lookup"><span data-stu-id="f5886-109">0x0054</span></span>  <br/> |
|<span data-ttu-id="f5886-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f5886-110">Data type:</span></span>  <br/> |<span data-ttu-id="f5886-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f5886-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f5886-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f5886-112">Area:</span></span>  <br/> |<span data-ttu-id="f5886-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="f5886-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f5886-114">说明</span><span class="sxs-lookup"><span data-stu-id="f5886-114">Remarks</span></span>

<span data-ttu-id="f5886-115">此属性是一个发件人已委派接收此消息生成任何报告的收件人的地址属性。</span><span class="sxs-lookup"><span data-stu-id="f5886-115">This property is one of the address properties for the recipient that the sender has delegated to receive any reports generated for this message.</span></span>
  
<span data-ttu-id="f5886-116">必须将报表路由到另一个用户的客户端应用程序应在消息提交时设置此属性。</span><span class="sxs-lookup"><span data-stu-id="f5886-116">A client application that must route reports to another user should set this property at message submission time.</span></span> <span data-ttu-id="f5886-117">它未设置，如果报告发送到邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="f5886-117">If it is not set, the reports are sent to the message sender.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f5886-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f5886-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f5886-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f5886-119">Protocol specifications</span></span>

<span data-ttu-id="f5886-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f5886-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f5886-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="f5886-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f5886-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f5886-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f5886-123">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="f5886-123">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f5886-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f5886-124">Header files</span></span>

<span data-ttu-id="f5886-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f5886-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f5886-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f5886-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="f5886-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f5886-127">Mapitags.h</span></span>
  
> <span data-ttu-id="f5886-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f5886-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f5886-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5886-129">See also</span></span>



[<span data-ttu-id="f5886-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f5886-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f5886-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f5886-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f5886-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f5886-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f5886-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f5886-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

