---
title: PidTagAttachDataObject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachDataObject
api_type:
- HeaderDef
ms.assetid: b76312c6-7682-4ded-be25-55e21b0b091b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3961330476cad8947f94152e49c90adb1e8f8b21
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339282"
---
# <a name="pidtagattachdataobject-canonical-property"></a><span data-ttu-id="128bf-103">PidTagAttachDataObject 规范属性</span><span class="sxs-lookup"><span data-stu-id="128bf-103">PidTagAttachDataObject Canonical Property</span></span>

  
  
<span data-ttu-id="128bf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="128bf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="128bf-105">包含通常通过对象链接和嵌入 (OLE) **IStorage**接口访问的附件对象。</span><span class="sxs-lookup"><span data-stu-id="128bf-105">Contains an attachment object typically accessed through the Object Linking and Embedding (OLE) **IStorage** interface.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="128bf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="128bf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="128bf-107">PR_ATTACH_DATA_OBJ</span><span class="sxs-lookup"><span data-stu-id="128bf-107">PR_ATTACH_DATA_OBJ</span></span>  <br/> |
|<span data-ttu-id="128bf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="128bf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="128bf-109">0x3701</span><span class="sxs-lookup"><span data-stu-id="128bf-109">0x3701</span></span>  <br/> |
|<span data-ttu-id="128bf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="128bf-110">Data type:</span></span>  <br/> |<span data-ttu-id="128bf-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="128bf-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="128bf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="128bf-112">Area:</span></span>  <br/> |<span data-ttu-id="128bf-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="128bf-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="128bf-114">注解</span><span class="sxs-lookup"><span data-stu-id="128bf-114">Remarks</span></span>

<span data-ttu-id="128bf-115">如果**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值为**ATTACH_EMBEDDED_MSG**或**ATTACH_OLE**, 则此属性将保留附件。</span><span class="sxs-lookup"><span data-stu-id="128bf-115">This property holds the attachment when the value of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property is **ATTACH_EMBEDDED_MSG** or **ATTACH_OLE**.</span></span> <span data-ttu-id="128bf-116">可以从**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定 OLE 编码类型。</span><span class="sxs-lookup"><span data-stu-id="128bf-116">The OLE encoding type can be determined from **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)).</span></span> 
  
<span data-ttu-id="128bf-117">对于与**ATTACH_EMBEDDED_MSG**值关联的附件, 可以使用[IMessage: IMAPIProp](imessageimapiprop.md)接口来实现更快的访问。</span><span class="sxs-lookup"><span data-stu-id="128bf-117">For an attachment associated with the **ATTACH_EMBEDDED_MSG** value, the [IMessage:IMAPIProp](imessageimapiprop.md) interface can be used for faster access.</span></span> 
  
<span data-ttu-id="128bf-118">对于嵌入的动态 OLE 对象, **PR_ATTACH_DATA_OBJ**属性包含其自己的呈现信息, 并且**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 属性不应为 "不存在" 或 "空"。</span><span class="sxs-lookup"><span data-stu-id="128bf-118">For an embedded dynamic OLE object, the **PR_ATTACH_DATA_OBJ** property contains its own rendering information, and the **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) property should be either nonexistent or empty.</span></span> 
  
<span data-ttu-id="128bf-119">对于 OLE 文档文件附件, 邮件存储提供程序必须响应**PR_ATTACH_DATA_OBJ**上的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)呼叫, 并且可以选择响应**PR_ATTACH_DATA_BIN**上的呼叫 ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md) )。).</span><span class="sxs-lookup"><span data-stu-id="128bf-119">For an OLE document file attachment, the message store provider must respond to an [IMAPIProp::OpenProperty](imapiprop-openproperty.md) call on **PR_ATTACH_DATA_OBJ** and may optionally respond to a call on **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)).</span></span> <span data-ttu-id="128bf-120">**PR_ATTACH_DATA_BIN**和**PR_ATTACH_DATA_OBJ**属性共享相同的属性标识符, 因此这是同一属性的两个格式副本。</span><span class="sxs-lookup"><span data-stu-id="128bf-120">The **PR_ATTACH_DATA_BIN** and **PR_ATTACH_DATA_OBJ** properties share the same property identifier and thus are two renditions of the same property.</span></span> 
  
<span data-ttu-id="128bf-121">对于存储对象 (例如, 采用 OLE 2.0 docfile 格式的复合文件), 某些服务提供程序允许使用 MAPI **IStreamDocfile**接口打开它, 而没有其他成员的**IStream**子类将用于优化性能。</span><span class="sxs-lookup"><span data-stu-id="128bf-121">For a storage object, such as a compound file in OLE 2.0 docfile format, some service providers allow it to be opened with the MAPI **IStreamDocfile** interface, a subclass of **IStream** with no additional members, designed to optimize performance.</span></span> <span data-ttu-id="128bf-122">可能的保存足以证明试图通过**IStreamDocfile**打开**PR_ATTACH_DATA_OBJ** 。</span><span class="sxs-lookup"><span data-stu-id="128bf-122">The potential saving is enough to justify attempting to open **PR_ATTACH_DATA_OBJ** through **IStreamDocfile**.</span></span> <span data-ttu-id="128bf-123">如果返回**MAPI_E_INTERFACE_NOT_SUPPORTED** , 则客户端可以使用**IStream**打开**PR_ATTACH_DATA_BIN** 。</span><span class="sxs-lookup"><span data-stu-id="128bf-123">If **MAPI_E_INTERFACE_NOT_SUPPORTED** is returned, the client can then open **PR_ATTACH_DATA_BIN** with **IStream**.</span></span> 
  
<span data-ttu-id="128bf-124">如果客户端应用程序或服务提供程序无法通过使用**PR_ATTACH_DATA_OBJ**和**PR_ATTACH_METHOD**的帮助打开附件子方法, 则应使用**PR_ATTACH_DATA_BIN**。</span><span class="sxs-lookup"><span data-stu-id="128bf-124">If the client application or service provider cannot open an attachment subobject by using **PR_ATTACH_DATA_OBJ** with the help of **PR_ATTACH_METHOD**, it should use **PR_ATTACH_DATA_BIN**.</span></span> 
  
<span data-ttu-id="128bf-125">有关 ole 接口和格式的详细信息, 请参阅[ole and Data Transfer](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="128bf-125">For more information on OLE interfaces and formats, see [OLE and Data Transfer](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="128bf-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="128bf-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="128bf-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="128bf-127">Protocol specifications</span></span>

<span data-ttu-id="128bf-128">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="128bf-128">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="128bf-129">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="128bf-129">Handles message and attachment objects.</span></span>
    
## <a name="header-files"></a><span data-ttu-id="128bf-130">头文件</span><span class="sxs-lookup"><span data-stu-id="128bf-130">Header Files</span></span>

<span data-ttu-id="128bf-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="128bf-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="128bf-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="128bf-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="128bf-133">Mapitags</span><span class="sxs-lookup"><span data-stu-id="128bf-133">Mapitags.h</span></span>
  
> <span data-ttu-id="128bf-134">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="128bf-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="128bf-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="128bf-135">See also</span></span>



[<span data-ttu-id="128bf-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="128bf-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="128bf-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="128bf-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="128bf-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="128bf-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="128bf-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="128bf-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

