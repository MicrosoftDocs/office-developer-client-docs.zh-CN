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
ms.openlocfilehash: e93325873f1d9e89bb591d136df04aa27403375f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778147"
---
# <a name="pidtagreceivefoldersettings-canonical-property"></a><span data-ttu-id="fabba-103">PidTagReceiveFolderSettings 规范属性</span><span class="sxs-lookup"><span data-stu-id="fabba-103">PidTagReceiveFolderSettings Canonical Property</span></span>

  
  
<span data-ttu-id="fabba-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fabba-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fabba-105">包含表的邮件存储的接收文件夹设置。</span><span class="sxs-lookup"><span data-stu-id="fabba-105">Contains a table of a message store's receive folder settings.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fabba-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fabba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fabba-107">PR_RECEIVE_FOLDER_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="fabba-107">PR_RECEIVE_FOLDER_SETTINGS</span></span>  <br/> |
|<span data-ttu-id="fabba-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="fabba-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fabba-109">0x3415</span><span class="sxs-lookup"><span data-stu-id="fabba-109">0x3415</span></span>  <br/> |
|<span data-ttu-id="fabba-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fabba-110">Data type:</span></span>  <br/> |<span data-ttu-id="fabba-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="fabba-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="fabba-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fabba-112">Area:</span></span>  <br/> |<span data-ttu-id="fabba-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="fabba-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fabba-114">说明</span><span class="sxs-lookup"><span data-stu-id="fabba-114">Remarks</span></span>

<span data-ttu-id="fabba-115">可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。</span><span class="sxs-lookup"><span data-stu-id="fabba-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="fabba-116">作为 PT_OBJECT 类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法;应由[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，请求具有标识符 IID_IMAPITable 接口访问其内容。</span><span class="sxs-lookup"><span data-stu-id="fabba-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the interface with identifier IID_IMAPITable.</span></span> <span data-ttu-id="fabba-117">服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法或如果其设置，但可以选择将其报告不如果它未设置。</span><span class="sxs-lookup"><span data-stu-id="fabba-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="fabba-118">若要检索目录，客户端应用程序应调用[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fabba-118">To retrieve table contents, a client application should call the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> <span data-ttu-id="fabba-119">有关详细信息，请参阅[接收文件夹表](receive-folder-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="fabba-119">For more information, see [Receive Folder Tables](receive-folder-tables.md).</span></span>
  
<span data-ttu-id="fabba-120">此属性包含的接收文件夹的消息存储库的映射表。</span><span class="sxs-lookup"><span data-stu-id="fabba-120">This property contains a table of mappings of the receive folders for the message store.</span></span> <span data-ttu-id="fabba-121">调用**OpenProperty**此属性等效于调用**GetReceiveFolderTable**消息存储库。</span><span class="sxs-lookup"><span data-stu-id="fabba-121">Calling **OpenProperty** on this property is equivalent to calling **GetReceiveFolderTable** on the message store.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="fabba-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="fabba-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fabba-123">头文件</span><span class="sxs-lookup"><span data-stu-id="fabba-123">Header files</span></span>

<span data-ttu-id="fabba-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fabba-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="fabba-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fabba-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="fabba-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fabba-126">Mapitags.h</span></span>
  
> <span data-ttu-id="fabba-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fabba-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fabba-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fabba-128">See also</span></span>



[<span data-ttu-id="fabba-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fabba-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fabba-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fabba-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fabba-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fabba-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fabba-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fabba-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

