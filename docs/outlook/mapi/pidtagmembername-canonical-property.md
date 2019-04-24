---
title: PidTagMemberName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberName
api_type:
- HeaderDef
ms.assetid: e19129bf-d07c-4d2e-9d4d-edbfda088ea7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a119cf1446600153e433c4aae99037d9810015c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342481"
---
# <a name="pidtagmembername-canonical-property"></a><span data-ttu-id="a8c5f-103">PidTagMemberName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a8c5f-103">PidTagMemberName Canonical Property</span></span>

  
  
<span data-ttu-id="a8c5f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a8c5f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a8c5f-105">包含访问控制列表 (ACL) 表的成员的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a8c5f-105">Contains the display name of a member of the access control list (ACL) table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a8c5f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a8c5f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a8c5f-107">PR_MEMBER_NAME、PR_MEMBER_NAME_A、PR_MEMBER_NAME_W</span><span class="sxs-lookup"><span data-stu-id="a8c5f-107">PR_MEMBER_NAME, PR_MEMBER_NAME_A, PR_MEMBER_NAME_W</span></span>  <br/> |
|<span data-ttu-id="a8c5f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a8c5f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a8c5f-109">0x6672</span><span class="sxs-lookup"><span data-stu-id="a8c5f-109">0x6672</span></span>  <br/> |
|<span data-ttu-id="a8c5f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a8c5f-110">Data type:</span></span>  <br/> |<span data-ttu-id="a8c5f-111">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="a8c5f-111">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="a8c5f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a8c5f-112">Area:</span></span>  <br/> |<span data-ttu-id="a8c5f-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="a8c5f-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a8c5f-114">注解</span><span class="sxs-lookup"><span data-stu-id="a8c5f-114">Remarks</span></span>

<span data-ttu-id="a8c5f-115">[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)接口使用这些属性来显示 ACL 表的成员名称, 该名称是对文件夹或邮箱具有明确权限的人员或角色。</span><span class="sxs-lookup"><span data-stu-id="a8c5f-115">These properties are used by the [IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md) interface to display the name of a member of an ACL table, which is a person or role with explicit rights on a folder or mailbox.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a8c5f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="a8c5f-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a8c5f-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="a8c5f-117">Protocol specifications</span></span>

<span data-ttu-id="a8c5f-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a8c5f-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a8c5f-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a8c5f-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a8c5f-120">[[毫秒-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a8c5f-120">[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a8c5f-121">处理存储在服务器上的文件夹权限列表的检索。</span><span class="sxs-lookup"><span data-stu-id="a8c5f-121">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a8c5f-122">头文件</span><span class="sxs-lookup"><span data-stu-id="a8c5f-122">Header files</span></span>

<span data-ttu-id="a8c5f-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a8c5f-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="a8c5f-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a8c5f-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="a8c5f-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="a8c5f-125">Mapitags.h</span></span>
  
> <span data-ttu-id="a8c5f-126">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a8c5f-126">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a8c5f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8c5f-127">See also</span></span>



[<span data-ttu-id="a8c5f-128">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a8c5f-128">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="a8c5f-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a8c5f-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a8c5f-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a8c5f-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a8c5f-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a8c5f-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a8c5f-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a8c5f-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

