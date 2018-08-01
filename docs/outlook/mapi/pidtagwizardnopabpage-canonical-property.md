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
ms.openlocfilehash: b393155d00b47fa8cce23c1b5ac7043237a58983
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778558"
---
# <a name="pidtagwizardnopabpage-canonical-property"></a><span data-ttu-id="5b2c5-103">PidTagWizardNoPabPage 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b2c5-103">PidTagWizardNoPabPage Canonical Property</span></span>

  
  
<span data-ttu-id="5b2c5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5b2c5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5b2c5-105">若要隐藏个人通讯簿 (PAB) 页配置文件向导时，此属性包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5b2c5-105">This property contains TRUE if the profile wizard is to suppress the personal address book (PAB) page.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5b2c5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5b2c5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5b2c5-107">PR_WIZARD_NO_PAB_PAGE</span><span class="sxs-lookup"><span data-stu-id="5b2c5-107">PR_WIZARD_NO_PAB_PAGE</span></span>  <br/> |
|<span data-ttu-id="5b2c5-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5b2c5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5b2c5-109">0x6701</span><span class="sxs-lookup"><span data-stu-id="5b2c5-109">0x6701</span></span>  <br/> |
|<span data-ttu-id="5b2c5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5b2c5-110">Data type:</span></span>  <br/> |<span data-ttu-id="5b2c5-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="5b2c5-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="5b2c5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5b2c5-112">Area:</span></span>  <br/> |<span data-ttu-id="5b2c5-113">Exchange 管理</span><span class="sxs-lookup"><span data-stu-id="5b2c5-113">Exchange Administrative</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5b2c5-114">说明</span><span class="sxs-lookup"><span data-stu-id="5b2c5-114">Remarks</span></span>

<span data-ttu-id="5b2c5-115">调用基于[LAUNCHWIZARDENTRY](launchwizardentry.md)函数原型的函数时，服务提供商可以设置该属性。</span><span class="sxs-lookup"><span data-stu-id="5b2c5-115">Service providers can set this property when calling a function based on the [LAUNCHWIZARDENTRY](launchwizardentry.md) function prototype.</span></span> <span data-ttu-id="5b2c5-116">此属性会通知配置文件向导提供程序不希望 PAB 页后，可以在用户对话框显示。</span><span class="sxs-lookup"><span data-stu-id="5b2c5-116">This property tells the profile wizard that the provider does not want the PAB page to be displayed during the user dialog.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="5b2c5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="5b2c5-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="5b2c5-118">头文件</span><span class="sxs-lookup"><span data-stu-id="5b2c5-118">Header files</span></span>

<span data-ttu-id="5b2c5-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5b2c5-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="5b2c5-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5b2c5-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="5b2c5-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5b2c5-121">Mapitags.h</span></span>
  
> <span data-ttu-id="5b2c5-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5b2c5-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5b2c5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b2c5-123">See also</span></span>



[<span data-ttu-id="5b2c5-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5b2c5-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5b2c5-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b2c5-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5b2c5-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5b2c5-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5b2c5-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5b2c5-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

