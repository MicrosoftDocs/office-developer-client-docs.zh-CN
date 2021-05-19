---
title: PidTagMessageCodepage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageCodepage
api_type:
- HeaderDef
ms.assetid: eef73e34-470c-4c37-94ce-ea95fe83bc10
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 49f2c1c0b8af21f837582698763c17b9c41e1923
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358462"
---
# <a name="pidtagmessagecodepage-canonical-property"></a><span data-ttu-id="95bdb-103">PidTagMessageCodepage 规范属性</span><span class="sxs-lookup"><span data-stu-id="95bdb-103">PidTagMessageCodepage Canonical Property</span></span>

  
  
<span data-ttu-id="95bdb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95bdb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95bdb-105">包含用于邮件的代码页。</span><span class="sxs-lookup"><span data-stu-id="95bdb-105">Contains the code page that is used for the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="95bdb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="95bdb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="95bdb-107">PR_MESSAGE_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="95bdb-107">PR_MESSAGE_CODEPAGE</span></span>  <br/> |
|<span data-ttu-id="95bdb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="95bdb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="95bdb-109">0x3FFD</span><span class="sxs-lookup"><span data-stu-id="95bdb-109">0x3FFD</span></span>  <br/> |
|<span data-ttu-id="95bdb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="95bdb-110">Data type:</span></span>  <br/> |<span data-ttu-id="95bdb-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="95bdb-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="95bdb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="95bdb-112">Area:</span></span>  <br/> |<span data-ttu-id="95bdb-113">常见</span><span class="sxs-lookup"><span data-stu-id="95bdb-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="95bdb-114">备注</span><span class="sxs-lookup"><span data-stu-id="95bdb-114">Remarks</span></span>

<span data-ttu-id="95bdb-115">如果此属性设置为零，则使用文件夹对象代码页 (0) 。</span><span class="sxs-lookup"><span data-stu-id="95bdb-115">The folder object code page is used if this property is set to zero (0).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="95bdb-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="95bdb-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="95bdb-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="95bdb-117">Protocol specifications</span></span>

<span data-ttu-id="95bdb-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="95bdb-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="95bdb-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="95bdb-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="95bdb-120">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="95bdb-120">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="95bdb-121">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="95bdb-121">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="95bdb-122">[[MS-OXPFOAB]](https://msdn.microsoft.com/library/258a07a7-34a7-4373-87c1-cddf51447d00%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="95bdb-122">[[MS-OXPFOAB]](https://msdn.microsoft.com/library/258a07a7-34a7-4373-87c1-cddf51447d00%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="95bdb-123">指定从服务器到客户端 (OAB) 脱机通讯簿的方法。</span><span class="sxs-lookup"><span data-stu-id="95bdb-123">Specifies the method of delivering offline address book (OAB) data from server to client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="95bdb-124">头文件</span><span class="sxs-lookup"><span data-stu-id="95bdb-124">Header files</span></span>

<span data-ttu-id="95bdb-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="95bdb-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="95bdb-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="95bdb-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="95bdb-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="95bdb-127">Mapitags.h</span></span>
  
> <span data-ttu-id="95bdb-128">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="95bdb-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="95bdb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95bdb-129">See also</span></span>



[<span data-ttu-id="95bdb-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="95bdb-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="95bdb-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="95bdb-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="95bdb-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="95bdb-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="95bdb-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="95bdb-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

