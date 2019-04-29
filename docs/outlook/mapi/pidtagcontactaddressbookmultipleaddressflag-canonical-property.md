---
title: PidTagContactAddressBookMultipleAddressFlag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookMultipleAddressFlag
api_type:
- HeaderDef
ms.assetid: aefc34c5-1beb-44cf-a455-90f466e157ce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6fabb03d552f195c200b0ecbd8fd69f470c0e1fd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431566"
---
# <a name="pidtagcontactaddressbookmultipleaddressflag-canonical-property"></a><span data-ttu-id="c6361-103">PidTagContactAddressBookMultipleAddressFlag 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6361-103">PidTagContactAddressBookMultipleAddressFlag Canonical Property</span></span>

  
  
<span data-ttu-id="c6361-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6361-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6361-105">包含一个标志, 当提供程序支持每个联系人项目的多个电子邮件地址时, 该标志为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c6361-105">Contains a flag that is TRUE when the provider supports multiple email addresses per contact item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c6361-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c6361-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c6361-107">PR_CONTAB_MULTI_ADDR_FLAG</span><span class="sxs-lookup"><span data-stu-id="c6361-107">PR_CONTAB_MULTI_ADDR_FLAG</span></span>  <br/> |
|<span data-ttu-id="c6361-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c6361-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c6361-109">0x6614</span><span class="sxs-lookup"><span data-stu-id="c6361-109">0x6614</span></span>  <br/> |
|<span data-ttu-id="c6361-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c6361-110">Data type:</span></span>  <br/> |<span data-ttu-id="c6361-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="c6361-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="c6361-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c6361-112">Area:</span></span>  <br/> |<span data-ttu-id="c6361-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="c6361-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c6361-114">说明</span><span class="sxs-lookup"><span data-stu-id="c6361-114">Remarks</span></span>

<span data-ttu-id="c6361-115">如果此属性为 TRUE, 则提供程序不允许没有电子邮件地址的联系人。</span><span class="sxs-lookup"><span data-stu-id="c6361-115">If this property is TRUE, the provider does not allow contacts without email addresses.</span></span> <span data-ttu-id="c6361-116">如果为 FALSE, 则提供程序将显示所有联系人, 无论其是否有主电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c6361-116">If FALSE, the provider shows all contacts whether or not they have a primary email address.</span></span> <span data-ttu-id="c6361-117">只有主电子邮件地址将生效。</span><span class="sxs-lookup"><span data-stu-id="c6361-117">Only the primary email address will be honored.</span></span> <span data-ttu-id="c6361-118">这是联系人通讯簿容器的属性, 以及联系人通讯簿容器表中的列。</span><span class="sxs-lookup"><span data-stu-id="c6361-118">This is a property on a Contact Address Book container, and a column in the table of Contact Address Book containers.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c6361-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="c6361-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c6361-120">头文件</span><span class="sxs-lookup"><span data-stu-id="c6361-120">Header files</span></span>

<span data-ttu-id="c6361-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c6361-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="c6361-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c6361-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="c6361-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c6361-123">Mapitags.h</span></span>
  
> <span data-ttu-id="c6361-124">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c6361-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c6361-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6361-125">See also</span></span>



[<span data-ttu-id="c6361-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c6361-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c6361-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6361-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c6361-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c6361-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c6361-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c6361-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

