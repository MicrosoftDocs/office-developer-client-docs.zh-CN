---
title: IProfAdmin IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin
api_type:
- COM
ms.assetid: 274899cc-2894-4d99-84ec-f18121e856a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cbdfba68490b1e756f277c6e552235368a86f310
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434114"
---
# <a name="iprofadmin--iunknown"></a>IProfAdmin : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
支持对配置文件的管理。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|公开者：  <br/> |配置文件管理对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IProfAdmin  <br/> |
|指针类型：  <br/> |LPPROFADMIN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](iprofadmin-getlasterror.md) <br/> |返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关配置文件管理对象发生的上一个错误的信息。  <br/> |
|[GetProfileTable](iprofadmin-getprofiletable.md) <br/> |提供对配置文件表的访问权限，该表包含有关所有可用配置文件的信息。  <br/> |
|[CreateProfile](iprofadmin-createprofile.md) <br/> |创建新的配置文件。  <br/> |
|[DeleteProfile](iprofadmin-deleteprofile.md) <br/> |删除配置文件。  <br/> |
|[ChangeProfilePassword](iprofadmin-changeprofilepassword.md) <br/> |已弃用。 更改配置文件的密码。  <br/> |
|[CopyProfile](iprofadmin-copyprofile.md) <br/> |复制配置文件。  <br/> |
|[RenameProfile](iprofadmin-renameprofile.md) <br/> |向配置文件分配新名称。  <br/> |
|[SetDefaultProfile](iprofadmin-setdefaultprofile.md) <br/> |设置或清除客户端的默认配置文件。  <br/> |
|[AdminServices](iprofadmin-adminservices.md) <br/> |提供对邮件服务管理对象的访问权限，以对配置文件中的邮件服务进行更改。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

