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
ms.openlocfilehash: 34f61f3ef64e5751f9be3df534c4379583447799
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592694"
---
# <a name="pidtagcontactaddressbookmultipleaddressflag-canonical-property"></a><span data-ttu-id="e789e-103">PidTagContactAddressBookMultipleAddressFlag 规范属性</span><span class="sxs-lookup"><span data-stu-id="e789e-103">PidTagContactAddressBookMultipleAddressFlag Canonical Property</span></span>

  
  
<span data-ttu-id="e789e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e789e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e789e-105">包含一个提供程序支持每个联系人项目的多个电子邮件地址时为 TRUE 的标志。</span><span class="sxs-lookup"><span data-stu-id="e789e-105">Contains a flag that is TRUE when the provider supports multiple email addresses per contact item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e789e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e789e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e789e-107">PR_CONTAB_MULTI_ADDR_FLAG</span><span class="sxs-lookup"><span data-stu-id="e789e-107">PR_CONTAB_MULTI_ADDR_FLAG</span></span>  <br/> |
|<span data-ttu-id="e789e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e789e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e789e-109">0x6614</span><span class="sxs-lookup"><span data-stu-id="e789e-109">0x6614</span></span>  <br/> |
|<span data-ttu-id="e789e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e789e-110">Data type:</span></span>  <br/> |<span data-ttu-id="e789e-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="e789e-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="e789e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e789e-112">Area:</span></span>  <br/> |<span data-ttu-id="e789e-113">联系人通讯簿</span><span class="sxs-lookup"><span data-stu-id="e789e-113">Contact address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e789e-114">注解</span><span class="sxs-lookup"><span data-stu-id="e789e-114">Remarks</span></span>

<span data-ttu-id="e789e-115">如果此属性为 TRUE，则提供程序不允许没有电子邮件地址的联系人。</span><span class="sxs-lookup"><span data-stu-id="e789e-115">If this property is TRUE, the provider does not allow contacts without email addresses.</span></span> <span data-ttu-id="e789e-116">如果为 FALSE，提供程序将显示所有联系人拥有主电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e789e-116">If FALSE, the provider shows all contacts whether or not they have a primary email address.</span></span> <span data-ttu-id="e789e-117">将有效仅的主电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e789e-117">Only the primary email address will be honored.</span></span> <span data-ttu-id="e789e-118">这是联系人通讯簿容器和联系人通讯簿容器的表中的列上的属性。</span><span class="sxs-lookup"><span data-stu-id="e789e-118">This is a property on a Contact Address Book container, and a column in the table of Contact Address Book containers.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e789e-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="e789e-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e789e-120">头文件</span><span class="sxs-lookup"><span data-stu-id="e789e-120">Header files</span></span>

<span data-ttu-id="e789e-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e789e-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="e789e-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e789e-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="e789e-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e789e-123">Mapitags.h</span></span>
  
> <span data-ttu-id="e789e-124">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e789e-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e789e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e789e-125">See also</span></span>



[<span data-ttu-id="e789e-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e789e-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e789e-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e789e-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e789e-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e789e-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e789e-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e789e-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

