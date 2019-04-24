---
title: PidTagAccount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccount
api_type:
- HeaderDef
ms.assetid: bec199b5-abfd-4686-ad59-21092212e1a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2962f973aa87b88f237ded69573df9ef312a7bc5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359776"
---
# <a name="pidtagaccount-canonical-property"></a><span data-ttu-id="3ddaf-103">PidTagAccount 规范属性</span><span class="sxs-lookup"><span data-stu-id="3ddaf-103">PidTagAccount Canonical Property</span></span>

  
  
<span data-ttu-id="3ddaf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ddaf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3ddaf-105">包含收件人的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-105">Contains the recipient's account name.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3ddaf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3ddaf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3ddaf-107">PR_ACCOUNT、PR_ACCOUNT_A、PR_ACCOUNT_W</span><span class="sxs-lookup"><span data-stu-id="3ddaf-107">PR_ACCOUNT, PR_ACCOUNT_A, PR_ACCOUNT_W</span></span>  <br/> |
|<span data-ttu-id="3ddaf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3ddaf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3ddaf-109">0x3A00</span><span class="sxs-lookup"><span data-stu-id="3ddaf-109">0x3A00</span></span>  <br/> |
|<span data-ttu-id="3ddaf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3ddaf-110">Data type:</span></span>  <br/> |<span data-ttu-id="3ddaf-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3ddaf-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3ddaf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3ddaf-112">Area:</span></span>  <br/> |<span data-ttu-id="3ddaf-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="3ddaf-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3ddaf-114">注解</span><span class="sxs-lookup"><span data-stu-id="3ddaf-114">Remarks</span></span>

<span data-ttu-id="3ddaf-115">这些属性可提供收件人的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="3ddaf-116">它们由收件人及其组织定义。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-116">They are defined by the recipient and their organization.</span></span>
  
<span data-ttu-id="3ddaf-117">这些属性通常包含收件人的电子邮件名称, 即电子邮件地址的最终组件, 用于唯一标识本地组织中的收件人。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-117">These properties commonly contain the recipient's email name, that is, the final component of the email address, which uniquely identifies the recipient in the local organization.</span></span> <span data-ttu-id="3ddaf-118">电子邮件名称对应于可确保在某个邮件域中具有唯一性的短名称的 "400. 400" 可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-118">The email name corresponds to the X.400 distinguished name, which is meant to be a short name guaranteed to be unique within a certain messaging domain.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3ddaf-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="3ddaf-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3ddaf-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="3ddaf-120">Protocol specifications</span></span>

<span data-ttu-id="3ddaf-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3ddaf-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3ddaf-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3ddaf-123">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3ddaf-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3ddaf-124">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="3ddaf-125">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3ddaf-125">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3ddaf-126">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3ddaf-127">头文件</span><span class="sxs-lookup"><span data-stu-id="3ddaf-127">Header files</span></span>

<span data-ttu-id="3ddaf-128">mapitags</span><span class="sxs-lookup"><span data-stu-id="3ddaf-128">mapitags.h</span></span>
  
> <span data-ttu-id="3ddaf-129">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-129">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="3ddaf-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3ddaf-130">mapidefs.h</span></span>
  
> <span data-ttu-id="3ddaf-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3ddaf-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3ddaf-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ddaf-132">See also</span></span>



[<span data-ttu-id="3ddaf-133">IMailUser : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="3ddaf-133">IMailUser : IMAPIProp</span></span>](imailuserimapiprop.md)


[<span data-ttu-id="3ddaf-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3ddaf-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3ddaf-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3ddaf-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3ddaf-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3ddaf-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

