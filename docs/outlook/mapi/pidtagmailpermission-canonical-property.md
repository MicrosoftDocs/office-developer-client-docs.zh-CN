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
ms.openlocfilehash: 4cc97647c60322783050abbebd18726434632a43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777829"
---
# <a name="pidtagmailpermission-canonical-property"></a><span data-ttu-id="a7d44-103">PidTagMailPermission 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7d44-103">PidTagMailPermission Canonical Property</span></span>

  
  
<span data-ttu-id="a7d44-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a7d44-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a7d44-105">包含 TRUE，则允许消息的用户发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="a7d44-105">Contains TRUE if the messaging user is allowed to send and receive messages.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a7d44-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a7d44-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a7d44-107">PR_MAIL_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="a7d44-107">PR_MAIL_PERMISSION</span></span>  <br/> |
|<span data-ttu-id="a7d44-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a7d44-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a7d44-109">0x3A0E</span><span class="sxs-lookup"><span data-stu-id="a7d44-109">0x3A0E</span></span>  <br/> |
|<span data-ttu-id="a7d44-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a7d44-110">Data type:</span></span>  <br/> |<span data-ttu-id="a7d44-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="a7d44-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="a7d44-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a7d44-112">Area:</span></span>  <br/> |<span data-ttu-id="a7d44-113">Address</span><span class="sxs-lookup"><span data-stu-id="a7d44-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a7d44-114">说明</span><span class="sxs-lookup"><span data-stu-id="a7d44-114">Remarks</span></span>

<span data-ttu-id="a7d44-115">如果未设置此属性，MAPI 会将其视为 TRUE 值。</span><span class="sxs-lookup"><span data-stu-id="a7d44-115">If this property is not set, MAPI treats it as having a TRUE value.</span></span> 
  
<span data-ttu-id="a7d44-116">其中某些条目不启用电子邮件的此属性设置为 FALSE 企业目录中。</span><span class="sxs-lookup"><span data-stu-id="a7d44-116">Set this property to FALSE in a corporate directory where some of the entries are not email-enabled.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a7d44-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="a7d44-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="a7d44-118">头文件</span><span class="sxs-lookup"><span data-stu-id="a7d44-118">Header files</span></span>

<span data-ttu-id="a7d44-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a7d44-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="a7d44-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a7d44-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="a7d44-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a7d44-121">Mapitags.h</span></span>
  
> <span data-ttu-id="a7d44-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a7d44-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a7d44-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7d44-123">See also</span></span>



[<span data-ttu-id="a7d44-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a7d44-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a7d44-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7d44-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a7d44-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a7d44-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a7d44-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a7d44-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

