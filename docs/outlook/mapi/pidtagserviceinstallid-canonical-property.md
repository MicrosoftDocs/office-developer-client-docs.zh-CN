---
title: PidTagServiceInstallId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceInstallId
api_type:
- COM
ms.assetid: 1dd14858-2ce6-4629-a2f1-82d23cd6576b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 159a25347cd64b44f42dbb5052425ebb67894a9b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430369"
---
# <a name="pidtagserviceinstallid-canonical-property"></a><span data-ttu-id="9fe6f-103">PidTagServiceInstallId 规范属性</span><span class="sxs-lookup"><span data-stu-id="9fe6f-103">PidTagServiceInstallId Canonical Property</span></span>

  
  
<span data-ttu-id="9fe6f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9fe6f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9fe6f-105">提供程序的组件 ID。</span><span class="sxs-lookup"><span data-stu-id="9fe6f-105">The component ID of the provider.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9fe6f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9fe6f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9fe6f-107">PR_SERVICE_INSTALL_ID、PR_SERVICE_INSTALL_ID_A、PR_SERVICE_INSTALL_ID_W</span><span class="sxs-lookup"><span data-stu-id="9fe6f-107">PR_SERVICE_INSTALL_ID, PR_SERVICE_INSTALL_ID_A, PR_SERVICE_INSTALL_ID_W</span></span>  <br/> |
|<span data-ttu-id="9fe6f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9fe6f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9fe6f-109">0x3D13</span><span class="sxs-lookup"><span data-stu-id="9fe6f-109">0x3D13</span></span>  <br/> |
|<span data-ttu-id="9fe6f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9fe6f-110">Data type:</span></span>  <br/> |<span data-ttu-id="9fe6f-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9fe6f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="9fe6f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9fe6f-112">Area:</span></span>  <br/> |<span data-ttu-id="9fe6f-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="9fe6f-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9fe6f-114">备注</span><span class="sxs-lookup"><span data-stu-id="9fe6f-114">Remarks</span></span>

<span data-ttu-id="9fe6f-115">这些属性可以用作 **MsiProvideQualifiedComponent** 调用的组件参数来安装提供程序。</span><span class="sxs-lookup"><span data-stu-id="9fe6f-115">These properties may be used as the component parameter of an **MsiProvideQualifiedComponent** call to install the provider.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9fe6f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="9fe6f-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9fe6f-117">头文件</span><span class="sxs-lookup"><span data-stu-id="9fe6f-117">Header files</span></span>

<span data-ttu-id="9fe6f-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9fe6f-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="9fe6f-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9fe6f-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="9fe6f-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9fe6f-120">Mapitags.h</span></span>
  
> <span data-ttu-id="9fe6f-121">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9fe6f-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9fe6f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fe6f-122">See also</span></span>



[<span data-ttu-id="9fe6f-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9fe6f-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9fe6f-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9fe6f-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9fe6f-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9fe6f-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9fe6f-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9fe6f-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

