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
ms.openlocfilehash: b396cd326dd25fd72346f9f8037e8a712b84a196
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430173"
---
# <a name="pidtagmailpermission-canonical-property"></a><span data-ttu-id="d8c36-103">PidTagMailPermission 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8c36-103">PidTagMailPermission Canonical Property</span></span>

  
  
<span data-ttu-id="d8c36-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d8c36-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d8c36-105">如果允许邮件传递用户发送和接收邮件，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="d8c36-105">Contains TRUE if the messaging user is allowed to send and receive messages.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d8c36-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d8c36-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d8c36-107">PR_MAIL_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="d8c36-107">PR_MAIL_PERMISSION</span></span>  <br/> |
|<span data-ttu-id="d8c36-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d8c36-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d8c36-109">0x3A0E</span><span class="sxs-lookup"><span data-stu-id="d8c36-109">0x3A0E</span></span>  <br/> |
|<span data-ttu-id="d8c36-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d8c36-110">Data type:</span></span>  <br/> |<span data-ttu-id="d8c36-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="d8c36-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="d8c36-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d8c36-112">Area:</span></span>  <br/> |<span data-ttu-id="d8c36-113">地址</span><span class="sxs-lookup"><span data-stu-id="d8c36-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d8c36-114">备注</span><span class="sxs-lookup"><span data-stu-id="d8c36-114">Remarks</span></span>

<span data-ttu-id="d8c36-115">如果未设置此属性，MAPI 会认为该属性具有 TRUE 值。</span><span class="sxs-lookup"><span data-stu-id="d8c36-115">If this property is not set, MAPI treats it as having a TRUE value.</span></span> 
  
<span data-ttu-id="d8c36-116">在某些条目未启用电子邮件的公司目录中，将此属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="d8c36-116">Set this property to FALSE in a corporate directory where some of the entries are not email-enabled.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d8c36-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d8c36-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d8c36-118">头文件</span><span class="sxs-lookup"><span data-stu-id="d8c36-118">Header files</span></span>

<span data-ttu-id="d8c36-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d8c36-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="d8c36-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d8c36-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="d8c36-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d8c36-121">Mapitags.h</span></span>
  
> <span data-ttu-id="d8c36-122">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d8c36-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8c36-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8c36-123">See also</span></span>



[<span data-ttu-id="d8c36-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d8c36-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d8c36-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8c36-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d8c36-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d8c36-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d8c36-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d8c36-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

