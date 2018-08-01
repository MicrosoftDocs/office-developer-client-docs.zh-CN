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
ms.openlocfilehash: 694cc4e4626fb9070927232bb72252f716eb458e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777830"
---
# <a name="pidtagmembername-canonical-property"></a><span data-ttu-id="88abf-103">PidTagMemberName 规范属性</span><span class="sxs-lookup"><span data-stu-id="88abf-103">PidTagMemberName Canonical Property</span></span>

  
  
<span data-ttu-id="88abf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="88abf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="88abf-105">包含成员的访问控制列表 (ACL) 表的显示的名称。</span><span class="sxs-lookup"><span data-stu-id="88abf-105">Contains the display name of a member of the access control list (ACL) table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="88abf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="88abf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="88abf-107">PR_MEMBER_NAME，PR_MEMBER_NAME_A，PR_MEMBER_NAME_W</span><span class="sxs-lookup"><span data-stu-id="88abf-107">PR_MEMBER_NAME, PR_MEMBER_NAME_A, PR_MEMBER_NAME_W</span></span>  <br/> |
|<span data-ttu-id="88abf-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="88abf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="88abf-109">0x6672</span><span class="sxs-lookup"><span data-stu-id="88abf-109">0x6672</span></span>  <br/> |
|<span data-ttu-id="88abf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="88abf-110">Data type:</span></span>  <br/> |<span data-ttu-id="88abf-111">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="88abf-111">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="88abf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="88abf-112">Area:</span></span>  <br/> |<span data-ttu-id="88abf-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="88abf-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="88abf-114">说明</span><span class="sxs-lookup"><span data-stu-id="88abf-114">Remarks</span></span>

<span data-ttu-id="88abf-115">通过使用这些属性[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)界面来显示 ACL 表，即的人员或与显式权限的文件夹或邮箱角色的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="88abf-115">These properties are used by the [IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md) interface to display the name of a member of an ACL table, which is a person or role with explicit rights on a folder or mailbox.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="88abf-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="88abf-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="88abf-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="88abf-117">Protocol specifications</span></span>

<span data-ttu-id="88abf-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="88abf-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="88abf-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="88abf-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="88abf-120">[[MS OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="88abf-120">[[MS-OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="88abf-121">处理检索存储在服务器的文件夹的权限列表。</span><span class="sxs-lookup"><span data-stu-id="88abf-121">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="88abf-122">头文件</span><span class="sxs-lookup"><span data-stu-id="88abf-122">Header files</span></span>

<span data-ttu-id="88abf-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="88abf-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="88abf-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="88abf-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="88abf-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="88abf-125">Mapitags.h</span></span>
  
> <span data-ttu-id="88abf-126">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="88abf-126">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="88abf-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88abf-127">See also</span></span>



[<span data-ttu-id="88abf-128">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="88abf-128">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="88abf-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="88abf-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="88abf-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="88abf-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="88abf-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="88abf-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="88abf-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="88abf-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

