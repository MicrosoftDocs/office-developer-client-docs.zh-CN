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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d992c7ac43c736e01184e1f12b3ad366587c9b06
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777267"
---
# <a name="pidtagaccesscontrollisttable-canonical-property"></a><span data-ttu-id="f884e-103">PidTagAccessControlListTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="f884e-103">PidTagAccessControlListTable Canonical Property</span></span>

  
  
<span data-ttu-id="f884e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f884e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f884e-105">包含表组成的所有系统访问控制列表 (SACL) 应用到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f884e-105">Contains a table that consists of all the system access control lists (SACL) applied to a folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f884e-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="f884e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f884e-107">PR_ACL_TABLE</span><span class="sxs-lookup"><span data-stu-id="f884e-107">PR_ACL_TABLE</span></span>  <br/> |
|<span data-ttu-id="f884e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f884e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f884e-109">0x3FE0</span><span class="sxs-lookup"><span data-stu-id="f884e-109">0x3FE0</span></span>  <br/> |
|<span data-ttu-id="f884e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f884e-110">Data type:</span></span>  <br/> |<span data-ttu-id="f884e-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="f884e-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="f884e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f884e-112">Area:</span></span>  <br/> |<span data-ttu-id="f884e-113">访问控制</span><span class="sxs-lookup"><span data-stu-id="f884e-113">Access Control</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f884e-114">备注</span><span class="sxs-lookup"><span data-stu-id="f884e-114">Remarks</span></span>

<span data-ttu-id="f884e-115">此属性是位于 Exchange 服务器上的所有 folder 对象。</span><span class="sxs-lookup"><span data-stu-id="f884e-115">This property is present on all folder objects on an Exchange Server.</span></span> <span data-ttu-id="f884e-116">包含此属性的值用于以进行读取和修改访问控制列表 (Acl) 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f884e-116">Values included in this property are used for reading and modifying access control lists (ACLs) on folders.</span></span> <span data-ttu-id="f884e-117">您可以使用具有**IID_IExchangeModifyTable**接口标识符[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法获取[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)到文件夹上的 ACL 表格的接口。</span><span class="sxs-lookup"><span data-stu-id="f884e-117">You can use the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method with the **IID_IExchangeModifyTable** interface identifier to obtain an [IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md) interface to the ACL table on a folder.</span></span> <span data-ttu-id="f884e-118">此接口可用于读取和修改这些 Acl。</span><span class="sxs-lookup"><span data-stu-id="f884e-118">You can use this interface to read and modify those ACLs.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f884e-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="f884e-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f884e-120">头文件</span><span class="sxs-lookup"><span data-stu-id="f884e-120">Header files</span></span>

<span data-ttu-id="f884e-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f884e-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="f884e-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f884e-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="f884e-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f884e-123">Mapitags.h</span></span>
  
> <span data-ttu-id="f884e-124">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f884e-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f884e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f884e-125">See also</span></span>



[<span data-ttu-id="f884e-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f884e-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f884e-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f884e-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f884e-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f884e-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f884e-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f884e-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

