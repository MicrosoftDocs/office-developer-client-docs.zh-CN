---
title: PidLidTaskActualEffort 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskActualEffort
api_type:
- COM
ms.assetid: 8e9a9432-bf50-4333-82ec-fba19dff8006
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7eb51396f4575a8f8f9ce15aff84eb894773e979
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331169"
---
# <a name="pidlidtaskactualeffort-canonical-property"></a><span data-ttu-id="66d31-103">PidLidTaskActualEffort 规范属性</span><span class="sxs-lookup"><span data-stu-id="66d31-103">PidLidTaskActualEffort Canonical Property</span></span>

  
  
<span data-ttu-id="66d31-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66d31-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66d31-105">指示用户执行任务的分钟数。</span><span class="sxs-lookup"><span data-stu-id="66d31-105">Indicates the number of minutes that the user performed a task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66d31-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="66d31-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="66d31-107">dispidTaskActualEffort</span><span class="sxs-lookup"><span data-stu-id="66d31-107">dispidTaskActualEffort</span></span>  <br/> |
|<span data-ttu-id="66d31-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="66d31-108">Property set:</span></span>  <br/> |<span data-ttu-id="66d31-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="66d31-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="66d31-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="66d31-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="66d31-111">0x00008110</span><span class="sxs-lookup"><span data-stu-id="66d31-111">0x00008110</span></span>  <br/> |
|<span data-ttu-id="66d31-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="66d31-112">Data type:</span></span>  <br/> |<span data-ttu-id="66d31-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="66d31-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="66d31-114">区域：</span><span class="sxs-lookup"><span data-stu-id="66d31-114">Area:</span></span>  <br/> |<span data-ttu-id="66d31-115">任务</span><span class="sxs-lookup"><span data-stu-id="66d31-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="66d31-116">注解</span><span class="sxs-lookup"><span data-stu-id="66d31-116">Remarks</span></span>

<span data-ttu-id="66d31-117">该值必须大于或等于 0, 小于 0x5AE980DF (1525252319), 其中480分钟等于1天, 而2400分钟等于一周 (在一个工作日中为八个小时, 在一个工作周中为五天)。</span><span class="sxs-lookup"><span data-stu-id="66d31-117">The value must be greater than or equal to 0 and less than 0x5AE980DF (1,525,252,319), where 480 minutes equal one day and 2400 minutes equal one week (eight hours in a work day and five days in a work week).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="66d31-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="66d31-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="66d31-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="66d31-119">Protocol specifications</span></span>

<span data-ttu-id="66d31-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66d31-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66d31-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="66d31-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="66d31-122">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66d31-122">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66d31-123">指定允许用于联系人和个人通讯组列表对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="66d31-123">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="66d31-124">头文件</span><span class="sxs-lookup"><span data-stu-id="66d31-124">Header files</span></span>

<span data-ttu-id="66d31-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="66d31-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="66d31-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="66d31-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="66d31-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66d31-127">See also</span></span>



[<span data-ttu-id="66d31-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="66d31-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="66d31-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="66d31-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="66d31-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="66d31-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="66d31-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="66d31-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

