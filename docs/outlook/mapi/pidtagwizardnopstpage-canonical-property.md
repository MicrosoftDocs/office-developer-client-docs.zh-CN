---
title: PidTagWizardNoPstPage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagWizardNoPstPage
api_type:
- COM
ms.assetid: 1ac09578-892b-4c72-92f6-c2419ac2efe8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e816af2ce60b4c06ae14f720cf7c36d58468d09d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422885"
---
# <a name="pidtagwizardnopstpage-canonical-property"></a><span data-ttu-id="426e5-103">PidTagWizardNoPstPage 规范属性</span><span class="sxs-lookup"><span data-stu-id="426e5-103">PidTagWizardNoPstPage Canonical Property</span></span>

  
  
<span data-ttu-id="426e5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="426e5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="426e5-105">如果配置文件向导要禁止 PST 邮件页上的个人邮件存储， (TRUE) TRUE。</span><span class="sxs-lookup"><span data-stu-id="426e5-105">This property contains TRUE if the profile wizard is to suppress the personal message store (PST) page.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="426e5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="426e5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="426e5-107">PR_WIZARD_NO_PST_PAGE</span><span class="sxs-lookup"><span data-stu-id="426e5-107">PR_WIZARD_NO_PST_PAGE</span></span>  <br/> |
|<span data-ttu-id="426e5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="426e5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="426e5-109">0x6700</span><span class="sxs-lookup"><span data-stu-id="426e5-109">0x6700</span></span>  <br/> |
|<span data-ttu-id="426e5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="426e5-110">Data type:</span></span>  <br/> |<span data-ttu-id="426e5-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="426e5-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="426e5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="426e5-112">Area:</span></span>  <br/> |<span data-ttu-id="426e5-113">Exchange管理</span><span class="sxs-lookup"><span data-stu-id="426e5-113">Exchange Administrative</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="426e5-114">备注</span><span class="sxs-lookup"><span data-stu-id="426e5-114">Remarks</span></span>

<span data-ttu-id="426e5-115">当基于 [LAUNCHWIZARDENTRY](launchwizardentry.md) 函数原型调用函数时，服务提供商可以设置此属性。</span><span class="sxs-lookup"><span data-stu-id="426e5-115">Service providers can set this property when calling a function based on the [LAUNCHWIZARDENTRY](launchwizardentry.md) function prototype.</span></span> <span data-ttu-id="426e5-116">此属性告知配置文件向导提供程序不希望在用户对话框期间显示 PST 页面。</span><span class="sxs-lookup"><span data-stu-id="426e5-116">This property tells the profile wizard that the provider does not want the PST page to be displayed during the user dialog.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="426e5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="426e5-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="426e5-118">头文件</span><span class="sxs-lookup"><span data-stu-id="426e5-118">Header files</span></span>

<span data-ttu-id="426e5-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="426e5-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="426e5-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="426e5-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="426e5-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="426e5-121">Mapitags.h</span></span>
  
> <span data-ttu-id="426e5-122">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="426e5-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="426e5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="426e5-123">See also</span></span>



[<span data-ttu-id="426e5-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="426e5-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="426e5-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="426e5-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="426e5-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="426e5-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="426e5-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="426e5-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

