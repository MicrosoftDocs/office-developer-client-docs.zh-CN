---
title: PidTagAddressBookHierarchicalRootDepartment
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAddressBookHierarchicalRootDepartment
api_type:
- HeaderDef
ms.assetid: c611640b-1a70-4a76-b7ff-c8ad8d320892
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 22a1a62f4ee6ff492f36eb18e2d92c8d70febd72
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382608"
---
# <a name="pidtagaddressbookhierarchicalrootdepartment"></a>PidTagAddressBookHierarchicalRootDepartment

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 包含分层通讯根 (HAB) 的可分辨的名称 (DN)。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EMS_AB_HAB_ROOT_DEPARTMENT PR_EMS_AB_HAB_ROOT_DEPARTMENT_A  <br/> |
|属性进行设置：  <br/> |通讯簿  <br/> |
|长 ID （盖）：  <br/> |0x8C98  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |Exchange 通讯簿  <br/> |
   
## <a name="remarks"></a>说明

这是全局地址列表 (GAL) 容器的属性，并代表分层通讯根的可分辨的名称。 此属性才存在脱机通讯簿中而不会在 Active Directory 域服务 (AD DS)。 呼叫者应将 MAPI_CACHE_ONLY 传递给 GetProps 呼叫，以避免远程过程调用。 如果不存在，呼叫者应使用 PR_EMS_AB_HAB_ROOT_DEPARTMENT，其类型 PT_OBJECT 为，查找根部门。 
  
根部门获得后，它可以具有 MAPI_MAILUSER 或 MAPI_DISTLIST 对象类型。 如果对象类型，MAPI_DISTLIST 正在采用新的架构。 对象类型是 MAPI_MAILUSER，如果要采用的以前的架构。 
  
- Microsoft Office Outlook 2007 Service Pack 2 支持两个架构。 
    
- Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持新的架构。
    
在新的架构中，所有部门组还通讯组列表，以及为类型 MAPI_DISTLIST。 通过完全一样通讯组列表成员 PR_EMS_AB_MEMBER，获得是部门组和部门内部门组的成员。
  
根部门获得后，它可以具有 MAPI_MAILUSER 或 MAPI_DISTLIST 对象类型。 对象类型是 MAPI_DISTLIST，如果正在使用新的架构。 对象类型是 MAPI_MAILUSER，如果正在使用旧的架构。 
  
在新的架构中，所有部门组也是 Dl 和类型 MAPI_DISTLIST。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Microsoft Exchange Server 协议规范的引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

