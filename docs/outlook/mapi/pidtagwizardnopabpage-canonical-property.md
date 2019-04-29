---
title: PidTagWizardNoPabPage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagWizardNoPabPage
api_type:
- COM
ms.assetid: 9cec22cd-798d-41f6-9ebd-c7354f2162c2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc971be76dbaa83176f207411f9f125ffee386cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424460"
---
# <a name="pidtagwizardnopabpage-canonical-property"></a><span data-ttu-id="1306b-103">PidTagWizardNoPabPage 规范属性</span><span class="sxs-lookup"><span data-stu-id="1306b-103">PidTagWizardNoPabPage Canonical Property</span></span>

  
  
<span data-ttu-id="1306b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1306b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1306b-105">如果配置文件向导要禁止显示 "个人通讯簿 (PAB)" 页面, 则此属性包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1306b-105">This property contains TRUE if the profile wizard is to suppress the personal address book (PAB) page.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1306b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1306b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1306b-107">PR_WIZARD_NO_PAB_PAGE</span><span class="sxs-lookup"><span data-stu-id="1306b-107">PR_WIZARD_NO_PAB_PAGE</span></span>  <br/> |
|<span data-ttu-id="1306b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1306b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1306b-109">0x6701</span><span class="sxs-lookup"><span data-stu-id="1306b-109">0x6701</span></span>  <br/> |
|<span data-ttu-id="1306b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1306b-110">Data type:</span></span>  <br/> |<span data-ttu-id="1306b-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="1306b-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="1306b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1306b-112">Area:</span></span>  <br/> |<span data-ttu-id="1306b-113">Exchange 管理</span><span class="sxs-lookup"><span data-stu-id="1306b-113">Exchange Administrative</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1306b-114">说明</span><span class="sxs-lookup"><span data-stu-id="1306b-114">Remarks</span></span>

<span data-ttu-id="1306b-115">服务提供程序在调用基于[LAUNCHWIZARDENTRY](launchwizardentry.md)函数原型的函数时, 可以设置此属性。</span><span class="sxs-lookup"><span data-stu-id="1306b-115">Service providers can set this property when calling a function based on the [LAUNCHWIZARDENTRY](launchwizardentry.md) function prototype.</span></span> <span data-ttu-id="1306b-116">此属性告知配置文件向导, 提供程序不希望在用户对话过程中显示 PAB 页面。</span><span class="sxs-lookup"><span data-stu-id="1306b-116">This property tells the profile wizard that the provider does not want the PAB page to be displayed during the user dialog.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1306b-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="1306b-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1306b-118">头文件</span><span class="sxs-lookup"><span data-stu-id="1306b-118">Header files</span></span>

<span data-ttu-id="1306b-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1306b-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="1306b-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1306b-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="1306b-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="1306b-121">Mapitags.h</span></span>
  
> <span data-ttu-id="1306b-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1306b-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1306b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1306b-123">See also</span></span>



[<span data-ttu-id="1306b-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1306b-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1306b-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1306b-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1306b-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1306b-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1306b-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1306b-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

