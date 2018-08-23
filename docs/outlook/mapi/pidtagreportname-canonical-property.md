---
title: PidTagReportName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReportName
api_type:
- COM
ms.assetid: 4ec3100f-7cf1-4702-b326-e6da586a7bb2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3c1a848eec84c7d81792a95baa3f47fa6779e95f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569580"
---
# <a name="pidtagreportname-canonical-property"></a><span data-ttu-id="2c90e-103">PidTagReportName 规范属性</span><span class="sxs-lookup"><span data-stu-id="2c90e-103">PidTagReportName Canonical Property</span></span>

  
  
<span data-ttu-id="2c90e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c90e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c90e-105">包含应获得此消息报告的收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2c90e-105">Contains the display name for the recipient that should get reports for this message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2c90e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2c90e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2c90e-107">PR_REPORT_NAME，PR_REPORT_NAME_A，PR_REPORT_NAME_W</span><span class="sxs-lookup"><span data-stu-id="2c90e-107">PR_REPORT_NAME, PR_REPORT_NAME_A, PR_REPORT_NAME_W</span></span>  <br/> |
|<span data-ttu-id="2c90e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2c90e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2c90e-109">0x003A</span><span class="sxs-lookup"><span data-stu-id="2c90e-109">0x003A</span></span>  <br/> |
|<span data-ttu-id="2c90e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2c90e-110">Data type:</span></span>  <br/> |<span data-ttu-id="2c90e-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2c90e-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2c90e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2c90e-112">Area:</span></span>  <br/> |<span data-ttu-id="2c90e-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="2c90e-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2c90e-114">注解</span><span class="sxs-lookup"><span data-stu-id="2c90e-114">Remarks</span></span>

<span data-ttu-id="2c90e-115">这些属性是发件人已委派接收此消息生成任何报告的收件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="2c90e-115">These properties are examples of the address properties for the recipient that the sender has delegated to receive any reports generated for this message.</span></span>
  
<span data-ttu-id="2c90e-116">必须将报表路由到另一个用户的客户端应用程序应在消息提交时设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="2c90e-116">A client application that must route reports to another user should set these properties at message submission time.</span></span> <span data-ttu-id="2c90e-117">如果未设置这些属性，报告将发送给邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="2c90e-117">If they are not set, the reports are sent to the message sender.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2c90e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2c90e-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="2c90e-119">头文件</span><span class="sxs-lookup"><span data-stu-id="2c90e-119">Header files</span></span>

<span data-ttu-id="2c90e-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2c90e-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="2c90e-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2c90e-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="2c90e-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2c90e-122">Mapitags.h</span></span>
  
> <span data-ttu-id="2c90e-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2c90e-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2c90e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c90e-124">See also</span></span>



[<span data-ttu-id="2c90e-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2c90e-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2c90e-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2c90e-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2c90e-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2c90e-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2c90e-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2c90e-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

