---
title: PidTagAccessControlListTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccess
api_type:
- HeaderDef
ms.assetid: 48667fda-ddc4-42ac-9231-761db0a4c1a9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9c71a2b806b810906c13ea4750e5491b1544f640
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332002"
---
# <a name="pidtagaccesscontrollisttable-canonical-property"></a><span data-ttu-id="02d6a-103">PidTagAccessControlListTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="02d6a-103">PidTagAccessControlListTable Canonical Property</span></span>

  
  
<span data-ttu-id="02d6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="02d6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="02d6a-105">包含一个表, 该表由应用于文件夹的所有系统访问控制列表 (SACL) 组成。</span><span class="sxs-lookup"><span data-stu-id="02d6a-105">Contains a table that consists of all the system access control lists (SACL) applied to a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="02d6a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="02d6a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="02d6a-107">PR_ACL_TABLE</span><span class="sxs-lookup"><span data-stu-id="02d6a-107">PR_ACL_TABLE</span></span>  <br/> |
|<span data-ttu-id="02d6a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="02d6a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="02d6a-109">0x3FE0</span><span class="sxs-lookup"><span data-stu-id="02d6a-109">0x3FE0</span></span>  <br/> |
|<span data-ttu-id="02d6a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="02d6a-110">Data type:</span></span>  <br/> |<span data-ttu-id="02d6a-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="02d6a-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="02d6a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="02d6a-112">Area:</span></span>  <br/> |<span data-ttu-id="02d6a-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="02d6a-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="02d6a-114">注解</span><span class="sxs-lookup"><span data-stu-id="02d6a-114">Remarks</span></span>

<span data-ttu-id="02d6a-115">此属性在 Exchange 服务器上的所有 folder 对象上都存在。</span><span class="sxs-lookup"><span data-stu-id="02d6a-115">This property is present on all folder objects on an Exchange Server.</span></span> <span data-ttu-id="02d6a-116">此属性中包含的值用于读取和修改文件夹的访问控制列表 (acl)。</span><span class="sxs-lookup"><span data-stu-id="02d6a-116">Values included in this property are used for reading and modifying access control lists (ACLs) on folders.</span></span> <span data-ttu-id="02d6a-117">您可以将[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法与**IID_IExchangeModifyTable**接口标识符一起使用, 以获取文件夹上的 ACL 表的[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="02d6a-117">You can use the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with the **IID_IExchangeModifyTable** interface identifier to obtain an [IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md) interface to the ACL table on a folder.</span></span> <span data-ttu-id="02d6a-118">您可以使用此接口读取和修改这些 acl。</span><span class="sxs-lookup"><span data-stu-id="02d6a-118">You can use this interface to read and modify those ACLs.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="02d6a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="02d6a-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="02d6a-120">头文件</span><span class="sxs-lookup"><span data-stu-id="02d6a-120">Header files</span></span>

<span data-ttu-id="02d6a-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="02d6a-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="02d6a-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="02d6a-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="02d6a-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="02d6a-123">Mapitags.h</span></span>
  
> <span data-ttu-id="02d6a-124">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="02d6a-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="02d6a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02d6a-125">See also</span></span>



[<span data-ttu-id="02d6a-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="02d6a-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="02d6a-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="02d6a-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="02d6a-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="02d6a-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="02d6a-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="02d6a-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

