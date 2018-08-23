---
title: PidTagMailPermission 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMailPermission
api_type:
- HeaderDef
ms.assetid: f8270ef2-56d4-4b47-bdda-a39c966bbcba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fb0b66cbf0de1ac351bb2026a48e0154de779206
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571190"
---
# <a name="pidtagmailpermission-canonical-property"></a><span data-ttu-id="72afa-103">PidTagMailPermission 规范属性</span><span class="sxs-lookup"><span data-stu-id="72afa-103">PidTagMailPermission Canonical Property</span></span>

  
  
<span data-ttu-id="72afa-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72afa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="72afa-105">包含 TRUE，则允许消息的用户发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="72afa-105">Contains TRUE if the messaging user is allowed to send and receive messages.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="72afa-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="72afa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="72afa-107">PR_MAIL_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="72afa-107">PR_MAIL_PERMISSION</span></span>  <br/> |
|<span data-ttu-id="72afa-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="72afa-108">Identifier:</span></span>  <br/> |<span data-ttu-id="72afa-109">0x3A0E</span><span class="sxs-lookup"><span data-stu-id="72afa-109">0x3A0E</span></span>  <br/> |
|<span data-ttu-id="72afa-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="72afa-110">Data type:</span></span>  <br/> |<span data-ttu-id="72afa-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="72afa-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="72afa-112">区域：</span><span class="sxs-lookup"><span data-stu-id="72afa-112">Area:</span></span>  <br/> |<span data-ttu-id="72afa-113">Address</span><span class="sxs-lookup"><span data-stu-id="72afa-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="72afa-114">注解</span><span class="sxs-lookup"><span data-stu-id="72afa-114">Remarks</span></span>

<span data-ttu-id="72afa-115">如果未设置此属性，MAPI 会将其视为 TRUE 值。</span><span class="sxs-lookup"><span data-stu-id="72afa-115">If this property is not set, MAPI treats it as having a TRUE value.</span></span> 
  
<span data-ttu-id="72afa-116">其中某些条目不启用电子邮件的此属性设置为 FALSE 企业目录中。</span><span class="sxs-lookup"><span data-stu-id="72afa-116">Set this property to FALSE in a corporate directory where some of the entries are not email-enabled.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="72afa-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="72afa-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="72afa-118">头文件</span><span class="sxs-lookup"><span data-stu-id="72afa-118">Header files</span></span>

<span data-ttu-id="72afa-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="72afa-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="72afa-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="72afa-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="72afa-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="72afa-121">Mapitags.h</span></span>
  
> <span data-ttu-id="72afa-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="72afa-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="72afa-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72afa-123">See also</span></span>



[<span data-ttu-id="72afa-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="72afa-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="72afa-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="72afa-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="72afa-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="72afa-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="72afa-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="72afa-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

