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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4d3a38f55fa2869df3f8afa1301cf1ad0c7b0737
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778215"
---
# <a name="pidtagreportname-canonical-property"></a><span data-ttu-id="8b065-103">PidTagReportName 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b065-103">PidTagReportName Canonical Property</span></span>

  
  
<span data-ttu-id="8b065-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8b065-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8b065-105">包含应获得此消息报告的收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="8b065-105">Contains the display name for the recipient that should get reports for this message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8b065-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="8b065-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8b065-107">PR_REPORT_NAME，PR_REPORT_NAME_A，PR_REPORT_NAME_W</span><span class="sxs-lookup"><span data-stu-id="8b065-107">PR_REPORT_NAME, PR_REPORT_NAME_A, PR_REPORT_NAME_W</span></span>  <br/> |
|<span data-ttu-id="8b065-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8b065-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8b065-109">0x003A</span><span class="sxs-lookup"><span data-stu-id="8b065-109">0x003A</span></span>  <br/> |
|<span data-ttu-id="8b065-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8b065-110">Data type:</span></span>  <br/> |<span data-ttu-id="8b065-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8b065-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8b065-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8b065-112">Area:</span></span>  <br/> |<span data-ttu-id="8b065-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="8b065-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8b065-114">备注</span><span class="sxs-lookup"><span data-stu-id="8b065-114">Remarks</span></span>

<span data-ttu-id="8b065-115">这些属性是发件人已委派接收此消息生成任何报告的收件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="8b065-115">These properties are examples of the address properties for the recipient that the sender has delegated to receive any reports generated for this message.</span></span>
  
<span data-ttu-id="8b065-116">必须将报表路由到另一个用户的客户端应用程序应在消息提交时设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="8b065-116">A client application that must route reports to another user should set these properties at message submission time.</span></span> <span data-ttu-id="8b065-117">如果未设置这些属性，报告将发送给邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="8b065-117">If they are not set, the reports are sent to the message sender.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8b065-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="8b065-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8b065-119">头文件</span><span class="sxs-lookup"><span data-stu-id="8b065-119">Header files</span></span>

<span data-ttu-id="8b065-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8b065-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="8b065-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8b065-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="8b065-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8b065-122">Mapitags.h</span></span>
  
> <span data-ttu-id="8b065-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8b065-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8b065-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b065-124">See also</span></span>



[<span data-ttu-id="8b065-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8b065-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8b065-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b065-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8b065-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8b065-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8b065-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8b065-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

