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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356740"
---
# <a name="pidtagreceivefoldersettings-canonical-property"></a><span data-ttu-id="0b4ff-103">PidTagReceiveFolderSettings 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b4ff-103">PidTagReceiveFolderSettings Canonical Property</span></span>

  
  
<span data-ttu-id="0b4ff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0b4ff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0b4ff-105">包含邮件存储区的接收文件夹设置的表。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-105">Contains a table of a message store's receive folder settings.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0b4ff-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0b4ff-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0b4ff-107">PR_RECEIVE_FOLDER_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="0b4ff-107">PR_RECEIVE_FOLDER_SETTINGS</span></span>  <br/> |
|<span data-ttu-id="0b4ff-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0b4ff-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0b4ff-109">0x3415</span><span class="sxs-lookup"><span data-stu-id="0b4ff-109">0x3415</span></span>  <br/> |
|<span data-ttu-id="0b4ff-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0b4ff-110">Data type:</span></span>  <br/> |<span data-ttu-id="0b4ff-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="0b4ff-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="0b4ff-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0b4ff-112">Area:</span></span>  <br/> |<span data-ttu-id="0b4ff-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="0b4ff-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0b4ff-114">注解</span><span class="sxs-lookup"><span data-stu-id="0b4ff-114">Remarks</span></span>

<span data-ttu-id="0b4ff-115">此属性可以排除在[IMAPIProp:: CopyTo](imapiprop-copyto.md)操作中, 也可以包含在[IMAPIProp:: CopyProps](imapiprop-copyprops.md)操作中。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="0b4ff-116">作为 PT_OBJECT 类型的属性, [IMAPIProp:: GetProps](imapiprop-getprops.md)方法无法成功检索它;其内容应由[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法访问, 请求提供带有标识符 IID_IMAPITable 的接口。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the interface with identifier IID_IMAPITable.</span></span> <span data-ttu-id="0b4ff-117">如果设置了服务提供程序, 则必须将其报告给[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 但如果未设置, 则可以选择报告它。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="0b4ff-118">若要检索表内容, 客户端应用程序应调用[IMsgStore:: GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-118">To retrieve table contents, a client application should call the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> <span data-ttu-id="0b4ff-119">有关详细信息, 请参阅[接收文件夹表](receive-folder-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-119">For more information, see [Receive Folder Tables](receive-folder-tables.md).</span></span>
  
<span data-ttu-id="0b4ff-120">此属性包含邮件存储区的接收文件夹的映射表。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-120">This property contains a table of mappings of the receive folders for the message store.</span></span> <span data-ttu-id="0b4ff-121">对此属性调用**OpenProperty**等效于调用邮件存储区上的**GetReceiveFolderTable** 。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-121">Calling **OpenProperty** on this property is equivalent to calling **GetReceiveFolderTable** on the message store.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0b4ff-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="0b4ff-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0b4ff-123">头文件</span><span class="sxs-lookup"><span data-stu-id="0b4ff-123">Header files</span></span>

<span data-ttu-id="0b4ff-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0b4ff-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="0b4ff-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="0b4ff-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0b4ff-126">Mapitags.h</span></span>
  
> <span data-ttu-id="0b4ff-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0b4ff-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0b4ff-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b4ff-128">See also</span></span>



[<span data-ttu-id="0b4ff-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0b4ff-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0b4ff-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b4ff-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0b4ff-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0b4ff-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0b4ff-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0b4ff-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

