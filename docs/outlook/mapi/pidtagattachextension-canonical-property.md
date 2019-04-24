---
title: PidTagAttachExtension 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachExtension
api_type:
- HeaderDef
ms.assetid: 667da30b-e11c-4040-aecf-bb35eed23722
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 26efa868de29bc8a6a180b717230951b76da26a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319759"
---
# <a name="pidtagattachextension-canonical-property"></a><span data-ttu-id="87914-103">PidTagAttachExtension 规范属性</span><span class="sxs-lookup"><span data-stu-id="87914-103">PidTagAttachExtension Canonical Property</span></span>

  
  
<span data-ttu-id="87914-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="87914-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="87914-105">包含一个指示附件的文档类型的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="87914-105">Contains a file name extension that indicates the document type of an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="87914-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="87914-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="87914-107">PR_ATTACH_EXTENSION、PR_ATTACH_EXTENSION_A、PR_ATTACH_EXTENSION_W</span><span class="sxs-lookup"><span data-stu-id="87914-107">PR_ATTACH_EXTENSION, PR_ATTACH_EXTENSION_A, PR_ATTACH_EXTENSION_W</span></span>  <br/> |
|<span data-ttu-id="87914-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="87914-108">Identifier:</span></span>  <br/> |<span data-ttu-id="87914-109">0x3703</span><span class="sxs-lookup"><span data-stu-id="87914-109">0x3703</span></span>  <br/> |
|<span data-ttu-id="87914-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="87914-110">Data type:</span></span>  <br/> |<span data-ttu-id="87914-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="87914-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="87914-112">区域：</span><span class="sxs-lookup"><span data-stu-id="87914-112">Area:</span></span>  <br/> |<span data-ttu-id="87914-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="87914-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="87914-114">注解</span><span class="sxs-lookup"><span data-stu-id="87914-114">Remarks</span></span>

<span data-ttu-id="87914-115">这些属性是由客户端应用程序在提交时设置的。</span><span class="sxs-lookup"><span data-stu-id="87914-115">These properties are set by the client application at submission time.</span></span> 
  
<span data-ttu-id="87914-116">邮件系统在转换邮件附件 (在路由转换中) 或基于收到的邮件中的附件启动应用程序时使用**PR_ATTACH_EXTENSION** 。</span><span class="sxs-lookup"><span data-stu-id="87914-116">The messaging system uses **PR_ATTACH_EXTENSION** when converting message attachments (in-route conversion) or launching applications based on attachments in received messages.</span></span> <span data-ttu-id="87914-117">如果发送客户端未提供这些属性的值, 则处理附件的邮件存储无义务生成该附件。</span><span class="sxs-lookup"><span data-stu-id="87914-117">If the sending client does not provide a value for these properties, the message store handling the attachment is not obligated to generate it.</span></span> <span data-ttu-id="87914-118">接收客户端应首先检查**PR_ATTACH_EXTENSION**, 如果未提供, 应分析附件的**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 或 PR_ATTACH_LONG_FILENAME 中的文件扩展名。 \*\*\*\*([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="87914-118">The receiving client should first check for **PR_ATTACH_EXTENSION**, and if it is not provided, should parse the file name extension from the attachment's **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) or **PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="87914-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="87914-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="87914-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="87914-120">Protocol specifications</span></span>

<span data-ttu-id="87914-121">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87914-121">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87914-122">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="87914-122">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="87914-123">头文件</span><span class="sxs-lookup"><span data-stu-id="87914-123">Header files</span></span>

<span data-ttu-id="87914-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="87914-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="87914-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="87914-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="87914-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="87914-126">Mapitags.h</span></span>
  
> <span data-ttu-id="87914-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="87914-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="87914-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87914-128">See also</span></span>



[<span data-ttu-id="87914-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="87914-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="87914-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="87914-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="87914-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="87914-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="87914-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="87914-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

