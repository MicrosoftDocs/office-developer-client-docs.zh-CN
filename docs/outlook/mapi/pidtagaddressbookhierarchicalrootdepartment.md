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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326122"
---
# <a name="pidtagaddressbookhierarchicalrootdepartment"></a>PidTagAddressBookHierarchicalRootDepartment

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 包含层次结构地址根 (DN) DN (HAB) 。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EMS_AB_HAB_ROOT_DEPARTMENT、PR_EMS_AB_HAB_ROOT_DEPARTMENT_A  <br/> |
|属性集：  <br/> |通讯簿  <br/> |
|LONG ID (的一) ：  <br/> |0x8C98  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |Exchange通讯簿  <br/> |
   
## <a name="remarks"></a>备注

这是全局地址列表上的一个属性 (GAL) ，表示分层地址根的可分辨名称。 此属性仅存在于脱机通讯簿中，从不存在于 AD DS (Active Directory 域服务) 。 调用方应MAPI_CACHE_ONLY GetProps 调用，以避免远程过程调用。 如果不存在，则调用方应该PR_EMS_AB_HAB_ROOT_DEPARTMENT类型为 PT_OBJECT，以查找根部门。 
  
获取根部门后，它可以具有一个对象类型 MAPI_MAILUSER或MAPI_DISTLIST。 如果对象类型，MAPI_DISTLIST新架构。 如果对象类型，MAPI_MAILUSER上一个架构。 
  
- Microsoft Office Outlook 2007 Service Pack 2 支持这两种架构。 
    
- Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持新架构。
    
在新的架构中，所有部门组也是通讯组列表，并且MAPI_DISTLIST。 部门组的成员和部门组内的部门成员是通过使用通讯组PR_EMS_AB_MEMBER，与通讯组列表成员完全相同。
  
获取根部门后，它可以具有一个对象类型 MAPI_MAILUSER或MAPI_DISTLIST。 如果对象类型新MAPI_DISTLIST，则使用新架构。 如果对象类型，MAPI_MAILUSER旧架构。 
  
在新的架构中，所有部门组也是 DLL，并且MAPI_DISTLIST。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Microsoft Exchange Server引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

