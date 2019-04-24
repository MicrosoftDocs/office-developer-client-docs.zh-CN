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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341125"
---
# <a name="pidtagserviceinstallid-canonical-property"></a><span data-ttu-id="47b63-103">PidTagServiceInstallId 规范属性</span><span class="sxs-lookup"><span data-stu-id="47b63-103">PidTagServiceInstallId Canonical Property</span></span>

  
  
<span data-ttu-id="47b63-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="47b63-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="47b63-105">提供程序的组件 ID。</span><span class="sxs-lookup"><span data-stu-id="47b63-105">The component ID of the provider.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="47b63-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="47b63-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="47b63-107">PR_SERVICE_INSTALL_ID、PR_SERVICE_INSTALL_ID_A、PR_SERVICE_INSTALL_ID_W</span><span class="sxs-lookup"><span data-stu-id="47b63-107">PR_SERVICE_INSTALL_ID, PR_SERVICE_INSTALL_ID_A, PR_SERVICE_INSTALL_ID_W</span></span>  <br/> |
|<span data-ttu-id="47b63-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="47b63-108">Identifier:</span></span>  <br/> |<span data-ttu-id="47b63-109">0x3D13</span><span class="sxs-lookup"><span data-stu-id="47b63-109">0x3D13</span></span>  <br/> |
|<span data-ttu-id="47b63-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="47b63-110">Data type:</span></span>  <br/> |<span data-ttu-id="47b63-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="47b63-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="47b63-112">区域：</span><span class="sxs-lookup"><span data-stu-id="47b63-112">Area:</span></span>  <br/> |<span data-ttu-id="47b63-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="47b63-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="47b63-114">注解</span><span class="sxs-lookup"><span data-stu-id="47b63-114">Remarks</span></span>

<span data-ttu-id="47b63-115">这些属性可用作**MsiProvideQualifiedComponent**调用的 component 参数, 以安装提供程序。</span><span class="sxs-lookup"><span data-stu-id="47b63-115">These properties may be used as the component parameter of an **MsiProvideQualifiedComponent** call to install the provider.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="47b63-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="47b63-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="47b63-117">头文件</span><span class="sxs-lookup"><span data-stu-id="47b63-117">Header files</span></span>

<span data-ttu-id="47b63-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="47b63-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="47b63-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="47b63-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="47b63-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="47b63-120">Mapitags.h</span></span>
  
> <span data-ttu-id="47b63-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="47b63-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="47b63-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47b63-122">See also</span></span>



[<span data-ttu-id="47b63-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="47b63-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="47b63-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="47b63-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="47b63-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="47b63-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="47b63-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="47b63-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

