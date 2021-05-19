---
title: PidTagReceiveFolderSettings 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceiveFolderSettings
api_type:
- COM
ms.assetid: 2f0b1679-05b0-4580-b6d2-474fe3f9d012
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8590e357252089aaa49a71d443037b9b9ed77ee4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415052"
---
# <a name="pidtagreceivefoldersettings-canonical-property"></a><span data-ttu-id="694ec-103">PidTagReceiveFolderSettings 规范属性</span><span class="sxs-lookup"><span data-stu-id="694ec-103">PidTagReceiveFolderSettings Canonical Property</span></span>

  
  
<span data-ttu-id="694ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="694ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="694ec-105">包含邮件存储的接收文件夹设置的表。</span><span class="sxs-lookup"><span data-stu-id="694ec-105">Contains a table of a message store's receive folder settings.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="694ec-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="694ec-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="694ec-107">PR_RECEIVE_FOLDER_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="694ec-107">PR_RECEIVE_FOLDER_SETTINGS</span></span>  <br/> |
|<span data-ttu-id="694ec-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="694ec-108">Identifier:</span></span>  <br/> |<span data-ttu-id="694ec-109">0x3415</span><span class="sxs-lookup"><span data-stu-id="694ec-109">0x3415</span></span>  <br/> |
|<span data-ttu-id="694ec-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="694ec-110">Data type:</span></span>  <br/> |<span data-ttu-id="694ec-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="694ec-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="694ec-112">区域：</span><span class="sxs-lookup"><span data-stu-id="694ec-112">Area:</span></span>  <br/> |<span data-ttu-id="694ec-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="694ec-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="694ec-114">备注</span><span class="sxs-lookup"><span data-stu-id="694ec-114">Remarks</span></span>

<span data-ttu-id="694ec-115">此属性可以在 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 操作中排除，也可以包含在 [IMAPIProp：：CopyProps 操作](imapiprop-copyprops.md) 中。</span><span class="sxs-lookup"><span data-stu-id="694ec-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="694ec-116">作为类型为 [PT_OBJECT，IMAPIProp：：GetProps](imapiprop-getprops.md) 方法无法成功检索它;它的内容应该由 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法访问，并请求具有标识符的IID_IMAPITable。</span><span class="sxs-lookup"><span data-stu-id="694ec-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the interface with identifier IID_IMAPITable.</span></span> <span data-ttu-id="694ec-117">如果已设置，服务提供商必须报告给 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，但可以选择是否报告（如果未设置）。</span><span class="sxs-lookup"><span data-stu-id="694ec-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="694ec-118">若要检索表内容，客户端应用程序应调用 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="694ec-118">To retrieve table contents, a client application should call the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> <span data-ttu-id="694ec-119">有关详细信息，请参阅 [接收文件夹表](receive-folder-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="694ec-119">For more information, see [Receive Folder Tables](receive-folder-tables.md).</span></span>
  
<span data-ttu-id="694ec-120">此属性包含邮件存储的接收文件夹的映射表。</span><span class="sxs-lookup"><span data-stu-id="694ec-120">This property contains a table of mappings of the receive folders for the message store.</span></span> <span data-ttu-id="694ec-121">对 **此属性调用 OpenProperty** 等效于在邮件存储上调用 **GetReceiveFolderTable。**</span><span class="sxs-lookup"><span data-stu-id="694ec-121">Calling **OpenProperty** on this property is equivalent to calling **GetReceiveFolderTable** on the message store.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="694ec-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="694ec-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="694ec-123">头文件</span><span class="sxs-lookup"><span data-stu-id="694ec-123">Header files</span></span>

<span data-ttu-id="694ec-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="694ec-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="694ec-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="694ec-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="694ec-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="694ec-126">Mapitags.h</span></span>
  
> <span data-ttu-id="694ec-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="694ec-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="694ec-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="694ec-128">See also</span></span>



[<span data-ttu-id="694ec-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="694ec-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="694ec-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="694ec-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="694ec-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="694ec-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="694ec-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="694ec-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

